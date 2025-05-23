# Analyseur de texte avec arguments de ligne de commande

## Introduction

Cet exercice vous permettra de maîtriser les tableaux de caractères (chaînes de caractères) en C tout en apprenant à utiliser les arguments passés au programme via la ligne de commande. Vous découvrirez comment accéder aux paramètres `argc` et `argv` de la fonction `main` pour créer des programmes qui peuvent être exécutés avec différents arguments, comme les outils en ligne de commande classiques.

## Exercice

### Partie 1 : Affichage des arguments reçus

Créez un programme C qui :

1. Utilise les paramètres `argc` et `argv` dans la fonction `main`
2. Affiche le nombre d'arguments reçus (y compris le nom du programme)
3. Affiche chaque argument avec son numéro de position
4. Gère le cas où aucun argument n'est fourni

Voici un exemple de structure pour commencer :

```c
#include <stdio.h>

int main(int argc, char *argv[]) {
    // Vérification du nombre d'arguments

    // Affichage des informations sur les arguments

    // Parcours et affichage de chaque argument

    return 0;
}
```

### Partie 2 : Analyse des mots fournis

Modifiez votre programme pour :

1. Vérifier que des mots ont été fournis en arguments (au moins un mot après le nom du programme)
2. Pour chaque mot fourni, calculer et afficher sa longueur
3. Identifier et afficher le mot le plus long et le mot le plus court
4. Compter le nombre total de caractères dans tous les mots (sans compter les espaces)

### Partie 3 : Opérations avancées sur les arguments

Étendez votre programme pour effectuer différentes analyses selon le premier argument fourni :

1. **"count"** : Compte le nombre de mots fournis
2. **"reverse"** : Affiche tous les mots à l'envers
3. **"stats"** : Affiche des statistiques complètes (longueur moyenne, mot le plus long, etc.)

Le programme doit afficher un message d'erreur si la commande n'est pas reconnue.

## Résultat attendu

Votre programme doit fonctionner comme suit lorsqu'il est compilé sous le nom `analyseur` :

```bash
$ ./analyseur
Erreur : Aucun argument fourni.
Usage : ./analyseur <commande> [mots...]

$ ./analyseur count bonjour monde programmation
Nombre d'arguments reçus : 4
Nombre de mots à analyser : 3
Mots : bonjour, monde, programmation

$ ./analyseur reverse chat chien oiseau
Mots inversés :
1. tahc
2. neihc
3. uaesio

$ ./analyseur stats bonjour le monde de la programmation
=== STATISTIQUES ===
Nombre de mots : 6
Mot le plus court : "le" (2 caractères)
Mot le plus long : "programmation" (13 caractères)
Longueur moyenne : 6.33 caractères
Total de caractères : 38
```

## Astuces

- `argc` contient le nombre total d'arguments (nom du programme + arguments fournis)
- `argv[0]` contient toujours le nom du programme
- `argv[1]`, `argv[2]`, etc. contiennent les arguments fournis par l'utilisateur
- Pour comparer deux chaînes caractère par caractère, créez une fonction qui compare chaque caractère jusqu'à `'\0'`
- Pour calculer la longueur d'une chaîne, comptez les caractères jusqu'à rencontrer `'\0'`
- Pour inverser une chaîne, créez un nouveau tableau et copiez les caractères dans l'ordre inverse
- N'oubliez pas de vérifier que vous avez suffisamment d'arguments avant d'y accéder

## Pour aller plus loin

Si vous souhaitez approfondir ce projet, vous pourriez explorer :

- L'implémentation d'un tri alphabétique des mots fournis

---

_Les arguments de ligne de commande sont un moyen puissant de rendre vos programmes flexibles et réutilisables. Cette approche est utilisée par la plupart des outils système et utilitaires de développement._
