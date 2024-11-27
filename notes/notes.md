## 0
alle prosjekter er basert på en behov somen kunde har.(kasje bortsett fra R&D)

Kunde har behov som driver utviklings process som skal bygge et produkt som møte kundens behov. så lenge det oppfylle constraints itviklene har

selv om vi har disse hoved ting Customers, Products, Constraints og Process. Under det er det mange ting også
  - Users
  - Requirements
  - Technology
  - Tools
  - Budget, Schedule
  - Legal, Ethical
  - Teams,
  - Skills

But sometimes there is a problem between the user needs and expectation. one might build a product that fulfils the needs but is not what the user expected. 
It is part of a software engineers Job to capture the need so that it doesnt change much.
But there are other ways, For example Agile and Scrum are about when the needs change and allow for it all the time.

Sometimes a part of our job is not to blindly follow the client needs as they say it. cause a lot of time the client themselves dont know what they want/need. But they have domain knowledge. its just that they will usually not be technical(if the client is Human :). )

This is where water fall is great for. 

!Important. Usually this will be mixed where agile is nested under waterfall. for example the developer team might themselves in their team run agile with change etc. 
but the people who own the project in Entirety like project managers, CTO, drive waterfall at least when it comes to documentation, requirements etc.

The developers can have their own understanding of their project e.g forntend, backend etc. But usually as a whole there are requirements that can be hard to fulfill if they change all the time.

### complexity
this has something to do with coplexity. for example to expand on the example of the developer and the project manager.

If we think the developer is a plumber/carpenter/expert and the project manager is an architect,
if there is something wrong with for example a door to hall that it open too slowly an thus makes queues. then its something that perhaps the door smith installed the door wrong and we can just change the door and problem fixed.

but if its a problem with that the hallway to the hall is too narrow and thus causes queue(assuming the experts just did what was planned perfectly). then the problem is much harder to fix at the clients(building owner and stakeholder(people who want to use the hall)) expence.
To fix this is exponentially harder and potentially unfixable. To fix the best choice would have been durring th eplanning stage, checking the requirements and feasability etc.

### Layers that can be in a project
 - Presentation Layer
    - håndter User Interface.etc
  - Domain Layer
    - Application logic
    - another name for this is this is where our business logic
  - Service Access Layer
    - database access
    - location access
  - Platform Layer
    - frameworks
    - operating system

This is called **Layering** the number of layers is not limited to these

### fault and failures
a fault is a bug but a failure is the result of a failure.
all software have bugs but that deosnt mean that a failure will happen

### Testing
we can test for a big(meaningful part of the input domain) of the software to be tested and the entire output domain.
it could be the difference between looking for a bug 1 by 1 vs knowing exactly before even the client what and how the bug appers. 

### Iron triangle
  - Scope with quality
  - Time or schedule
  - Cost or bugjet
these are neutral exclusive, meaning if you increase one the other decreases. (inverse of cost)
if you will have low cost then you have to pay with quality or time.

You cant optimize all three and must choose 2

### Rammverk vs metode
software metode sier hvordan du skal gjør det.
med rammeverk/framework sier hvis du bruke dette ...
e.g git er et rammeverk - hvis du jobbe på denne måte sp klarer du å håndtere proskjeten din på en gri måte
version kontroll er en metode
scrum er et rammeverk men for eksempel Agile(manifesto) er et rammeverk.

### V-model
a good way to go about with software engineering is following the v model
    where we make the user requirements, system spec, subsystem spec, component spec, coding and unit testing, functional testing, intergration testing, system testing, acceptance testing

## 1
ord begrenser hva vi klarer å formidle.
hvis man klarer å beskrive en product wed bluk ar enkle ord VERB og SUBSTANTIV. 

for eksempel hvis vi tenke på word programmet:
  - Skrive Teskst
  - Lage dockumenter
    - Gjøre skole oppgaver. dette er et sub av lage dokumenter fordi for å gjøre skole oppgave må du lage docunter
    -  disse ting teller ikke i beskrivelsen av programet og derfor må vi være litt bred med beskrivelse
  - Lese documenter
  - Konvertere filer
  - Redigere Filer
    - Formatere filer
  - Stave kontroll
  - Printer Dokumenter
  - Sende Dokumenter
  - Samskrive documenter

## usecase diagrammer
use case diagramer for dette programer vil være alt innen en boundary av hva dette systemet er beskrevet til å gjøre. 
den kan snakke til andre systemer men det er ikke en en del av dette systemet usecase diagram.
e.g printer er nødvendig for word programet til å klare til å gjøre "Printer dokumenter". men printer er en egen use case som ikke inkluderer i vår useCase, bare en externe behov med egne usecase

contekst diagramer er når du har en usecase diagram som ingkluderer eksterne behov den har


Selv om man har en usecase beskrivelse, pleier det å være en dokument på hver av de use casene. ofte inkluderer en GUI. som ved foreksempel bruke FIGMA

SELV om man spliter business logikk fra use logikk(bruker grensesnitt). it doesnt affect the usecase diagram. this means if for example we restructure our code then it useless for the user.
ikke bland bland hva vi skal gjære med hvordan vi skal gjøre

for alle prosjekt begynn å skyll ut ting. hold de ting som er hører til hverandre, fraskilt fra hverandre
