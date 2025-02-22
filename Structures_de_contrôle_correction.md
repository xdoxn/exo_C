## **Correction des exercices - Structures de contrôle**

### **Exercice 4 : Conditions (if, else)**
```c
#include <stdio.h>

int main() {
    int age;
    
    printf("Entrez votre âge : ");
    scanf("%d", &age);
    
    if (age >= 18) {
        printf("Vous êtes majeur.\n");
    } else {
        printf("Vous êtes mineur.\n");
    }

    return 0;
}
```

---

### **Exercice 5 : Boucle for**
```c
#include <stdio.h>

int main() {
    printf("Les 10 premiers nombres pairs :\n");
    for (int i = 0; i < 10; i++) {
        printf("%d ", i * 2);
    }
    printf("\n");
    return 0;
}
```

---

### **Exercice 6 : Boucle while**
```c
#include <stdio.h>

int main() {
    int nombre;
    
    do {
        printf("Entrez un nombre entre 1 et 10 : ");
        scanf("%d", &nombre);
    } while (nombre < 1 || nombre > 10);
    
    printf("Vous avez entré : %d\n", nombre);
    
    return 0;
}
```

---

### **Exercice 7 : Switch case**
```c
#include <stdio.h>

int main() {
    int jour;
    
    printf("Entrez un numéro de jour (1 à 7) : ");
    scanf("%d", &jour);
    
    switch (jour) {
        case 1: printf("Lundi\n"); break;
        case 2: printf("Mardi\n"); break;
        case 3: printf("Mercredi\n"); break;
        case 4: printf("Jeudi\n"); break;
        case 5: printf("Vendredi\n"); break;
        case 6: printf("Samedi\n"); break;
        case 7: printf("Dimanche\n"); break;
        default: printf("Numéro invalide !\n");
    }

    return 0;
}
```