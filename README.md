Bevezetés az Adattudományba: Kép-osztályozási Projekt

## Cél
A projekt célja egy Konvolúciós Neurális Háló (CNN) megvalósítása a TensorFlow/Keras keretrendszerrel bináris kép-osztályozási feladat megoldására.

## 📊 Elért Eredmények és Főbb Metrikák

| Metrika | Eredmény | Megjegyzés |
| :--- | :--- | :--- |
| **Végső Teszt Pontosság** | **71.00%** | (A 75%-os határt nem sikerült elérni.) |
| **Teszt F1-score (pozitív osztály)** | **0.2927** | (Jelzi a gyenge, de meglévő felismerést.) |
| **Tréning rétegek száma** | Legalább 7 rejtett réteg | (Teljesítve) |
| **Regularizáció** | Early Stopping, Dropout | (Teljesítve) |

## ⚙️ Módszertani Kihívások és Korrekció

A modell tanítása során a legnagyobb kihívást az osztályok közötti jelentős **egyensúlytalanság (Class Imbalance)** jelentette a kisméretű adathalmazon.
* **Probléma:** A modell a kezdeti tréning során az összes mintát a gyakoribb (0-ás) osztályba sorolta ($\mathbf{0.00}$ Recall).
* **Korrekció:** A problémát **osztálysúlyozás** (`class_weight='balanced'`) bevezetésével orvosoltuk. Ez javította a modell kiegyensúlyozottságát (a ritkább osztály Recall-ja **$0.24$-ra** emelkedett), de a teljes pontosság végül $71.00\%$-on stabilizálódott.
