# C4_Now_Next

Now/Next colouring for C4, so effectively extended colouring for <https://github.com/plantuml-stdlib/C4-PlantUML>

Using C4 diagrams in plantuml is great; this introduces some coloring so that we have the capability to think about a C4 diagram in terms of Roadmaps

Essentially it just defines some new colours for `System_now` (same as existing C4 System), `System_Next` (ochre), `System_Later` (a lovely lilac) along with the various other components of a C4 diagram because just having "System" is too boring and doesn't show on the same diagram your expected journey to the desired state.

```text
@startuml
!define C4_URL https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master
!define C4_COLOUR https://raw.githubusercontent.com/quotidian-ennui/C4_Now_Next/main
!include C4_URL/C4_Component.puml
!include C4_COLOUR/C4_System_Now_Next.puml

SYSTEM_LEGEND_WITH_COLOR()
System_Next(next, "AI thing", "Someone wants a thing with AI in it.")
System_Now(current, "Uncool", "This is what we have")
System_Later(ai_blockchain, "Random Buzzword", "Quantum Computing AI Blockchain\nWinner, Bingo!")

current ..> next: migrates
Rel(current, ai_blockchain, "injects data into")
@enduml

```
