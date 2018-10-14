### Instrumentation

-@@-

Informations en plus ?

-@@-

Classes

Méthodes<!-- .element class="fragment" -->

Paramètres<!-- .element class="fragment" -->

Resultat en retour<!-- .element class="fragment" -->

-@@-

### 2 possibilités

Dans le code `Inline`<!-- .element class="fragment" -->

Via l'agent et sa configuration<!-- .element class="fragment" -->

-@-

### Instrumentation - `Inline`

```xml
<dependency>
  <groupId>org.glowroot</groupId>
  <artifactId>glowroot-agent-api</artifactId>
  <version>0.11.1</version>
</dependency>
```

Ajout d'une dependance

-@@-

### `Inline` - annotation

```java
@Instrumentation.Timer("person byId")
public Person getPersonById(final Long personId) throws PersonNotFouncException {
  return personRepository.
    findById(personId).orElseThrow(() -> new PersonNotFouncException(personId));
}
```

-@@-

### `Inline` - annotation

```java
@Instrumentation.TraceEntry(message = "person id: {{0}}",
  timer = "person getId")
public Person getPersonById(final Long personId) throws PersonNotFouncException {
  return personRepository.
    findById(personId).orElseThrow(() -> new PersonNotFouncException(personId));
}
```

-@@-

### `Inline` - annotation

```java
@Instrumentation.TraceEntry(
    message = "person.login: {{0.login}}",
    timer = "person create")
public Person createPerson(Person person) {
  person.setId(null);
  return personRepository.save(person);
}
```

-@@-

### `Inline`

***Problème*** <!-- .element style="color: crimson;" -->

**Adhérence**<!-- .element class="fragment" -->

-@-

### Instrumentation - Configuration

![](images/instrumentation-01.jpeg)<!-- .element class="fragment" -->

-@@-

### Instrumentation - Configuration

Utiliser l'introspection au runtime

*package*<!-- .element class="fragment" -->

*classe*<!-- .element class="fragment" -->

*méthode*<!-- .element class="fragment" -->

-@@-

### Instrumentation - Configuration

![](images/instrumentation-02-01.jpeg)
Toutes les méthodes

-@@-

### Instrumentation - Configuration

![](images/instrumentation-02-03.jpeg)
Toutes une méthode

-@@-

### Instrumentation - Configuration

Deux choix non exclusif, mais...

![](images/instrumentation-02-04.jpeg)<!-- .element class="fragment" -->

-@@-

### Instrumentation - Configuration

Vue d'aggregation

Nom de la transaction

pattern de capture

Nom du timer

*Le tout servi par une aide propre*<!-- .element class="fragment" -->
-@@-

### Instrumentation - Configuration

exportation

```json
{
  "className": "org.shipstone.demo.glowroot.people.web.PeopleEndpoint",
  "methodName": "getById",
  "methodParameterTypes": [
    ".."
  ],
  "captureKind": "transaction",
  "transactionType": "Web",
  "transactionNameTemplate": "personEndpoint",
  "alreadyInTransactionBehavior": "capture-trace-entry",
  "traceEntryMessageTemplate": "{{this}}.{{methodName}}( {{0}} ) => {{_}}",
  "timerName": "personTimer"
}
```

-@@-

# Démo

