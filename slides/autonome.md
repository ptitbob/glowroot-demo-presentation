### mode autonome

expose un web serveur sur le port 4000

*En dev, sans mode debug (pleine vitesse)*

*En integ, lors des validations MOE pour remonter les hotspots*<!-- .element class="fragment fade-out" -->

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

-@@-

![](images/0928-avise-01-02.JPG)

-@@-

![](images/0928-avise-01-03.JPG)

-@@-

![](images/0928-avise-01-04.JPG)

-@@-

![](images/0928-avise-01-05.JPG)

-@@-

![](images/0928-avise-01-06-a.JPG)

-@@-

![](images/0928-avise-01-06-b.JPG)

-@@-

![](images/0928-avise-01-06-c.JPG)

-@@-

![](images/0928-avise-01-06-d.JPG)
