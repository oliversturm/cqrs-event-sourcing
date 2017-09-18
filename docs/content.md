## Microservices

A Complete Picture


> Oliver Sturm &bull; @olivers &bull; oliver@oliversturm.com

<img src="devexpress.png" class="plain" style="background:transparent;opacity:0.7;" alt="DevExpress">&nbsp;&nbsp;<img src="mvp.png" class="plain" style="background:transparent;opacity:0.4;" alt="MVP">

---

## Oliver Sturm

* Training Director at DevExpress
* Consultant, trainer, author, software architect and developer for over 25 years
* Microsoft C# MVP

* Contact: oliver@oliversturm.com

---

## Agenda

* Service structure 
  * A look at a microservices architecture
* Communication
  * Considerations pro and con frameworks
  * Working with individual services
* Packaging/deployment
  * Developer concerns
  * Real-world deployment with AWS
* Developer stuff
  * Debugging

---

## Service structure

My demo application system has at least seven services:

<img src="services1.svg" style="background: white;" alt="Services">

^

## Querying data

<img src="query.svg" style="background: white;" alt="Querying data">

^

## Creating a new row

<img src="create-new-row.svg" style="background: white;" alt="Creating a new row">

^

## Service structure

More advanced architecture has more services:

<img src="services2.svg" style="background: white;" alt="More Services">

^

## Querying data with CQRS/ES

<img src="es-query.svg" style="background: white;" alt="Querying data with CQRS/Event Sourcing">

^

## Creating a new row with CQRS/ES

<img src="es-create-new-row.svg" style="background: white;" alt="Creating a new row with CQRS/Event Sourcing">


---

## Communication

* Structural question: who talks to who?
* Implementation question: how does the talking work?

^

## Direct Communication

<img src="communication-direct.svg" style="background: white;" alt="Direct Communication">

^

## Using a Broker

<img src="communication-broker.svg" style="background: white;" alt="Using a broker">

^

## How does the talking work?

* Each service could be a web service. REST? Proprietary? Your choice.
* Each service could be implemented to talk to the broker exclusively.
* Libraries exist that implement communication.

---

## Packaging/deployment

* Running lots of services manually isn't much fun
  * Consider automation
* Services may need individual runtime environments
* Container systems to the rescue!

---

## Debugging

* Granularity of services makes it easier to test
* Services can be debugged as individual entities
* Services **are** individual entities -- best regards from functional programming!

---

## Sources

* This presentation: 
  * https://oliversturm.github.io/microservices-complete-picture
  * Deprettified content in pdf format: https://oliversturm.github.io/microservices-complete-picture/slidecontent.pdf

* Demo code:
  * https://github.com/oliversturm/cqrs-grid-demo (check *master* and *event-sourcing* branches)

---

## Thank You

Please feel free to contact me about the content anytime.

oliver@oliversturm.com
