# Introduction-au-langage-C

# 📌 **1. Introduction au langage C**
Le langage **C** est un langage de programmation bas niveau, efficace et puissant. Il est utilisé pour la programmation système, les systèmes embarqués et le développement de logiciels performants.

---

# 📌 **2. Structure de base d’un programme en C**
Un programme en C suit une structure précise :

```c
#include <stdio.h>  // 📌 Inclusion de la bibliothèque standard d'entrée/sortie

int main() {  // 📌 Fonction principale
    printf("Bonjour, C !\n");  // 📌 Affichage à l'écran
    return 0;  // 📌 Indique que le programme s'est exécuté avec succès
}
```

✅ `#include <stdio.h>` : Inclusion de la bibliothèque standard.  
✅ `main()` : Point d'entrée du programme.  
✅ `printf()` : Fonction d'affichage.  
✅ `return 0;` : Indique que le programme s’est terminé sans erreur.  

---

# 📌 **3. Variables et types de données**
En C, chaque variable a un type défini.

### **🔹 Types de base**
| Type        | Taille (en octets) | Valeur possible |
|------------|----------------|----------------|
| `char`     | 1              | Caractère (`'A'`) |
| `int`      | 2 ou 4         | Nombre entier |
| `float`    | 4              | Nombre à virgule flottante |
| `double`   | 8              | Nombre flottant plus précis |

### **🔹 Déclaration et affectation**
```c
int age = 25;
float pi = 3.14;
char lettre = 'A';

printf("Âge : %d, Pi : %.2f, Lettre : %c\n", age, pi, lettre);
```
✅ `%d` : Affichage d’un entier.  
✅ `%.2f` : Affichage d’un flottant avec 2 décimales.  
✅ `%c` : Affichage d’un caractère.  

---

# 📌 **4. Opérateurs en C**
| Opérateur | Description | Exemple |
|-----------|------------|---------|
| `+` | Addition | `a + b` |
| `-` | Soustraction | `a - b` |
| `*` | Multiplication | `a * b` |
| `/` | Division | `a / b` |
| `%` | Modulo (reste de division) | `a % b` |

### **Exemple :**
```c
int a = 10, b = 3;
printf("Addition: %d\n", a + b);  // 13
printf("Modulo: %d\n", a % b);    // 1
```

---

# 📌 **5. Conditions (`if`, `else`, `switch`)**
Les structures conditionnelles permettent d'exécuter des blocs de code selon des conditions.

### **🔹 `if` / `else if` / `else`**
```c
int age = 20;

if (age < 18) {
    printf("Mineur\n");
} else if (age == 18) {
    printf("Juste majeur\n");
} else {
    printf("Majeur\n");
}
```

### **🔹 `switch`**
```c
int jour = 3;

switch (jour) {
    case 1: printf("Lundi\n"); break;
    case 2: printf("Mardi\n"); break;
    case 3: printf("Mercredi\n"); break;
    default: printf("Jour inconnu\n");
}
```

✅ `break;` empêche l’exécution des autres cas.  

---

# 📌 **6. Boucles (`for`, `while`, `do while`)**
Les boucles permettent d’exécuter un bloc de code plusieurs fois.

### **🔹 `for`**
```c
for (int i = 0; i < 5; i++) {
    printf("i = %d\n", i);
}
```
✅ Boucle **for** : Initialisation → Condition → Incrémentation.

### **🔹 `while`**
```c
int i = 0;
while (i < 5) {
    printf("i = %d\n", i);
    i++;
}
```

### **🔹 `do while`**
```c
int i = 0;
do {
    printf("i = %d\n", i);
    i++;
} while (i < 5);
```
✅ `do while` exécute au moins une fois le bloc avant de tester la condition.  

---

# 📌 **7. Fonctions**
Les fonctions permettent de structurer le code en blocs réutilisables.

### **🔹 Définition et appel d’une fonction**
```c
#include <stdio.h>

// Déclaration de la fonction
void direBonjour() {
    printf("Bonjour !\n");
}

int main() {
    direBonjour();  // Appel de la fonction
    return 0;
}
```
✅ `void` signifie que la fonction ne retourne rien.

### **🔹 Fonction avec paramètres et retour**
```c
int somme(int a, int b) {
    return a + b;
}

int main() {
    int resultat = somme(5, 3);
    printf("Somme = %d\n", resultat);
    return 0;
}
```
✅ `somme(int a, int b)` : Fonction prenant deux paramètres et retournant un entier.

---

# 📌 **8. Tableaux et chaînes de caractères**
### **🔹 Tableaux**
```c
int nombres[3] = {10, 20, 30};
printf("Premier élément : %d\n", nombres[0]);
```

### **🔹 Chaînes de caractères**
```c
char nom[] = "C Programmation";
printf("Nom : %s\n", nom);
```
✅ `%s` permet d’afficher une chaîne de caractères.  

---

# 📌 **9. Pointeurs**
Les pointeurs stockent l’adresse d’une variable.

### **🔹 Déclaration et utilisation**
```c
int a = 10;
int* p = &a;

printf("Adresse de a : %p\n", p);
printf("Valeur de a via p : %d\n", *p);
```
✅ `*p` permet d’accéder à la valeur stockée à l’adresse.  

---

# 📌 **10. Fichiers (`fopen`, `fwrite`, `fread`)**
Lire et écrire dans des fichiers.

### **🔹 Écriture dans un fichier**
```c
#include <stdio.h>

int main() {
    FILE* fichier = fopen("test.txt", "w");  // Ouvrir en mode écriture
    if (fichier != NULL) {
        fprintf(fichier, "Hello, fichier !\n");
        fclose(fichier);
    }
    return 0;
}
```

### **🔹 Lecture d’un fichier**
```c
#include <stdio.h>

int main() {
    char texte[100];
    FILE* fichier = fopen("test.txt", "r");
    if (fichier != NULL) {
        fgets(texte, 100, fichier);
        printf("Contenu : %s\n", texte);
        fclose(fichier);
    }
    return 0;
}
```
✅ `fopen("fichier.txt", "w")` : Ouvre un fichier en écriture.  
✅ `fprintf()` : Écrit du texte dans un fichier.  
✅ `fgets()` : Lit une ligne d’un fichier.  

---

## 🚀 **Conclusion**
✔️ **Base du C** : Variables, opérateurs, structures conditionnelles, boucles.  
✔️ **Modularité** : Fonctions pour organiser le code.  
✔️ **Pointeurs** : Gestion avancée de la mémoire.  
✔️ **Manipulation de fichiers** : Lire et écrire des fichiers avec `fopen()`.  

Si tu veux des exercices ou plus d’explications sur un sujet précis, dis-moi ! 😊
