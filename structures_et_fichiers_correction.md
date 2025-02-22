
---

## **Correction des exercices - Structures et fichiers**

### **Exercice 15 : Structure simple**
```c
#include <stdio.h>

struct Personne {
    char nom[50];
    int age;
};

int main() {
    struct Personne p;
    
    printf("Entrez votre nom : ");
    scanf("%s", p.nom);
    
    printf("Entrez votre âge : ");
    scanf("%d", &p.age);
    
    printf("Nom : %s, Âge : %d\n", p.nom, p.age);
    
    return 0;
}
```

📌 **Remarque** : Pour lire des noms avec des espaces, utilisez `fgets(p.nom, 50, stdin);`.

---

### **Exercice 16 : Tableau de structures**
```c
#include <stdio.h>

struct Etudiant {
    char nom[50];
    float moyenne;
};

int main() {
    struct Etudiant etudiants[3];

    for (int i = 0; i < 3; i++) {
        printf("Entrez le nom de l'étudiant %d : ", i + 1);
        scanf("%s", etudiants[i].nom);
        
        printf("Entrez sa moyenne : ");
        scanf("%f", &etudiants[i].moyenne);
    }

    printf("\nListe des étudiants :\n");
    for (int i = 0; i < 3; i++) {
        printf("Nom : %s, Moyenne : %.2f\n", etudiants[i].nom, etudiants[i].moyenne);
    }

    return 0;
}
```

---

### **Exercice 17 : Écriture dans un fichier**
```c
#include <stdio.h>

int main() {
    FILE *fichier = fopen("donnees.txt", "w");

    if (fichier == NULL) {
        printf("Erreur d'ouverture du fichier.\n");
        return 1;
    }

    fprintf(fichier, "Bonjour, ceci est un fichier texte en C !\n");
    
    fclose(fichier);
    
    printf("Données écrites dans le fichier avec succès.\n");

    return 0;
}
```

---

### **Exercice 18 : Lecture d'un fichier**
```c
#include <stdio.h>

int main() {
    FILE *fichier = fopen("donnees.txt", "r");
    char ligne[100];

    if (fichier == NULL) {
        printf("Erreur d'ouverture du fichier.\n");
        return 1;
    }

    while (fgets(ligne, sizeof(ligne), fichier) != NULL) {
        printf("%s", ligne);
    }

    fclose(fichier);
    
    return 0;
}
```

---
