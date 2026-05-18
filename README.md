# Prediktion av båtar i hamn

Detta notebook tränar ML-modeller för att prediktera antalet båtar i de 100 mest populära hamnarna baserat på väderdata, tid och genomsnittlig beläggning. 
Ett externt dataset som tillhandahålls av företaget Skippo ligger till grund för modellträningen.

## 1. Introduktion
Modellerna syftar till att förutsäga antalet båtar i de 100 mest aktiva hamnarna.

## 2. Dataförberedelse
- Data läses in och relevanta kolumner konverteras till korrekta datatyper.
- Datasetet filtreras till de 100 hamnar med flest båtar.
- Korrelationsmatriser och databeskrivningar genereras för att analysera data.

## 3. Feature Engineering
- Cykliska tids- och vindriktningsfunktioner (`hour_sin`, `hour_cos`, `wind_dir_sin`, `wind_dir_cos`) skapas.
- En `average_boats_at_harbor` feature beräknas baserat på träningsdata för att förhindra dataläckage.

## 4. Modellträning och Utvärdering
- Data delas upp i tränings- och testset (80/20).
- Data standardiseras med `StandardScaler`.
- Två modeller tränas: Linjär Regression och RandomForestRegressor.
- Modellerna utvärderas med MAE, MSE, RMSE och R².

## 5. Resultat och Visualisering
- Predikterade värden jämförs med faktiska värden.
- Negativa prediktioner från Linjär Regression sätts till noll.
- Resultaten visualiseras med scatter plots, residualfördelning och feature importances för RandomForest-modellen.
- Distributionen av målvariabeln visas för både hela datasetet och topp 100 hamnar
