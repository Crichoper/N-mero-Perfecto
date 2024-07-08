# Numero-Perfecto
#include <stdio.h>
#include <conio.h>
int esPerfecto(int num) {
    int sumaDivisores = 0;
    for (int i = 1; i <= num / 2; i++) {
        if (num % i == 0) {
            sumaDivisores += i;
        }
    }
    return sumaDivisores == num;
}
void encontrarNumerosPerfectos(int limite) {
    int contador = 0;
    int i = 1;
    printf("Numeros perfectos hasta %d:\n", limite); 
    while (i <= limite && i <= 1000) {
        if (esPerfecto(i)) {
            printf("%d ", i);
            contador++;
        }
        i++;
    }
    printf("\nCantidad de numeros perfectos: %d\n", contador);
}
int main() {
    int NUM;
    char opcion;
    do {
        printf("Ingrese un numero (entero positivo): ");
        scanf("%d", &NUM);
        if (NUM <= 0) {
            printf("El numero ingresado no es valido. Debe ser positivo.\n");
        } else {
            printf("Solo se mostraran los numeros perfectos del 1 hasta el 1000.\n");
            encontrarNumerosPerfectos(NUM);
        }
        printf("\nDesea ingresar otro numero? (s/n): ");
        scanf(" %c", &opcion);
    } while (opcion == 's' || opcion == 'S');
    printf("Fin del programa.\n");
    getch();
    return 0;
}
