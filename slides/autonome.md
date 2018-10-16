### mode autonome

expose un web serveur sur le port 4000

*En dev, sans mode debug (pleine vitesse)*

*En integ, lors des validations MOE pour remonter les hotspots*<!-- .element class="fragment fade-out" -->

notes:

En integ, mieux vaux privilégier le mode connecté.

-@@-

### mode autonome

***En parametre de la JVM***

```
java -javaagent:path/to/glowroot.jar -jar superApp.jar
```

![](images/intellij-javaagent.png)<!-- .element class="fragment" -->

notes:
sous Intellij, exemple de configuration de d'execution

java -javaagent:../../glowroot/glowroot.jar -jar people-0.0.1-SNAPSHOT.jar

aide glowroot : [](https://github.com/glowroot/glowroot/wiki/Where-are-my-application-server%27s-JVM-args%3F#spring-boot)

-@@-

# Démo

-@-

## Et dans la vrai vie ?

-@@-

## Glowroot & AVISé

-@@-

![](images/0928-avise-01.JPG)

notes:

Vue générale

A noter, le pic JDBC

-@@-

![](images/0928-avise-01-02.JPG)

notes:

Listes des requetes les + longues

-@@-

![](images/0928-avise-01-03.JPG)

notes:

et les slowtrace (overhead < 10 ms pour la démo)

-@@-

![](images/0928-avise-01-04.JPG)

notes:

Les requêtes

La requête INFNITE qui prends pas mal de temps

A remarquer, temps total & moyen

-@@-

![](images/0928-avise-01-05.JPG)

notes:

les appel HTTP

A remarquer, temps total & moyen

-@@-

![](images/0928-avise-01-06-a.JPG)

notes:

un appel en détail

permet de voi le différent temps totaux

Cout du logging

-@@-

![](images/0928-avise-01-06-b.JPG)

notes:

Le détail des différentes étapes

Permet de visualiser sans ambiguité les SPOF

-@@-

![](images/0928-avise-01-06-c.JPG)

notes:

Visualisation d'un requête JDBC avec les paramètres

-@@-

![](images/0928-avise-01-06-d.JPG)

notes:

L'ensemble des requêtes SQL
