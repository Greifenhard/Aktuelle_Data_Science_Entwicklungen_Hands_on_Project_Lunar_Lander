# Aktuelle_Data_Science_Entwicklungen_Hands_on_Project_Lunar_Lander

Dieses Repository enthält die Implementierung von zwei verschiedenen Reinforcement Learning (RL)-Agenten zur Lösung der  **LunarLander-v3** -Umgebung von Gymnasium: ein **Policy Learning (PL)-Agent** und ein  **Double Deep Q-Network (Double DQN)-Agent** . Ziel dieses Projekts war es, die grundlegenden Konzepte des Reinforcement Learnings praktisch anzuwenden und die Leistungsfähigkeit unterschiedlicher Algorithmen in einer gängigen Simulationsumgebung zu demonstrieren.

## Inhaltsverzeichnis

* [Über das Projekt](https://www.google.com/search?q=%23%C3%BCber-das-projekt)
* [Umgebung: LunarLander-v3](https://www.google.com/search?q=%23umgebung-lunarflander-v3)
* [RL-Agenten](https://www.google.com/search?q=%23rl-agenten)
  * [Double Deep Q-Network (DQN) Agent](https://www.google.com/search?q=%23double-deep-q-network-dqn-agent)
  * [Policy Learning (PL) Agent](https://www.google.com/search?q=%23policy-learning-pl-agent)
* [Dateistruktur](https://www.google.com/search?q=%23dateistruktur)
* [Einrichtung und Ausführung](https://www.google.com/search?q=%23einrichtung-und-ausf%C3%BChrung)
* [Ergebnisse](https://www.google.com/search?q=%23ergebnisse)
* [Autoren](https://www.google.com/search?q=%23autoren)
* [Lizenz](https://www.google.com/search?q=%23lizenz)

## Über das Projekt

Dieses Projekt ist Teil einer Hands-On-Aufgabe zum Thema Reinforcement Learning. Es beleuchtet die Anwendung von RL-Algorithmen zur Steuerung eines Raumschiffs, das sicher auf einer vorgegebenen Landeplattform auf dem Mond landen muss. Durch die Implementierung und den Vergleich zweier unterschiedlicher Ansätze werden die Stärken und Schwächen von wertbasierten und politikbasierten Methoden im RL aufgezeigt.

## Umgebung: LunarLander-v3

Die  **LunarLander-v3** -Umgebung ist eine klassische Kontrollaufgabe im Reinforcement Learning.

* **Zustandsraum:** Besteht aus 8 kontinuierlichen Werten (Position, Geschwindigkeit, Winkel, Winkelgeschwindigkeit des Landers, Bodenkontakt der Beine).
* **Aktionsraum:** Diskret mit 4 möglichen Aktionen (nichts tun, Haupttriebwerk zünden, linkes Seitentriebwerk zünden, rechtes Seitentriebwerk zünden).
* **Belohnung:** Der Agent erhält Belohnungen für eine sichere Landung auf der Plattform und Strafen für Abstürze oder den unnötigen Verbrauch von Treibstoff. Ziel ist es, die kumulierte Belohnung zu maximieren.

## RL-Agenten

Im Rahmen dieses Projekts wurden zwei Agenten entwickelt und trainiert:

### Double Deep Q-Network (DQN) Agent

Der Double DQN Agent ist eine Weiterentwicklung des klassischen DQN-Algorithmus, der das Problem der Überschätzung von Q-Werten adressiert. Er verwendet zwei separate neuronale Netzwerke – ein **Online-Netzwerk** für die Aktionsauswahl und ein **Target-Netzwerk** für die Zielwertberechnung –, um ein stabileres Training zu gewährleisten. Der Agent nutzt zudem ein **Replay-Memory** für Experience Replay und eine **Epsilon-Greedy-Strategie** zur Balancierung von Exploration und Exploitation.

* **Implementierung:** `DQN_LunarLander.ipynb`
* **Trainiertes Modell:** `./Models/DQN_Model.pt`

### Policy Learning (PL) Agent

Der Policy Learning Agent basiert auf dem  **REINFORCE-Algorithmus** , einer Form des Policy Gradient Methods. Dieser Agent lernt direkt eine Politik (d.h., die Wahrscheinlichkeitsverteilung über Aktionen), die den erwarteten kumulativen Belohnung maximiert. Der Agent sammelt Erfahrungen über eine gesamte Episode und aktualisiert seine Politik am Ende jeder Episode basierend auf den diskontierten Belohnungen.

* **Implementierung:** `PL_LunarLander.ipynb`
* **Trainiertes Modell:** `./Models/PL_Model.pt`

## Dateistruktur

```
.
├── DQN_LunarLander.ipynb
├── PL_LunarLander.ipynb
├── requirements.txt
└── Models/
    ├── DQN_Model.pt
    └── PL_Model.pt
```

* `DQN_LunarLander.ipynb`: Jupyter Notebook mit der Implementierung, dem Training und der Evaluierung des Double DQN Agenten.
* `PL_LunarLander.ipynb`: Jupyter Notebook mit der Implementierung, dem Training und der Evaluierung des Policy Learning Agenten.
* `requirements.txt`: Listet alle benötigten Python-Pakete auf.
* `Models/`: Verzeichnis zum Speichern der trainierten Modelle.
  * `DQN_Model.pt`: Das trainierte PyTorch-Modell des Double DQN Agenten.
  * `PL_Model.pt`: Das trainierte PyTorch-Modell des Policy Learning Agenten.

## Einrichtung und Ausführung

Um dieses Projekt auszuführen, folgen Sie bitte den folgenden Schritten:

1. **Repository klonen:**
   **Bash**

   ```
   git clone https://github.com/Greifenhard/Aktuelle_Data_Science_Entwicklungen_Hands_on_Project_Lunar_Lander.git
   cd IhrRepositoryName
   ```
2. **Virtuelle Umgebung erstellen und aktivieren (empfohlen):**
   **Bash**

   ```
   python -m venv venv
   # Auf Linux/macOS
   source venv/bin/activate
   # Auf Windows
   venv\Scripts\activate
   ```
3. **Abhängigkeiten installieren:**
   **Bash**

   ```
   pip install -r requirements.txt
   ```
4. **Jupyter Notebook starten:**

   Öffnen Sie anschließend `DQN_LunarLander.ipynb` oder `PL_LunarLander.ipynb` in Ihrem Browser. Sie können die Zellen der Notebooks ausführen, um die Agenten zu trainieren oder die Ergebnisse zu visualisieren. Die Notebooks enthalten bereits die Outputs der ausgeführten Zellen, sodass die Ergebnisse direkt sichtbar sind.

## Ergebnisse

Die detaillierte Analyse und Bewertung der Agenten, einschließlich Trainingsverläufen und Performance-Metriken, finden Sie in den jeweiligen Jupyter Notebooks und dem dazugehörigen Projektbericht.

Kurz zusammengefasst:

* Der **Double DQN Agent** zeigte eine herausragende Leistung mit hoher Konsistenz und einer Erfolgsrate von über 90% beim Erreichen hoher Belohnungen.
* Der **Policy Learning Agent** konnte die Aufgabe grundsätzlich lösen, zeigte jedoch eine signifikante Leistungsinkonsistenz und eine höhere Varianz in den Belohnungen.

## Autor

* Michael Greif

## Lizenz

Dieses Projekt ist unter der MIT-Lizenz lizenziert. Siehe die `LICENSE`-Datei für weitere Details.

---
