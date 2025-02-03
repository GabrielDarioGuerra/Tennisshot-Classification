# **Tennis-Schläge-Klassifizierungsaufgabe**

Autoren:

- Gabriel Guerra
- Simon Bieri

Ziel des Projektes ist es, Tennisschläge (`forehand`, `backhand`, `serve`) anhand von Bildern zu Klassifizieren. Die
Bilder beinhalten Tennis-spielende Personen von hinten. Dabei wurden zwei verschiedene Datenquellen verwendet:
- Aus einem Online-Artikel (genauere Beschreibung im HTML in Part 1)
- Selbs extrahierte Bilder aus selbst aufgenommenen Videosequenzen

Das Projekt ist in zwei Teilen aufgeteilt:

## **Part 1**

### Inhalt

- Beschreibung der Problemstellung
- Beschreibung der verwendeten Datenquellen
- Vorprozessierung (Cropping) der Bilder
- Klassifizierung mit **ResNet-18**
- Klassifizierungsbenchmark mit einer **Keypoint-basierten Methode**

### Ergebnisse

- Die **ResNet-18-Methode** erzielte auf einzelnen Datasets eine **Accuracy** von 86 %, zeigte jedoch Schwächen bei der Generalisierung auf neue Daten:  
  Zwischen den Datasets wurde nur eine **Accuracy** von 25 % erreicht, schlechter als die zufällige Wahrscheinlichkeit von 33 %.

- Im Gegensatz dazu erreichte die **Keypoint-Methode** eine starke **Accuracy** von 86 % zwischen verschiedenen Datasets, basierend lediglich auf Keypoint-Daten, die mithilfe von **MediaPipe Pose** extrahiert wurden.

### Fazit

Dieses Projekt kombiniert Bildklassifikation und Keypoint-Analyse, um robuste Modelle zu entwickeln.  
Die Ergebnisse verdeutlichen das Potenzial der Keypoint-Methode für **Cross-Dataset-Generalization** und die 
Bedeutung einer umfassenden Datenbasis zur Verbesserung der Generalisierung für Modelle wie **ResNet-18**, 
insbesondere angesichts der Komplexität der Bilder und der Aufgabe.

[**Link zu Part 1**](https://1drv.ms/u/s!Aln5M-1qAY5Ml7QBcq09aRqtvlcN1w?e=BgjWzb)

---

## **Part 2**

### Inhalt

- Einfache, schnelle Klassifizierug mit **Keypoints** und **Gradient Boost Classifier**
- Feature Extraktion
- Data Augmentation
- Hyper-Parameter-Tuning

### Ergebnisse

- Nur anhand von Körperteil-Koordinaten, kann ein einfaches Machine-Learning-Modell trainiert werden.
- Im ersten Versuch wurde das Modell nur mit dem Online-Datenset trainiert. Im Testset desselben Datensets, wurde eine
**Accuracy** von **90 %** erreicht. Mit demselben Modell auf den selbst erfassten Datenset jedoch, konnte nur eine
**Accuracy** von **73 %** erreicht werden.
- Mithilfe des Trainings über den gesamten Datensatz, Data Augmentation und Hyper-Parameter-Tuning konnte eine 
**Accuracy** von **93 %** auf dem Testset erreicht werden.

### Fazit

Es ist absolut Möglich, dass mithilfe von vortrainierten Modellen, welche **Keypoints** aus Bildern extrahieren,
ein generisches Klassifizierungsmodell zu erstellen. 

[**Link zu Part 2**](https://1drv.ms/u/s!Aln5M-1qAY5Ml7QAWFX9ZGyPnQeCHw?e=Q1WPCW)
