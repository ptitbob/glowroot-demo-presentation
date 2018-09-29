## Je suis glowroot

![](images/iamroot.jpg)

-@-

## Glowroot

https://glowroot.org/

**APM**

*OpenSource (ASL 2.0)*

-@@-

### APM, c'est quoi cette bête là ?

**Application Performance Management**

*Outil de mesure des performance d'une application*

-@@-

### On parle de quoi ?

Terme principal : TPS (Transaction/s)

-@@-

## C'est quoi un APM ?

* en prod : *Suivi des executions, SLA*<!-- .element class="fragment" -->
* en recette : *suivi des executions, reductio des WTF*<!-- .element class="fragment" -->
* en integ : *Un outils pour eviter les WTF*<!-- .element class="fragment" -->
* en dev : *Run à donf !*<!-- .element class="fragment" -->

notes:
SLA : Service Level Agreement

-@@-

On en a un au SIHM

Dynatrace <!-- .element class="fragment" -->

Pas sur nos postes, ni en integ<!-- .element class="fragment" style="color: red;" -->

***Blackbelt***<!-- .element class="fragment" -->

-@@-

## Alors glowroot c'est quoi ?

Agent Java

Deux modes :
*autonome*<!-- .element class="fragment" -->
ou
*connecté*<!-- .element class="fragment" -->

overhead marginal < 10 µs<!-- .element class="fragment" -->

mémoire : ~ 2 ko<!-- .element class="fragment" -->

[github.com/glowroot/glowroot-benchmark](https://github.com/glowroot/glowroot-benchmark)<!-- .element class="fragment" -->

-@-

### mode autonome

expose un web serveur sur le port 4000

*En dev, sans mode debug (pleine vitesse)*

*En integ, lors des validations MOE pour remonter les hotspots*

-@-

### mode autonome

***En parametre de la JVM***

```
java -javaagent:path/to/glowroot.jar -jar superApp.jar
```

![](images/intellij-javaagent.png)<!-- .element class="fragment" -->

notes:
sous Intellij, exemple de configuration de d'execution

aide glowroot : [](https://github.com/glowroot/glowroot/wiki/Where-are-my-application-server%27s-JVM-args%3F#spring-boot)

