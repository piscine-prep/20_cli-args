# Compteur de lettres avec arguments

## Introduction

Cet exercice vous permettra d'apprendre à utiliser les arguments passés à votre programme via la ligne de commande pour analyser des mots. Vous allez créer un programme simple qui compte les lettres dans un mot, puis étendre cette fonctionnalité pour analyser plusieurs mots à la fois. C'est une excellente introduction aux paramètres `argc` et `argv` de la fonction `main`.

## Exercice

### Partie 1 : Analyse d'un seul mot

Créez un programme C qui :

1. Reçoit un mot en argument via la ligne de commande
2. Compte le nombre total de lettres dans ce mot
3. Compte combien de fois la lettre 'e' apparaît dans le mot
4. Affiche ces informations de manière claire

Voici un exemple de structure pour commencer :

```c
#include <stdio.h>

int main(int argc, char **argv) {
    // Vérifier qu'un mot a été fourni

    // Analyser le mot fourni

    // Afficher les résultats

    return 0;
}
```

### Partie 2 : Analyse de plusieurs mots

Modifiez votre programme pour :

1. Accepter plusieurs mots en arguments
2. Pour chaque mot, afficher son analyse individuelle (nombre de lettres et nombre de 'e')
3. Calculer et afficher les totaux pour tous les mots combinés

### Partie 3 : Analyse complète avec détails

Étendez votre programme pour :

1. Afficher une liste numérotée de tous les mots analysés
2. Montrer les statistiques individuelles pour chaque mot
3. Calculer et afficher les statistiques globales (total de lettres, total de 'e', pourcentage de 'e')
4. Identifier le mot qui contient le plus de lettres 'e'

## Résultat attendu

Votre programme doit fonctionner comme suit lorsqu'il est compilé sous le nom `compteur` :

```bash
$ ./compteur
Erreur : Veuillez fournir au moins un mot à analyser.
Usage : ./compteur <mot1> [mot2] [mot3] ...

$ ./compteur bonjour
=== ANALYSE D'UN MOT ===
Mot analysé : "bonjour"
Nombre de lettres : 7
Nombre de 'e' : 0

$ ./compteur hello world
=== ANALYSE DE PLUSIEURS MOTS ===
1. "hello"
   - Nombre de lettres : 5
   - Nombre de 'e' : 1

2. "world"
   - Nombre de lettres : 5
   - Nombre de 'e' : 0

=== STATISTIQUES GLOBALES ===
Nombre total de mots : 2
Nombre total de lettres : 10
Nombre total de 'e' : 1
Pourcentage de 'e' : 10%

$ ./compteur telephone ordinateur clavier
=== ANALYSE DE PLUSIEURS MOTS ===
1. "telephone"
   - Nombre de lettres : 9
   - Nombre de 'e' : 3

2. "ordinateur"
   - Nombre de lettres : 10
   - Nombre de 'e' : 1

3. "clavier"
   - Nombre de lettres : 7
   - Nombre de 'e' : 1

=== STATISTIQUES GLOBALES ===
Nombre total de mots : 3
Nombre total de lettres : 26
Nombre total de 'e' : 5
Pourcentage de 'e' : 19%
Mot avec le plus de 'e' : "telephone" (3 occurrences)
```

## Astuces

- `argc` contient le nombre total d'arguments (nom du programme + mots fournis)
- `argv[0]` est le nom du programme, `argv[1]` est le premier mot, etc.
- Pour compter les lettres d'un mot, parcourez chaque caractère jusqu'à `'\0'`
- Pour compter les 'e', vérifiez si chaque caractère est égal à 'e'
- N'oubliez pas de vérifier que `argc` est supérieur à 1 avant d'accéder aux arguments
- Pour calculer un pourcentage : `(nombre_de_e * 100) / nombre_total_lettres`

## Pour aller plus loin

Si vous souhaitez approfondir cet exercice, vous pourriez :

- Compter d'autres lettres en plus du 'e' (comme les voyelles)
- Ignorer la casse (compter 'E' et 'e' ensemble)
- Identifier le mot le plus long et le plus court
- Calculer la longueur moyenne des mots

---

_Les arguments de ligne de commande sont un moyen simple et efficace de passer des données à votre programme. Cette technique est largement utilisée dans les outils système et les utilitaires._
