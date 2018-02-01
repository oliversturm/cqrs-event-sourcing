title: CQRS and Event Sourcing
subtitle:
class: animation-fade
layout: true

<!-- This slide will serve as the base layout for all your slides -->

.bottom-bar[
{{title}}
]

---

class: impact

# {{title}}

## {{subtitle}}

.title-oli[
Oliver Sturm &bull; @olivers &bull; oliver@oliversturm.com
]

.title-logo[
<img src="template/devexpress.png" id="devexpress" alt="DevExpress"><img src="template/mvp.png" id="mvp" alt="MVP">
]

---

## Oliver Sturm

* Training Director at DevExpress
* Consultant, trainer, author, software architect and developer for over 25 years
* Microsoft C# MVP

* Contact: oliver@oliversturm.com

---

## Agenda

* CQRS - Why? When? How?
  * Sometimes there are choices
  * Sometimes the decision is natural
  * Consequences
* Event Sourcing
  * Again: Why? When? How?
* Eventual consistency

---

## Data Access, "Traditionally"

```cs
ImportantData editObject;

protected override void OnInit(EventArgs e) {
  editObject = LoadEditObject();
  control.DataSource = editObject;
  control.DataBind();
}

protected void Page_Load(object sender, EventArgs e) {
  if (IsPostBack) {
    MergeEditorChanges(editObject);
    SaveObject(editObject);
  } ...
}
```

---

## Data Access, "Traditionally"

1. Objects are loaded into memory
1. Data is shown in UI
1. Changes are submitted
1. Loaded objects are modified
1. Local change detection optimizes process of persistence

---

## CQRS &mdash; Why?

* Because "loading data for visualization" doesn't have the same requirements as "persisting data"
* Because one loading process can be different from another
* Because one persistence process can be different from another
* Because we can save time in "page cycle" environments
* Because separate execution paths are easier to test and maintain

---

## CQRS &mdash; When?

* Almost anytime!
* Typical doubts:
  * Pure client app &mdash; do I benefit?
  * More complex structure == more complicated maintenance work?
  * But what about ORM?

---

## CQRS &mdash; How?

* Separate execution paths for data reading and writing
* Consider modeling changes as commands
* Consider efficient data models to support business operations

---

## Querying Data

.svg-light[
![Querying Data](query.svg)
]

---

## Creating a New Row

.svg-light[
![Creating a New Row](create-new-row.svg)
]

---

## Event Sourcing

* Starting from _command_ idea
  * Primarily persist events, instead of data
  * Append-only event log
  * Derive entity state at any time, for any point in time
* Entities/Aggregates/domain objects
* Optimizations: snapshots, projections, (persistent) read models

---

## Event Sourcing &mdash; Why?

* Events describe what the system was asked to do, any technical consequences of an event are not set in stone. Fantastic for long-term maintenance!
* Clean, extensible and scalable structure, supporting strict separations of concerns.
* Event Storming &mdash; very practical planning method

---

## Event Sourcing &mdash; When?

* Tempting pattern for many applications, but with structural consequences
  * In-process? Possible...

---

## Event Sourcing &mdash; How?

* Any service can receive commands
* Raising domain events across service boundaries requires communication infrastructure
* Persisting events and possibly read models requires a persistence layer
* Structural maintenance of aggregates and projections is a bit fiddly
* Recommended: use libraries existing for all platforms

---

## Creating a New Row with CQRS/ES

.svg-light[
![Creating a New Row with CQRS/Event Sourcing](es-create-new-row.svg)
]

---

## Querying Data with CQRS/ES

.svg-light[
![Querying Data with CQRS/Event Sourcing](es-query.svg)
]

---

## Eventual Consistency

> Consistency is over-rated (Greg Young, Mr CQRS)

* General issue in distributed systems - CAP theorem
* Eventual consistency exists in the real world. Starbucks?
* How eventual are things in your system?
* Business logic needs to deal with issues resulting from eventual consistency
  * Compensation
  * Special programming tactics
  * Check this out: http://queue.acm.org/detail.cfm?id=2462076

---

## Sources

* This presentation:

  * https://oliversturm.github.io/cqrs-event-sourcing
  * Deprettified content in pdf format: https://oliversturm.github.io/cqrs-event-sourcing/slidecontent.pdf

* Demo code:

  * https://github.com/oliversturm/cqrs-grid-demo (check _event-sourcing_ branch)

* Talk to Seneca

  * https://github.com/oliversturm/talk-to-seneca

---

## Thank You

Please feel free to contact me about the content anytime.

oliver@oliversturm.com
