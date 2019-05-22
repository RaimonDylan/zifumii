# Zyfumi



![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/ZIFOUZIFOU.gif)






---


![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/AnimatedGif.gif)


----


![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/SHIFU1.jpg)



--- 




### Introduction
![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/SHIFU3.jpg)
Zyfumi est un jeu vidéo en deux dimensions réalisé sur UnityEngine dont le bût est de jouer au Shi-fu-mi d'une façon différente.
Zyfumi se déroule dans une arène de combat, l'utilisateur joue un personnage combattant un autre personnage *Intelligence Artifitielle* et possède 3 variantes de sorts disponibles : 
![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/SHIFU2.jpg)
* Épée
* Saisir
* Bouclier

### Conception détaillée
* Schématisation sous forme de maquettes de ce qui est attendu et la représentation faite pour Zyfumi :

![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/conception.jpeg)



* Le personnage gagne de l'expérience et à chaque palier ( niveau 1 a un palier de 100xp )  et chaque niveau fait gagner un point de compétence permettant au joueur de se spécialiser dans une des 3 variantes de sorts 

![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/XP.gif)



* Ce qui donne sous Machination

![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/GAMEPALY.gif)



* Diagramme des cas d'utilisations non exhaustifs : 

![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/use.png)

### Spécification des besoins
* Zyfumi doit être basé sur le système du [Shi-fu-mi](https://www.google.com) *Pierre-papier-ciseaux est un jeu effectué avec les mains et opposant un ou plusieurs joueurs.*
* Zyfumi est un jeu au tour par tour
* Dans Zyfumi, le joueur joue contre une Intelligence Artifitielle
* Dans Zyfumi, cette intelligence artifitielle donne la possibilité au joueur de développer des stratégies
* Dans Zyfumi, l'intelligence artifitielle gère la progession de la difficulté
* Dans Zyfumi, le joueur doit penser que le jeu est juste 
* Dans Zyfumi, le joueur doit trouver une interface attrayante
* Dans Zyfumi, de multiples intelligences artifitielles peuvent être implémentées

## Architecture logicielle 

![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/Diagramme%20de%20classe.PNG)

* GameManager 
```Est la classe qui permet de gérer la partie, comme les lancements de partie, les choix de personnage, d'inventaire etc```
* Player
```Est la classe Personnage qui permet de gérer le ou les personages, les différents choix de caractéristiques etc```
* Skill
```Est la classe qui permer de gérer les différents Talents du personnage, les attaques, les boucliers, les saisies, etc ```
* Experience
```Est la classe qui s'occupe de la gestion de l'expérience acquise du personnage```

* MixedCOntroller
```Est la classe qui permet de gérer la bande sonore du jeu```

* Tower
```Est la classe de level design permettant de gérer la progression du joueur```




Exemple de variables 
```c#
    private float experience = 0; // Expérience initialisée à 0 de base
    private int niveau = 1; // Niveau initialisé à 1 de base
    private int xpBase = 100; // Expérience de base d'un joueur
    private int xpIncr = 50; // Incrémentation fixe
    private Player myPlayer; // Le joueur lié à l'expérience 
    private SimpleHealthBar expBar; // La barre de vie implémentée sur la scène

    public float Experience { get => experience; set => experience = value; }
    public int Niveau { get => niveau; set => niveau = value; }
    public int XpBase { get => xpBase; set => xpBase = value; }
    public int XpIncr { get => xpIncr; set => xpIncr = value; }
    public Player MyPlayer { get => myPlayer; set => myPlayer = value; }
    public SimpleHealthBar ExpBar { get => expBar; set => expBar = value; }
    
    
    

```

```c#

    // Augmente de 1 la valeur de stage Now
    // Sauvegarde de l'étage si on passe un boss
    public void stageUp()
    {
        if(stageNow%5 == 0) // Si on a battu le boss
        {
            saveStage = stageNow;
            // Sauvegarde des données 
            PlayerPrefs.SetInt("saveStage", saveStage);
            PlayerPrefs.Save();
        }
        // Incrémentation de l'étage si on est pas à l'étage maximum
        stageNow = (stageNow + 1 <= stageMax) ? stageNow + 1 : stageMax;
    }
```

## Spécification du code, règles de codage
* Les commentaires doivent être clairs et concis
* Les identificateurs doivent être lisibles et licites pour des raisons de concisions, *par exemple, isLimited est mieux que limit* 
* Pas de traits d'union ou de soulignement dans les variables
* Pas de caractères spéciaux ni de numéros dans les noms de variables 
* Pas d'utilisation d'abréviations non licites, *getWidth et non gw* 
* Utilisation obligatoire de noms sémantiques : *getLength() et non getInt* pour récupérer une taille en int

## Compte rendu d'éxecution de test et fiches d'anomalies

fonction settingsBoss() => 
![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/SUCCESS.gif)

fonction resetLevel() => 
![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/ERR.gif)


Après correction => 
![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/SUCCESS.gif)




Exemple de fiche d'anomalie qui est remontée 
![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/ANO.PNG)

Avant ça manquait de dynamisme

![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/SHIFU2.jpg)

Après travail sur l'intégration d'animations, d'effets spéciaux et de petits bruits d'interaction

![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/AnimatedGif.gif)

![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/SUCCESS.gif)


## Suivi du déroulement de projet
* Taiga du projet 
* la collaboration entre les membres de l’équipe pour développer les initiatives, récolter plus d’idées
### Détails sprint 0
![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/Sprint0.PNG)
### Détails sprint 1
![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/Sprint1.PNG)
### versionning du projet sur Unity
![](https://raw.githubusercontent.com/RaimonDylan/zifumii/master/photos/collab.PNG)
