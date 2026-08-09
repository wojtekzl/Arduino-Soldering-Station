# Arduino MAX6675 Soldering Station

[Przejdź do wersji polskiej](#polska-wersja) | [English version below](#english-version)

---
![Main Photo](Media/front_with_soldering_iron.jpg)
---

<a name="polska-wersja"></a>
## Polska Wersja

### [Zobacz prezentację wideo na YouTube](https://youtu.be/utnwF4OAL98)

### O Projekcie
Zaawansowana stacja lutownicza DIY oparta na mikrokontrolerze Arduino Nano. Projekt łączy precyzyjne sterowanie cyfrowe z ergonomiczną obudową 3D. System wykorzystuje termoparę typu K (MAX6675) oraz tranzystor MOSFET do sterowania grzałką 12V.

### Główne Funkcjonalności
* **Sterowanie PID:** Autorski algorytm zapewniający stabilną temperaturę bez przeregulowań (overshoot).
* **Filtracja EMA (Exponential Moving Average):** Wykładnicze wygładzanie sygnału z potencjometru - eliminuje "skakanie" nastawy spowodowane szumami zasilacza.
* **Tryb Sleep:** Funkcja szybkiego schłodzenia grotu do 100°C po naciśnięciu przycisku Mode.
* **Synchronizacja Pomiaru:** Czasowe wyłączanie grzałki (PWM=0) podczas odczytu temperatury, co eliminuje błędy pomiarowe wywołane zakłóceniami EM.

### Schemat
Pełny schemat połączeń znajduje się w pliku `Hardware/diagram.png`.
![Diagram](Hardware/diagram.png)

### Struktura Repozytorium
* `/Firmware/` - Kod źródłowy Arduino (PID & Logic).
* `/Hardware/` - Schemat ideowy (`diagram.png`) wraz z rozpiską pinów.
* `/3D Models/` - Kompletny projekt obudowy w formacie `.3mf`.
* `/Media/` - Dokumentacja fotograficzna gotowego urządzenia.

### 🛠️ Lista części (Bill of Materials)

Poniżej znajduje się pełna lista komponentów użytych w projekcie wraz z linkami do zakupu. 

| Element | Specyfikacja / Uwagi | Link |
| :--- | :--- | :--- |
| **Kolba lutownicza C245** | Rękojeść + zestaw 4 grotów | [Link do sklepu](https://pl.aliexpress.com/item/1005007374283070.html) |
| **Stojak / Uchwyt lutowniczy** | Potrzebny do pozyskania sprężyny | [Link do sklepu](https://pl.aliexpress.com/item/1005007594381430.html) |
| **Moduł MAX6675** | Kontroler termopary (1 szt.) | [Link do sklepu](https://pl.aliexpress.com/item/1005002767849346.html) |
| **Zasilacz 12V 5A 60W** | Zasilanie główne | [Link do sklepu](https://pl.aliexpress.com/item/1005010210930161.html) |
| **Arduino Nano** | Mikrokontroler sterujący | [Link do sklepu](https://pl.aliexpress.com/item/1005007274954319.html) |
| **Wyświetlacz LCD 16x2 I2C** | Ekran z konwerterem magistrali I2C | [Link do sklepu](https://pl.aliexpress.com/item/1005012115973038.html) |
| **Przetwornica LM2596** | Moduł obniżający napięcie (Step-Down) | [Link do sklepu](https://pl.aliexpress.com/item/1005008183314384.html) |
| **Tranzystor MOSFET IRF9540N** | P-Channel | [Link do sklepu](https://pl.aliexpress.com/item/1005005195045769.html) |
| **Radiator tranzystora** | Dedykowe chłodzenie MOSFET | [Link do sklepu](https://pl.aliexpress.com/item/1005005945661635.html) |
| **Tranzystor BC548** | Bipolarny NPN | [Link do sklepu](https://pl.aliexpress.com/item/1005012273890651.html) |
| **Potencjometr 10 kΩ** | Liniowy (do regulacji) | [Link do sklepu](https://pl.aliexpress.com/item/1005006982762711.html) |
| **Zestaw rezystorów** | Wymagane wartości: 10 kΩ oraz 470 Ω | [Link do sklepu](https://pl.aliexpress.com/item/1005011772534173.html) |
| **Przycisk R13-507** | Chwilowy (microswitch) | [Link do sklepu](https://pl.aliexpress.com/item/10000274959292.html) |
| **Przełącznik KCD4** | Dwubiegunowy 16A 250V | [Link do sklepu](https://pl.aliexpress.com/item/4000138252026.html) |
| **Gniazdo zasilania AC-14-F6** | Zintegrowane gniazdo sieciowe | [Link do sklepu](https://pl.aliexpress.com/item/1005009372189680.html) |
| **Złącze GX12 5-pin** | Komplet męski + żeński | [Link do sklepu](https://pl.aliexpress.com/item/1005009246738180.html) |
| **Kabel zasilający** | Długość według własnych potrzeb | [Link do sklepu](https://pl.aliexpress.com/item/1005007175847704.html) |
| **Przewody zasilające** | Grubsze przewody dedykowane pod 12V 5A | [Link do sklepu](https://pl.aliexpress.com/item/1005012368787619.html) |
| **Przewody Arduino** | Męsko-żeńskie (np. pod ekran LCD) | [Link do sklepu](https://pl.aliexpress.com/item/1005006216103587.html) |
| **Przewody stykowe** | Zestaw zworek (140 szt.) | [Link do sklepu](https://pl.aliexpress.com/item/1005007561943443.html) |
| **Płytka stykowa** | Prototypowa (zalecana do testów) | [Link do sklepu](https://pl.aliexpress.com/item/1005008642599597.html) |
| **Płytka uniwersalna PCB** | 9x15 cm (do końcowego montażu) | [Link do sklepu](https://pl.aliexpress.com/item/1005012558186855.html) |
| **Listwa pinów (Goldpin)** | Prosta 1x40 pin | [Link do sklepu](https://pl.aliexpress.com/item/1005009884599370.html) |
| **Wkładki gwintowane** | Mosiężne M3 × 5 × 4.2 mm | [Link do sklepu](https://www.temu.com/pl/goods.html?goods_id=601099714384815) |
| **Śruby M5 × 8 mm** | Z łbem krzyżakowym Philips (20 szt.) | [Link do sklepu](https://pl.aliexpress.com/item/1005012149506637.html) |
| **Nakrętki M5** | Standardowe metryczne | [Link do sklepu](https://pl.aliexpress.com/item/1005011858105441.html) |
| **Gąbka czyścikowa** | Do czyszczenia grotów na gorąco | [Link do sklepu](https://pl.aliexpress.com/item/1005012432291048.html) |

> 💳 **Orientacyjny koszt całkowity:** **~420 PLN** *(podana kwota obejmuje same komponenty — bez podatków, cła oraz kosztów wysyłki)*.

### Inspiracje
Projekt powstał inspirując się projektem z kanału **[Zrobisz to SAM](https://www.youtube.com/@zrobisz_to_sam_)**. 
W mojej wersji wprowadziłem następujące zmiany i usprawnienia:
1. Pełna implementacja algorytmu PID dla lepszej stabilności cieplnej - wyeliminowanie przegrzewania się zasilacza.
2. Zmiana sterowania z encodera na potencjometr (szybsza nastawa) oraz dodanie filtracji cyfrowej (EMA) dla sygnału z potencjometru.
3. Dodanie fizycznego przycisku trybu Heat/Sleep dla błyskawicznej zmiany stanu pracy
4. Projektowanie od podstaw obudowy 3D razem z ergonomiczną podpórką.
5. Usunięcie zbędnych linijek kodu.

### UWAGA
Projekt dotyczy urządzeń pracujących z wysoką temperaturą oraz napięciem sieciowym. Nie ponoszę odpowiedzialności za jakiekolwiek szkody materialne, uszczerbek na zdrowiu lub inne straty powstałe w wyniku budowy lub użytkowania tego urządzenia. Wszystko robisz na własną odpowiedzialność. Pamiętaj o zachowaniu zasad BHP!

---

<a name="english-version"></a>
## English Version

### About The Project
An advanced DIY soldering station powered by an Arduino Nano microcontroller. This project combines precise digital control with an ergonomic 3D-printed enclosure. The system utilizes a K-type thermocouple (MAX6675) and a MOSFET transistor to drive a 12V heating element.

### Key Features
* **PID Control:** Custom-tuned algorithm ensuring stable temperature without overshooting.
* **EMA Filtering (Exponential Moving Average):** Software-based smoothing of the potentiometer signal - eliminates setpoint "jitter" caused by power supply noise.
* **Sleep Mode:** Rapid tip cooldown to 100°C at the press of the Mode button.
* **Measurement Synchronization:** Momentary heater deactivation (PWM=0) during temperature readouts to eliminate measurement errors caused by electromagnetic interference (EMI).

### Diagram
The full wiring diagram is available in the `Hardware/diagram.png` file.
![Diagram](Hardware/diagram.png)

### Repository Structure
* `/Firmware/` - Arduino source code (PID & Logic).
* `/Hardware/` - Circuit diagram (`diagram.png`) with pinout configuration.
* `/3D Models/` - Complete 3D enclosure project in `.3mf` format.
* `/Media/` - Photographic documentation of the finished device.

### 🛠️ Bill of Materials (BOM)

Below is the complete list of components used in the project, along with purchase links.

| Component | Specification / Notes | Link |
| :--- | :--- | :--- |
| **C245 Soldering Handle** | Handle + set of 4 tips | [Store Link](https://pl.aliexpress.com/item/1005007374283070.html) |
| **Soldering Stand** | Used as a source for the spring | [Store Link](https://pl.aliexpress.com/item/1005007594381430.html) |
| **MAX6675 Module** | Thermocouple IC (1 pcs) | [Store Link](https://pl.aliexpress.com/item/1005002767849346.html) |
| **Power Supply 12V 5A 60W** | Main power supply | [Store Link](https://pl.aliexpress.com/item/1005010210930161.html) |
| **Arduino Nano** | Microcontroller board | [Store Link](https://pl.aliexpress.com/item/1005007274954319.html) |
| **16x2 I2C LCD Display** | Screen with I2C module | [Store Link](https://pl.aliexpress.com/item/1005012115973038.html) |
| **LM2596 Converter** | Step-Down module | [Store Link](https://pl.aliexpress.com/item/1005008183314384.html) |
| **IRF9540N MOSFET** | P-Channel Transistor | [Store Link](https://pl.aliexpress.com/item/1005005195045769.html) |
| **MOSFET Heatsink** | Cooling for the transistor | [Store Link](https://pl.aliexpress.com/item/1005005945661635.html) |
| **BC548 Transistor** | Bipolar NPN | [Store Link](https://pl.aliexpress.com/item/1005012273890651.html) |
| **10kΩ Potentiometer** | Linear (for adjustment) | [Store Link](https://pl.aliexpress.com/item/1005006982762711.html) |
| **Resistor Kit** | Required values: 10kΩ & 470Ω | [Store Link](https://pl.aliexpress.com/item/1005011772534173.html) |
| **R13-507 Push Button** | Momentary switch | [Store Link](https://pl.aliexpress.com/item/10000274959292.html) |
| **KCD4 Power Switch** | Double Pole 16A 250V | [Store Link](https://pl.aliexpress.com/item/4000138252026.html) |
| **AC-14-F6 Power Socket** | Integrated AC power inlet | [Store Link](https://pl.aliexpress.com/item/1005009372189680.html) |
| **GX12 5-Pin Connector** | Male + Female pair | [Store Link](https://pl.aliexpress.com/item/1005009246738180.html) |
| **AC Power Cable** | Length based on personal preference | [Store Link](https://pl.aliexpress.com/item/1005007175847704.html) |
| **12V 5A Power Wires** | Thicker gauge wires for high current | [Store Link](https://pl.aliexpress.com/item/1005012368787619.html) |
| **Arduino Wires** | Male-to-Female jumper wires | [Store Link](https://pl.aliexpress.com/item/1005006216103587.html) |
| **Breadboard Jumpers** | Jumper wire set (140 pcs) | [Store Link](https://pl.aliexpress.com/item/1005007561943443.html) |
| **Breadboard** | Prototype board (recommended for testing) | [Store Link](https://pl.aliexpress.com/item/1005008642599597.html) |
| **Universal PCB** | 9x15 cm (for final assembly) | [Store Link](https://pl.aliexpress.com/item/1005012558186855.html) |
| **Pin Headers (Goldpins)** | Straight 1x40 pin | [Store Link](https://pl.aliexpress.com/item/1005009884599370.html) |
| **Threaded Inserts** | Brass M3 × 5 × 4.2 mm | [Store Link](https://www.temu.com/pl/goods.html?goods_id=601099714384815) |
| **M5 × 8 mm Screws** | Philips head (20 pcs) | [Store Link](https://pl.aliexpress.com/item/1005012149506637.html) |
| **M5 Nuts** | Standard metric nuts | [Store Link](https://pl.aliexpress.com/item/1005011858105441.html) |
| **Cleaning Sponge** | Tip cleaning sponge | [Store Link](https://pl.aliexpress.com/item/1005012432291048.html) |

> 💳 **Estimated Total Cost:** **~420 PLN** (~105 USD) *(excludes shipping costs, taxes, or custom duties)*.

### Inspirations
This project was inspired by the project from the **[Zrobisz to SAM](https://www.youtube.com/@zrobisz_to_sam_)** YouTube channel.
In my version, I have introduced the following improvements:
1. Full implementation of the PID algorithm for improved thermal stability – eliminating power supply overheating.
2. Switching the control from an encoder to a potentiometer (faster adjustment) and adding digital filtering (EMA) for the potentiometer signal.
3. Adding a physical Heat/Sleep mode button for instant operating mode switching.
4. Designing a 3D enclosure from scratch, including an ergonomic support.
5. Removing unnecessary lines of code.

### DISCLAIMER
This project involves high temperatures and mains voltage. I am not responsible for any property damage, personal injury, or other losses resulting from the construction or use of this device. You build and use it at your own risk. Always follow safety guidelines!

---

## Galeria / Gallery
| Tryb Pracy / Heat Mode | Wnętrze / Inside | Podpórka / Stand |
|---|---|---|
| ![Heat](Media/front_heat.jpg) | ![Inside](Media/inside.jpg) | ![Stand](Media/soldering_iron_stand.jpg) |

---
*Created by Wojciech Z | MIT License | 2026*
