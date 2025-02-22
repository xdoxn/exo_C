
---

## **Correction des exercices - Fonctions et pointeurs**

### **Exercice 11 : Fonction simple**
```c
#include <stdio.h>

int carre(int nombre) {
    return nombre * nombre;
}

int main() {
    int nombre;
    
    printf("Entrez un nombre : ");
    scanf("%d", &nombre);
    
    printf("Le carré de %d est %d\n", nombre, carre(nombre));
    
    return 0;
}
```

---

### **Exercice 12 : Fonction avec plusieurs paramètres**
```c
#include <stdio.h>

int somme(int a, int b) {
    return a + b;
}

int main() {
    int x, y;
    
    printf("Entrez deux nombres : ");
    scanf("%d %d", &x, &y);
    
    printf("La somme de %d et %d est %d\n", x, y, somme(x, y));
    
    return 0;
}
```

---

### **Exercice 13 : Pointeurs et modification de variable**
```c
#include <stdio.h>

void echanger(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 5, y = 10;
    
    printf("Avant échange : x = %d, y = %d\n", x, y);
    echanger(&x, &y);
    printf("Après échange : x = %d, y = %d\n", x, y);
    
    return 0;
}
```

---

### **Exercice 14 : Allocation dynamique**
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n, *tableau;
    
    printf("Entrez la taille du tableau : ");
    scanf("%d", &n);
    
    tableau = (int *)malloc(n * sizeof(int));
    
    if (tableau == NULL) {
        printf("Échec de l'allocation mémoire\n");
        return 1;
    }
    
    printf("Entrez %d nombres :\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &tableau[i]);
    }
    
    printf("Vous avez entré : ");
    for (int i = 0; i < n; i++) {
        printf("%d ", tableau[i]);
    }
    printf("\n");

    free(tableau);
    
    return 0;
}
```
📌 **Remarque** : Toujours libérer la mémoire allouée avec `free()`.

---