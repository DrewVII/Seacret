WVII
7wanderer
Ne pas déranger

Jawednatsugo — Hier à 23:12
je suis entrain de faire le rapport la
WVII — Hier à 23:21
J’te fais ça demain ou en rentrant
Jawednatsugo — Aujourd’hui à 01:37
mais demain faut saigner le bail eft
Demain : 
Salaire des employés a mettre en place
Le brouillard
Le Menu Principal avec la sauvegarde
Acheter les améliorations pour les serveurs et les cuisiniers
Musique du jeu
Jawednatsugo — Aujourd’hui à 01:45
demain soyez a l'affut on reste en voc faut travailler toute la journée non stop
et des qu'on a la version finale
je ferais la java doc
c pas obligatoire mais faut manger un max de points
WVII — Aujourd’hui à 10:50
Vous me dites quand ça se co
Au pire venez à la fac
Vers 13/14h
WVII — Aujourd’hui à 11:00
En 3h on finit
WVII — Aujourd’hui à 17:23
@Jawednatsugo
avec chatgpt
package gui;

import java.awt.BorderLayout;
import java.awt.Container;
import java.awt.Dimension;
import java.awt.event.KeyEvent;
Afficher plus
message.txt
5 Ko
demande pourquoi InfoZone ne s'actualise pas ici
Pourquoi les differentes informations restent fixes malgré l'actualisation constante
Une fois réglé
Le jeu sera fini en 2h MAX
je pèse mes mots
WVII — Aujourd’hui à 19:15
public void saveGame() {
            try {
                BufferedWriter writerArg = new BufferedWriter(new FileWriter(argentFile));
                BufferedWriter writerRep = new BufferedWriter(new FileWriter(repFile));
                BufferedWriter writerLvl = new BufferedWriter(new FileWriter(levelFile));

                writerArg.write(argent);
                writerRep.write(reputation);
                writerLvl.write(lvlRestaurant);

                writerArg.close();
                writerRep.close();
                writerLvl.close();
            }
            catch(NumberFormatException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            } catch (IOException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            }
        }

        public void loadGame() {
            try {
                BufferedReader readerArg = new BufferedReader(new FileReader(argentFile));
                BufferedReader readerRep = new BufferedReader(new FileReader(repFile));
                BufferedReader readerLvl = new BufferedReader(new FileReader(levelFile));

                argent = Integer.parseInt(readerArg.readLine());
                reputation = Integer.parseInt(readerRep.readLine());
                lvlRestaurant = Integer.parseInt(readerLvl.readLine());

                readerArg.close();
                readerRep.close();
                readerLvl.close();
            }
            catch(NumberFormatException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            } catch (IOException e) {
                // TODO Auto-generated catch block
                e.printStackTrace();
            }
        }

        public void newGame() {
            argent = 1000;
            reputation = 1;
            lvlRestaurant = 1;
        }
private String argentFile;
    private String repFile;
    private String levelFile;

    public Player(int argent, int depenses, int benefices, int lvlRestaurant, Menu menu, List<Serveur> serveurs,
            List<Cuisinier> cuisiniers, List<Table> tables,Stock stock, List<Chaise> chaises, int reputation) {
        String argentFile = "argent.txt";
        String repFile = "rep.txt";
        String levelFile = "level.txt";
WVII — Aujourd’hui à 19:25
    private class ShowInfo implements ActionListener {
        public void actionPerformed(ActionEvent event) {
            JOptionPane.showMessageDialog(null, "Temps restant avant la fin : " + manager.getJourneyTime(), "Jour "+manager.getCalendrier().getJour(), JOptionPane.INFORMATION_MESSAGE);
            option3 = JOptionPane.showOptionDialog(null, 
                    "Voulez-vous sauvegarder?", 
                    "Point de sauvegarde", 
                    JOptionPane.YES_NO_CANCEL_OPTION,
                    JOptionPane.PLAIN_MESSAGE,
                    null, 
                    options4, 
                    null);
            
            switch(option3) {
                case 1:
                    if(manager.getPlayer().upgradeRestaurantLvl2() == true) {
                        manager.getPlayer().upgradeRestaurantLvl2();
                    }
                    else {
                        JOptionPane.showMessageDialog(null, "Les conditions ne sont pas encore rencontrées", "Erreur", JOptionPane.ERROR_MESSAGE);
                    }
                ;
                
                case 2:
                    if(manager.getPlayer().upgradeRestaurantLvl3() == true) {
                        manager.getPlayer().upgradeRestaurantLvl3();
                    }
                    else {
                        JOptionPane.showMessageDialog(null, "Les conditions ne sont pas encore rencontrées", "Erreur", JOptionPane.ERROR_MESSAGE);
                    }
                ;
                
                default:
                    System.out.println("Pass");
            }
        }
    }
package gui;

import java.awt.BorderLayout;
import java.awt.CardLayout;
import java.awt.FlowLayout;
import java.awt.Color;
import java.awt.Font;
import java.awt.GridLayout;
import java.awt.Image;
import java.awt.Insets;
import java.awt.event.*;
import java.awt.image.BufferedImage;
import java.io.FileInputStream;

import javax.imageio.ImageIO;
import javax.swing.ImageIcon;
import javax.swing.JButton;
import javax.swing.JOptionPane;
import javax.swing.JPanel;

import engine.menu.Ingredient;
import engine.process.MobileElementManager;

public class ActionZone extends JPanel {
    private static final long serialVersionUID = 1L;
    
    private JButton staff;
    private JButton stock;
    private JButton restaurant;
    private JButton info;
    
    private ShowStaff staffShower;
    private ShowStock stockShower;
    private ShowClient clientShower;
    private ShowInfo infoShower;
    
    private int option2;
    private int option3;
    
    private BufferedImage sun;
    
    private CardLayout cardLayout;
    
    private Object[] options1 = {"Fermer", "Niveau 1", "Niveau 2"};
    private Object[] options4 = {"Oui", "Non"};
// A completer 
private class ShowStock implements ActionListener {
    public void actionPerformed(ActionEvent event) {
        StringBuilder stockInfo = new StringBuilder();
        for (Ingredient ingredient : manager.getMenuManager().getListeIngredient().getIngredientList()) {
            int quantite = manager.getStock().getQuantite(ingredient);
Afficher plus
v.txt
3 Ko
Jawednatsugo — Aujourd’hui à 19:34
@MelonPastèque
envoie ton truc
pour enlever les nuages
WVII — Aujourd’hui à 19:36
    private class ShowInfo implements ActionListener {
        public void actionPerformed(ActionEvent event) {
            JOptionPane.showMessageDialog(null, "Temps restant avant la fin : " + manager.getJourneyTime(), "Jour "+manager.getCalendrier().getJour(), JOptionPane.INFORMATION_MESSAGE);
            option3 = JOptionPane.showOptionDialog(null, 
                    "Voulez-vous sauvegarder?", 
                    "Point de sauvegarde", 
                    JOptionPane.YES_NO_CANCEL_OPTION,
                    JOptionPane.PLAIN_MESSAGE,
                    null, 
                    options4, 
                    null);
            
            switch(option3) {
                case 1:
                    manager.getPlayer().saveGame();
                break;
                case 2:
                    System.out.println("p");
                default:
                    System.out.println("Pass");
                    break;
            }
        }
    }
MelonPastèque — Aujourd’hui à 19:36
dans
Type de fichier joint : archive
V1.rar
6.98 MB
Jawednatsugo — Aujourd’hui à 19:37
c la V1 ca
gennre
MelonPastèque — Aujourd’hui à 19:37
ma dernier version
Jawednatsugo — Aujourd’hui à 19:37
la toute premiere version
lance
MelonPastèque — Aujourd’hui à 19:37
nan
Jawednatsugo — Aujourd’hui à 19:37
j'ai copié collé
MelonPastèque — Aujourd’hui à 19:37
c'est ma dernier version
ça  marche ? @Jawednatsugo
Jawednatsugo — Aujourd’hui à 19:59
Type de fichier joint : archive
resto.rar
4.71 MB
Jawednatsugo — Aujourd’hui à 21:00
il me manque que le src final est on a finis
j'ai fait
le rapport
+ latex
+ readme
WVII — Aujourd’hui à 21:29
Dans 10 min
Rassemblement à la avengers
J’vais jamais être aussi sérieux de ma vie
Soyez témoin
WVII — Aujourd’hui à 21:40
go
MelonPastèque — Aujourd’hui à 21:41
dans 15 min
WVII — Aujourd’hui à 22:03
package player;

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
Afficher plus
message.txt
7 Ko
package engine.mobile;

import engine.map.Block;

public class Cuisinier extends Staff {
    private int niveau;

    public Cuisinier(int argent, int niveau, Block position) {
        super(argent, position);
        this.niveau = niveau;
    }

    public int getNiveau() {
        return niveau;
    }

    public void setNiveau(int niveau) {
        this.niveau = niveau;
    }

    public void ameliorationNiveau2() {
        setNiveau(2);
    }

    public void ameliorationNiveau3() {
        setNiveau(3);
    }
}
package gui;

import java.awt.BorderLayout;
import java.awt.CardLayout;
import java.awt.FlowLayout;
import java.awt.Color;
Afficher plus
message.txt
10 Ko
@MelonPastèque besoin de toi stp
Jawednatsugo — Aujourd’hui à 22:18
@MelonPastèque
je t'invoque
MelonPastèque — Aujourd’hui à 22:39
public void addServeur2() {
        serveurs.add(serveur2);
    }
    public void addServeur3() {
        serveurs.add(new Serveur(1,1,posServeur3));
    }
private Block posServeur2 = new Block(4,7);
    private Block posServeur3 = new Block(11,7);

    private Serveur serveur2;
manager.addServeur2();
manager.addServeur3();
Jawednatsugo — Aujourd’hui à 22:50
Type de fichier joint : acrobat
Restaurant_2024.pdf
804.01 KB
Type de fichier joint : document
Rapport_Projet_TransitIDF.docx
200.96 KB
![Logo de Sea-cret de la Mer](https://i.ibb.co/6RZc3QN/zhtml-Black.jpg)

# Sea-cret de la Mer

Bienvenue sur **Sea-cret de la Mer**, votre jeu de gestion de restaurant.
Afficher plus
readme.txt
1 Ko
Contents de te voir, 
Ethwynn
.
 — Aujourd’hui à 23:47
WVII — Aujourd’hui à 23:48
https://github.com/DrewVII/Seacret
GitHub
GitHub - DrewVII/Seacret
Contribute to DrewVII/Seacret development by creating an account on GitHub.
GitHub - DrewVII/Seacret
Jawednatsugo — Aujourd’hui à 23:48
![Logo de Sea-cret de la Mer](https://i.ibb.co/6RZc3QN/zhtml-Black.jpg)

# Sea-cret de la Mer

Bienvenue sur **Sea-cret de la Mer**, votre jeu de gestion de restaurant.
Afficher plus
readme.txt
1 Ko
WVII — Aujourd’hui à 23:49
Image
Image
Jawednatsugo — Aujourd’hui à 23:50
![Logo de Sea-cret de la Mer](https://media.discordapp.net/attachments/1200518585949356064/1234622681412796457/seacret_de_la_mer.png?ex=66316779&is=663015f9&hm=d76ea399f94317e79be0a80b990b3024aa98ddb8791096cc04edfebdb52b7e33&=&format=webp&quality=lossless&width=669&height=676)

# Sea-cret de la Mer

Bienvenue sur **Sea-cret de la Mer**, votre jeu de gestion de restaurant.
Afficher plus
readme.txt
2 Ko
﻿
![Logo de Sea-cret de la Mer](https://media.discordapp.net/attachments/1200518585949356064/1234622681412796457/seacret_de_la_mer.png?ex=66316779&is=663015f9&hm=d76ea399f94317e79be0a80b990b3024aa98ddb8791096cc04edfebdb52b7e33&=&format=webp&quality=lossless&width=669&height=676)

# Sea-cret de la Mer

Bienvenue sur **Sea-cret de la Mer**, votre jeu de gestion de restaurant.

## Guide d'utilisation

- Lancez votre eclipse et créer un nouveau projet Java. 

- Copiez collez les  fichiers du répertoire `src` dans votre projet Java.

- Allez dans le package "test" et  ouvrez le fichier "TestGame.java".

## Support

En cas de questions ou de problèmes avec l'utilisation du jeu, n'hésitez pas à contacter notre support technique via email à zijawed984@gmail.com.

## Auteurs

- **CHEBALLAH Jawed**
- **MAKUISA Andrew**
- **REY Timothé**

## But du Projet

Ce projet a été développé dans le cadre du cours de Génie Logiciel de L2 Informatique à l'Université de Cergy.

## URL Utilisées

- [GitHUB](https://github.com/DrewVII/Seacret)

readme.txt
2 Ko
