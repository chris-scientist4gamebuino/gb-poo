
# SOKOBAN vs POO / Partie 4 : le personnage

v0.0.1

## INTRODUCTION

Dans les parties pr�c�dentes nous avons vu les bases de notre programme, la gestion de la cam�ra et la gestion de l'affichage. Nous allons voir dans cette quatri�me partie la gestion du personnage, ainsi � la fin de cette partie nous serons en mesure de d�placer le personnage (sans contrainte de physique : on pourra traverser les murs par exemple).

Les **pr�-requis** de ce tutoriel sont :
* Avoir une Gamebuino META.
* Avoir fait l'ensemble des ateliers.
* Avoir r�aliser la [partie 1](part_01.MD), la [partie 2](part_02.MD) et la [partie 3](part_03.MD) de ce tutoriel.

Je vous invite � t�l�charger [le code](https://github.com/chris-scientist/gb-poo/archive/v3.0.0.zip) qui est le r�sultat de la troisi�me partie, ceci pour partir sur des bases communes.

## CR�ATION DES BASES

Nous allons dans un premier temps d�finir toutes les m�thodes transverses au d�placement, c'est-�-dire qu'on utilise quand on se d�place dans n'importe quelle direction.

Nous avons besoin d'un moyen d'agir sur la carte, en effet il va falloir d�placer le personnage mais aussi remplacer l'ancienne position du personnage par un sprite. Pour ce faire nous allons �crire un *setter*, il s'agit d'une m�thode qui modifie un attribut. Le setter en question est setTypeOfSprites de la classe MapModel, que voici :

    void MapModel::setTypeOfSprites(const int aXSprites, const int aYSprites, const char aTypeOfSprites) {
        mapOfGame[aYSprites][aXSprites] = aTypeOfSprites;
    }

Nous allons maintenant intervenir dans la classe CharacterModel.

D'abord, il faut cr�er le getter sur la nouvelle position soit la m�thode getNextPos :

    const int * CharacterModel::getNextPos() const {
        return nextPos;
    }

Ensuite, cr�ons le getter sur l'ancien sprites soit la m�thode getOldTypeOfSprites :

    const char CharacterModel::getOldTypeOfSprites() const {
        return oldTypeOfSprites;
    }

Cr�ons le setter sur l'ancien sprites soit la m�thode setOldTypeOfSprites :

    void CharacterModel::setOldTypeOfSprites(const char aOldTypeOfSprites) {
        oldTypeOfSprites = aOldTypeOfSprites;
    }

Cr�ons la m�thode updatePositions, cette m�thode affecte la position suivante (nextPos) � la position courante comme ceci :

    void CharacterModel::updatePositions() {
        x = nextPos[0];
        y = nextPos[1];
    }

Enfin cr�ons la m�thode resetNextPositions, cette m�thode r�initialise la position suivante avec la position courante comme ceci :

    void CharacterModel::resetNextPositions() {
        nextPos[0] = x;
        nextPos[1] = y;
    }

Nous venons d'�crire toutes les m�thodes tranverses au d�placement. 

## SE D�PLACER VERS LE HAUT

*A venir !*

## QUELQUES PISTES POUR LES AUTRES D�PLACEMENTS

*A venir !*

## ASSOCIATION AVEC LA CROIX DIRECTIONNELLE

*A venir !*