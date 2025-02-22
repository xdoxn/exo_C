## **Correction des exercices - Bases du C**

### **Exercice 1 : Affichage simple**
```c
#include <stdio.h>

int main() {
    printf("Bonjour, bienvenue en langage C !\n");
    return 0;
}
```

---

### **Exercice 2 : Variables et types de données**
```c
#include <stdio.h>

int main() {
    int entier = 42;
    float reel = 3.14;
    char caractere = 'A';

    printf("Entier : %d\n", entier);
    printf("Réel : %.2f\n", reel);
    printf("Caractère : %c\n", caractere);

    return 0;
}
```

---

### **Exercice 3 : Opérations arithmétiques**
```c
#include <stdio.h>

int main() {
    int a, b;
    
    printf("Entrez deux nombres entiers : ");
    scanf("%d %d", &a, &b);
    
    printf("Somme : %d\n", a + b);
    printf("Différence : %d\n", a - b);
    printf("Produit : %d\n", a * b);
    
    if (b != 0) {
        printf("Quotient : %d\n", a / b);
        printf("Reste : %d\n", a % b);
    } else {
        printf("Division par zéro impossible.\n");
    }

    return 0;
}
```