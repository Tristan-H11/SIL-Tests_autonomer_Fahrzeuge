# Intelligentes Testen autonomer Fahrzeuge

Masterprojekt zum Thema SIL-Tests (Software-in-the-Loop) autonomer Fahrzeuge.
Die schriftliche Dokumentation wurde analog zum Projekt als Gruppenprojekt ausgearbeitet und findet in [Schriftstück_SIL_Tests_autonomer_Fahrzeuge.pdf](https://github.com/Tristan-H11/SIL-Tests_autonomer_Fahrzeuge/blob/main/Schriftstu%CC%88ck-SIL-Tests-autonomer-Fahrzeuge.pdf)

Ziel ist es, Fahrmanöver in einer simulierten Umgebung nicht über fest verdrahtete Skripte zu prüfen, sondern über **abstrakte Szenarien**: Ein Testfall wird als Menge von Constraints beschrieben (Start-/Endposition, Dauer, Reihenfolge fachlicher Aktionen, Geschwindigkeitsgrenzen). Eine konkrete Simulation gilt als gültig, wenn sie alle Constraints erfüllt.

Technisch basiert das Projekt auf [highway-env](https://github.com/Farama-Foundation/HighwayEnv) / Gymnasium für die Simulation und auf [BPpy](https://github.com/bThink-BGU/BPpy) (Behavioral Programming) für die Constraint-Prüfung.

## Was das Projekt kann

- Aufsetzen und Ausführen einer Multi-Agent-Highway-Simulation mit definierten Startpositionen
- Fachliche Interpretation der Roh-Observation aus HighwayEnv (Spur frei, Abstand zum Vorderfahrzeug, Geschwindigkeit, Spurzugehörigkeit)
- Beschreibung eines Überholmanövers als abstraktes Szenario mit Constraints
- Prüfung einer laufenden bzw. aufgezeichneten Simulation gegen diese Constraints über Events
- Demo-Simulationen, die je einen Constraint gezielt verletzen, inklusive Unit-Tests

## Status

Prototypischer Stand aus dem Masterprojekt. Der Observation-Wrapper ist auf HighwayEnv mit Kinematics-Observation (`absolute=False`, `normalize=False`) zugeschnitten und außerhalb dieser Konfiguration nur eingeschränkt nutzbar.
