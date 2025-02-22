
---

## **Correction des exercices - Tableaux et chaînes de caractères**

### **Exercice 8 : Tableaux**
```c
#include <stdio.h>

int main() {
    int nombres[5], somme = 0;
    
    printf("Entrez 5 nombres entiers :\n");
    for (int i = 0; i < 5; i++) {
        scanf("%d", &nombres[i]);
        somme += nombres[i];
    }
    
    printf("La somme des nombres est : %d\n", somme);
    
    return 0;
}
```

---

### **Exercice 9 : Chaînes de caractères**
```c
#include <stdio.h>

int main() {
    char prenom[50], nom[50];

    printf("Entrez votre prénom : ");
    scanf("%s", prenom);
    
    printf("Entrez votre nom : ");
    scanf("%s", nom);
    
    printf("Bonjour %s %s !\n", prenom, nom);
    
    return 0;
}
```
📌 **Remarque** : La fonction `scanf("%s", prenom)` lit une chaîne sans espace. Pour prendre en charge des noms avec espaces, utiliser `fgets()`.

---

### **Exercice 10 : Palindrome**
```c
#include <stdio.h>
#include <string.h>

int estPalindrome(char *chaine) {
    int debut = 0, fin = strlen(chaine) - 1;
    
    while (debut < fin) {
        if (chaine[debut] != chaine[fin]) {
            return 0;
        }
        debut++;
        fin--;
    }
    return 1;
}

int main() {
    char mot[100];

    printf("Entrez un mot : ");
    scanf("%s", mot);

    if (estPalindrome(mot)) {
        printf("Le mot \"%s\" est un palindrome.\n", mot);
    } else {
        printf("Le mot \"%s\" n'est pas un palindrome.\n", mot);
    }

    return 0;
}
```
📌 **Remarque** : Cette solution ne gère pas les espaces ni la casse. Une amélioration consisterait à convertir les majuscules en minuscules et à ignorer les espaces.