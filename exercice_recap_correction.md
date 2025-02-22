
---

## **Correction de l'exercice final - Gestion d'étudiants avec fichiers et structures**

### **Explication de la solution**
Ce programme permet :  
✅ **D'ajouter des étudiants** (nom, âge, moyenne)  
✅ **D'afficher la liste des étudiants**  
✅ **De sauvegarder les données dans un fichier**  
✅ **De charger les données au démarrage**  

---

### **Code complet**
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_ETUDIANTS 100
#define FICHIER "etudiants.txt"

struct Etudiant {
    char nom[50];
    int age;
    float moyenne;
};

void ajouterEtudiant(struct Etudiant etudiants[], int *nbEtudiants) {
    if (*nbEtudiants >= MAX_ETUDIANTS) {
        printf("Nombre maximum d'étudiants atteint.\n");
        return;
    }

    printf("Nom : ");
    scanf("%s", etudiants[*nbEtudiants].nom);

    printf("Âge : ");
    scanf("%d", &etudiants[*nbEtudiants].age);

    printf("Moyenne : ");
    scanf("%f", &etudiants[*nbEtudiants].moyenne);

    (*nbEtudiants)++;
}

void afficherEtudiants(struct Etudiant etudiants[], int nbEtudiants) {
    printf("\nListe des étudiants :\n");
    for (int i = 0; i < nbEtudiants; i++) {
        printf("Nom : %s, Âge : %d, Moyenne : %.2f\n", etudiants[i].nom, etudiants[i].age, etudiants[i].moyenne);
    }
}

void sauvegarderEtudiants(struct Etudiant etudiants[], int nbEtudiants) {
    FILE *fichier = fopen(FICHIER, "w");
    if (fichier == NULL) {
        printf("Erreur d'ouverture du fichier.\n");
        return;
    }

    for (int i = 0; i < nbEtudiants; i++) {
        fprintf(fichier, "%s %d %.2f\n", etudiants[i].nom, etudiants[i].age, etudiants[i].moyenne);
    }

    fclose(fichier);
    printf("Données sauvegardées.\n");
}

void chargerEtudiants(struct Etudiant etudiants[], int *nbEtudiants) {
    FILE *fichier = fopen(FICHIER, "r");
    if (fichier == NULL) {
        printf("Aucune donnée précédente trouvée.\n");
        return;
    }

    while (fscanf(fichier, "%s %d %f", etudiants[*nbEtudiants].nom, &etudiants[*nbEtudiants].age, &etudiants[*nbEtudiants].moyenne) == 3) {
        (*nbEtudiants)++;
    }

    fclose(fichier);
    printf("Données chargées avec succès.\n");
}

int main() {
    struct Etudiant etudiants[MAX_ETUDIANTS];
    int nbEtudiants = 0;
    int choix;

    chargerEtudiants(etudiants, &nbEtudiants);

    do {
        printf("\nMenu :\n");
        printf("1. Ajouter un étudiant\n");
        printf("2. Afficher les étudiants\n");
        printf("3. Sauvegarder et quitter\n");
        printf("Choix : ");
        scanf("%d", &choix);

        switch (choix) {
            case 1:
                ajouterEtudiant(etudiants, &nbEtudiants);
                break;
            case 2:
                afficherEtudiants(etudiants, nbEtudiants);
                break;
            case 3:
                sauvegarderEtudiants(etudiants, nbEtudiants);
                printf("Au revoir !\n");
                break;
            default:
                printf("Choix invalide.\n");
        }
    } while (choix != 3);

    return 0;
}
```

---

### **Explication du code**
✔ **Structures** : Utilisation de `struct Etudiant` pour stocker les infos.  
✔ **Fichiers** : Lecture/écriture des étudiants (`fscanf` et `fprintf`).  
✔ **Tableaux** : Stockage dynamique dans un tableau.  
✔ **Pointeurs** : Passage de `nbEtudiants` par adresse pour mise à jour.  
✔ **Boucles et conditions** : Interaction via un menu.  

---

### **Exemple d'utilisation**
```
Menu :
1. Ajouter un étudiant
2. Afficher les étudiants
3. Sauvegarder et quitter
Choix : 1
Nom : Alice
Âge : 21
Moyenne : 15.5

Menu :
1. Ajouter un étudiant
2. Afficher les étudiants
3. Sauvegarder et quitter
Choix : 2
Liste des étudiants :
Nom : Alice, Âge : 21, Moyenne : 15.50

Menu :
1. Ajouter un étudiant
2. Afficher les étudiants
3. Sauvegarder et quitter
Choix : 3
Données sauvegardées.
Au revoir !
```

---
