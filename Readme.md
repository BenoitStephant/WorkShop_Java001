# Workshop Java 001

![N|Solid](https://upload.wikimedia.org/wikipedia/fr/2/2e/Java_Logo.svg)

Avant de commencer ce Workshop il faut installer certaines choses 😁.

# Installation 🔨

- IntelliJ IDEA:
Contrairement au C vous aurez besoin d'un IDE pour pouvoir lancer vos programmes Java. À partir de 2 fichiers contenant du code Java le lancement devient compliqué sans IDE 😅.
L'IDE le plus développé en Java est IntelliJ vous pouvez vous rendre à cette adresse: https://www.jetbrains.com/fr-fr/idea/download/#section=mac et télécharger la version `community`, elle est gratuite et sufisante pour la suite du workshop.


## EX00: La premiere fois

Dans cette exercise il faut ce familiariser avec votre environnement de développement.

Vous pouvez déjà lancer votre IDE IntellidJ, vous allez arriver sur cette page.
![N|Solid](/assets/intelliJ_home.png)
Nous allons utiliser le même projet pour chaque exercise. Les exercises ne sont pas indépendant, pour pouvoir faire l'ex01 il faut avoir réussi l'ex00.
Pour pouvoir créer notre premier projet appuyez sur `Create New Project`.

Vous arrivez ensuite sur cette page:
![N|Solid](/assets/project_first_step.png)
Par défault la java est déjà selectionné en version 1.8, vous devez juste cliquer sur `Next`. Sur la page suivante cliquez également sur `Next`.

Vous devez arriver normalement sur cette page si vous êtes pas trop nul 😜:

![N|Solid](/assets/project_name.png)

J'ai mis Workshop_Java001 en nom de projet, vous pouvez mettre ce que vous voulez. Vous pouvez cliquer sur `Finish`. Notre projet est enfin crée 😏.

![N|Solid](/assets/IDE.png)

Sur cette magnifique interface vous devez tout d'abord créer votre classe Main, cette classe sera la prémière classe construite lors du lancement c'est l'équivalent du main en C. Pour la créer cliquez sur "Add Configuration" tout en haut.


![N|Solid](/assets/config.png)
Une fois arrivé sur cette page cliquer sur "Templates", puis "Application". Dans l'input texte "Main class" vous devez Rentrer le nom de votre Main Class. Appelez la comme vous voulez, mais gardez bien dans votre tête que tous commencera dans cette classe pour vos premier pas en Java. Une fois votre Main classe définie il faut la créer, cherchez le dossier src à l'aide de la barre à gauche, ca devrais pas être trop dure vous inquiétez pas 😌.

Si tu es entrain de lire cette phrase c'est que tu as réussi à trouver le dossier source, dans ce dossier tu pourras y mettre tes classes dont ta main Class. E parlant de main classe tu peux la créer en faisant un clique droit sur le dossier src et en sélectionnant "New" et "Java Class". Ensuite vous devez nommer votre classe. Nommez la du même nom que vous avez rentré en tant que MainClass.

Une fois votre première classe créer du code Java s'affiche enfin 🤩 enfin un déclaration de classe 😅.
![N|Solid](/assets/home_IDE.png)

## EX01: Hello world !!

Dans cette exercie le but est d'afficher dans la console "Hello world !!\n". Je vais vous laisser chercher par vous même comment pouvoir afficher cette première phrase. Le seul indice que je peux vous donner c'est que la flèche en haut à droite sert à lancer votre programme ca pourrait être d'une grande utilité 😁.

Vous devriez obtenir cela:
![N|Solid](/assets/ex01.png)

## EX02: Création de notre première classe

Maintenant que vous avez affiché vos premier mots dans la console nous allons maintenant créer une classe nommée `Character` (par convention les noms de classe commencent toujours par une majuscule). Pour commencer vous allez devoir créer dans votre IDE une nouvelle classe Java. Je vous laisse chercher comment la créer, c'est pas trés compliqué je vous rassure 😉.

En java et dans les languages objets en générale les objets sont initialisé via des constructeur. Comme son nom l'indique c'est lui qui va construire l'objet et initialiser ces variables. Ce constructeur devra être nommé du même de nom de la classe.

Dans une classe plusieurs chose sont présente:
- des méthodes
- des attributs

Pour le moment nous allons voir que les types `private` et `public`. Pour faire simple une méthode ou un attributs `private` ne pourrat être éxecuté ou lire à l'extérieur de la classe en tant que telle. Pour les attributs, Nous allons utiliser des `getters` et `setter`. Vous l'avez peut-être devinez mais les `getters`vont permettre de récupérer le contenu de la variable `private` présent dans une classe et le `setter` de lui assigner une valeur.

Je vous laisse faire un copier-coller la classe ci-dessous, elle sera à compléter au fur et à mesure des exercises:
```java
public class Character {

    //constructor of class Character
    public Character(final String name, final String team) {

    }

    // display this string: "Hi, I'm {Name} from {Team} !!\n"
    public void sayHello() {

    }

    // return value of local variable _name
    public String getName() {

    }

    // return value of local variable _team
    public String getTeam() {

    }

    // set the value of _name local variable
    public void setName(final String name) {

    }

    // set the value of _team local variable
    public void setTeam(final String team) {

    }

    private String _name;
    private String _team;
}
```

Pour accédes à une variable ou une méthode présente dans la classe on utilise le keyword `this` par exemple pour accéder à la variable _team présent dans la classe au-dessus on peut faire `this._team`. Au passage vous aurez peut-être remarqué que les variables présente dans la classe ont un `_` au début. Dans tous les languages qui utilise les types `private` et `public` ont utilise par convention un `_` au début pour les variables `private.

Une fois que vous avez copié-collé la classe dans votre IDE vous pouvez commencez par la compléter, aidez-vous des commentaires présent au dessus des fonctions cela pourrais vous aider pour réalisation le corps des méthodes.

Je vous laisse un main de test et l'output que vous devez obtenir ensuite:
```java
    public static void main(String[] args) {
        Character c = new Character("Yoda", "Jedi");

        c.sayHello();
        c.setName("Dark Vador");
        c.setTeam("Sith");
        c.sayHello();
        System.out.println("Current name: " + c.getName());
        System.out.println("Current team: " + c.getTeam());
    }
````
![N|Solid](/assets/ex02.png)

## EX03: Héritage

Dans cette exercise nous allons voir un concept essentiel à la programmation orientée objet. L'héritage permet à la classe qui hérite d'utiliser les méthodes et attributs public (ou protected mais nous allons pas aborder ce type je vous laisse vous renseignez tout seul de votre coté) présent dans cette classe. Pour notre classe Character nous aurront 2 classes qui hérite de celle-ci. Une nommée `DarkVador`et une autre nommée `Yoda`. Les 2 classes ont tous les deux besoin de la classe character, effectivement DarkVador et Yoda sont des personnages du film Star Wars et bien dans notre projet c'est la même chose ils appartiennent aussi à la classe Character.
La dernière chose à comprendre pour l'héritage c'est lors de la construction. Effectivement une classe qui hérite d'une classe va devoir appeler le constructeur de ca classe supérieur. Je vous laisse chercher comment faire pour qu'une classe hérite d'une autre ainsi que pour `super` bien appeler le constructeur de la classe supérieur 😜.

Lorsque que vous allez créer vos 2 nouvelles classe vous ne devez créer aucune méthodes 🧐. Notre utiliserons les méthodes de la classe `Character` obtenu grâce à l'héritage.

Voici le main de test ainsi que l'output à obtenir:
```java
    public static void main(String[] args) {
        Yoda yoda = new Yoda();
        DarkVador darkVador = new DarkVador();

        yoda.sayHello();
        darkVador.sayHello();
    }
````

![N|Solid](/assets/ex03.png)

## EX04: List et type

Dans cette dernière partie nous allons voir comment déclarer une liste d'élément et lui définir un type.

Voici comment ce déclare une liste:
```java
List<String> list
```

Le type de la liste est `String` c'est à dire que c'est une liste de `String`, pas compliqué non ?
Cette objet `List`contient pleins de méthodes qui vont nous permettre d'effectuer des opérations ou des actions sur elle mêmes.

exemple:
```java
list.add("first");
```

La méthode add permet d'ajouter un élement dans la liste.

Passons maintenant à la pratique et à l'utilisation de l'héritage crée à l'exercise précédent. Vous allez devoir ajouter des amis à nos classes `Yoda` et `Dark Vador`. Pour se faire vous devez créer une liste de Character. Vous devez aussi créer une méthodes `add` et `friendSayHello` dans Character.

Je vous donne pas de nom de classe défini pour les amis vous pouvez mettre ce que vous voulez.
Je vous laisse un main de test et l'output (ATTENTION: il se peut que vos nouvelles classes ne soit pas nommées de la même facon que le mienne vous devez adapter le main afin de prendre vo noms de classe).

```java
    public static void main(String[] args) {
        Yoda yoda = new Yoda();
        DarkVador darkVador = new DarkVador();
        Anakin anakin = new Anakin();
        Palpatin palpatin = new Palpatin();
        DarkMaul darkMaul = new DarkMaul();
        Luke luke = new Luke();

        yoda.addFriends(anakin);
        darkVador.addFriends(palpatin);
        darkVador.addFriends(darkMaul);
        yoda.friendSayHello();
        yoda.addFriends(luke);
        darkVador.friendSayHello();
        yoda.friendSayHello();
    }
```

![N|Solid](/assets/ex04.png)
