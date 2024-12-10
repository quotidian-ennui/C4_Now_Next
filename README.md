# C4_Now_Next

Now/Next colouring for C4, so effectively extended colouring for <https://github.com/plantuml-stdlib/C4-PlantUML>

Using C4 diagrams in plantuml is great; this introduces some coloring so that we have the capability to think about a C4 diagram in terms of Roadmaps

Essentially it just defines some new colours for `System_now` (same as existing C4 System), `System_Next` (ochre), `System_Later` (a lovely lilac) along with the various other components of a C4 diagram because just having "System" is too boring and doesn't show on the same diagram your expected journey to the desired state.

So if you wanted this :

![example-uml](https://www.plantuml.com/plantuml/png/ZP51Qzj048Nl-XLZdro8hKjEFQLsJ1jGd5Qs2OM2M4jZQwWqg-xEPfly-iucjLLwA0KXnCvxtpozlV5Yd8I-ooOD7eaHLjVLlYoW5Hdy-pnt9YvE96qu18-kjYp8igXjdm-TuUISUsawEkIhw_ddTBI_B_BUU47t9tFrK3pio__0_WXMg273SsGEbAjtOsErmP-YME9iGbnteJadpHFSzeFbH1WqqAYux4sYxRDcwi-mVqflhGWsLOcT4RBitxJPzkjsjxwlYlN7zUQsUhpRVNhrbBDtsHcku1dhwmgc7-v0MkBJLB-tjaVB2D6mU31l0uXQ0AYC64WMqv5YuwmEpY4dpj8w5NVFWCSZrQI7YRXhoOC-iJK24Q4rJpWI2gFrpmnLXyxMt-lM4AkdDDpO7fRXvILQroJCb_1wYP0Q3A9xKfxbnVID7uaPtHKiTMOdkY7JLiPql_zLd8gzJiVcHitVCPx8WDT2e3SdgjLqWznemRy0)

You would do this:

```text
@startuml
!define C4_URL https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master
!define C4_COLOUR https://raw.githubusercontent.com/quotidian-ennui/C4_Now_Next/main
!include C4_URL/C4_Component.puml
!include C4_COLOUR/C4_System_Now_Next.puml
!include C4_COLOUR/C4_Dotted_Relations.puml

SYSTEM_LEGEND_WITH_COLOR()
System_Next(next, "AI thing", "Someone wants a thing with AI in it.")
System_Now(current, "Boringly efficient", "This is what we have")
System_Later(ai_blockchain, "Random Buzzword", "Quantum Computing AI Blockchain\nWinner, Bingo!")

Rel(current, next, "trains")
Dotted_Rel(current, ai_blockchain, "via some magic")
@enduml
```
