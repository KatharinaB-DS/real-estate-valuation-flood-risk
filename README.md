# Hybrid Machine Learning | Immobilienbewertung & Hochwasserrisikoanalyse

**Bachelorarbeit – Informatik**  
**Schwerpunkt: Künstliche Intelligenz & Data Science**

Entwicklung eines hybriden Systems zur Immobilienbewertung und Analyse des standortbezogenen Hochwasserrisikos.

Das Projekt integriert strukturierte Immobiliendaten mit Geodaten aus OpenStreetMap sowie offiziellen Hochwassergefahrenkarten des ISOK-Systems (GUGiK). Ziel ist die automatische Bewertung von Immobilien unter Berücksichtigung klassischer Objektmerkmale und räumlicher Risikofaktoren.

---

## Projektübersicht

Das entwickelte System verarbeitet Daten aus drei Quellen:

- **Apartment Prices in Poland** (Kaggle)
- **OpenStreetMap**
- **ISOK** – Hochwassergefahrenkarten (GUGiK)

Während der Datenaufbereitung werden georäumliche Merkmale erzeugt, darunter die Entfernung zu Gewässern sowie die Entfernung zu Hochwasserrisikozonen. Anschließend werden diese Merkmale mit den tabellarischen Immobiliendaten kombiniert und in einem LightGBM-Modell zur Vorhersage des Immobilienwertes verarbeitet. Die Ergebnisse werden in Power BI visualisiert.

---

## Verwendete Technologien

- Python
- pandas
- NumPy
- scikit-learn
- LightGBM
- GeoPandas
- Shapely
- OSMnx
- Matplotlib
- Seaborn
- Folium
- joblib
- Power BI

---

## Projektergebnisse

- **Datenbasis:** 43.751 Immobilien aus Warschau, Breslau und Danzig
- **Integration:** Erfolgreiche Verschmelzung von Immobilien- und Geodaten
- **Automatisierung:** Automatische Berechnung der Entfernung zu Gewässern
- **Risikoanalyse:** Automatische Berechnung der Entfernung zu Hochwasserrisikozonen
- **Prädiktion:** Vorhersage des Immobilienwertes mittels LightGBM
- **Visualisierung:** Interaktive Ergebnisdarstellung in Power BI

---

## Modellergebnisse

| Modell | $R^2$ |
| :--- | ---: |
| Dummy Regressor | -0.0002 |
| Lineare Regression | 0.7190 |
| Ridge Regression | 0.7247 |
| LightGBM (nur tabellarische Daten) | 0.8353 |
| **LightGBM + OSM + ISOK (Hybridmodell)** | **0.8514** |

Die Erweiterung des Modells um Geodaten aus OpenStreetMap und ISOK führte zu einer deutlichen Verbesserung der Vorhersagegenauigkeit. Die entwickelte Variable **`log_distance_to_flood`** belegte Platz 2 im Feature-Importance-Ranking des Modells und bestätigte empirisch den signifikanten Einfluss des Hochwasserrisikos auf den Immobilienwert.

---

## 🖼️ Projektvorschau

### Entfernung zu Gewässern (Breslau)

![Entfernung zu Gewässern](Wroclam%20weryfikacja%20odleglosci%20od%20wody.png)

---

### Immobilien in Hochwasserrisikozonen

![Immobilien in Hochwasserrisikozonen](nierucholosci%20w%20strefie%20ryzyka.png)

---

### Ranking der wichtigsten Modellmerkmale (Feature Importance)

![Ranking der wichtigsten Modellmerkmale](Ranking%20ważności%20cech%20modelu.png)

---

### Partial Dependence Plot (PDP)

![Partial Dependence Plot](Partial%20Dependence%20Plot.png)

---

## Fazit

Im Rahmen der Arbeit wurde ein prototypisches System zur Immobilienbewertung und Bewertung standortbezogener Hochwasserrisiken erfolgreich entwickelt. Die Integration von OpenStreetMap- und ISOK-Daten verbesserte die Modellqualität maßgeblich und demonstrierte, dass räumliche Merkmale einen quantitativ messbaren Einfluss auf die Vorhersage von Immobilienpreisen haben.

---

## Datenquellen

- Apartment Prices in Poland (Kaggle)
- OpenStreetMap
- ISOK – Hochwassergefahrenkarten (GUGiK)

---

## Autor

**Katarzyna Brzeski**  
Bachelorarbeit – Informatik  
Vizja Universität Warschau
