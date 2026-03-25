# Mikrostruktura_Modelowanie_Zmiennosci_Zrealizowanej_Skoki_Cenowe
**MODELOWANIE ZMIENNOŚCI ZREALIZOWANEJ I DETEKCJA SKOKÓW CENOWYCH | 01/2026**

**Narzędzia**
  * R
  * tidyverse
  * ggplot2
  * rugarch
  * forecast
  * moments
  * kableExtra
  * R Markdown

**Problem**  

Konieczność oszacowania dziennej zmienności wybranej spółki giełdowej przy użyciu danych wysokiej częstotliwości, porównanie trzech estymatorów zmienności zrealizowanej oraz identyfikacja statystycznie istotnych skoków cenowych w procesie cenowym przy użyciu testów BNS z różnymi estymatorami zintegrowanej kwartyczności

**Rozwiązanie**
  * Przygotowano i oczyszczono dane tick-by-tick z okresu 6 miesięcy, filtrując do godzin notowań ciągłych (9:00-16:50)
  * Zbudowano szeregi 5-minutowych stóp zwrotu z eliminacją efektu overnight
  * Obliczono trzy estymatory dziennej zmienności zrealizowanej
  * Wyznaczono zrealizowaną dwupotęgową wariację (Bipower Variation) jako estymator zmienności ciągłej
  * Obliczono estymatory zintegrowanej kwartyczności: wariację trójpotęgową (TQ) i czteropotęgową (RQ)
  * Przeprowadzono testy detekcji skoków: oparty na różnicach liniowych, różnicach logarytmów i test ilorazowy
  * Zwizualizowano wyniki: porównanie estymatorów zmienności, wykres miary względnego skoku RJ, detekcja skoków na wykresach RV vs BV.

**Wynik**
  * Zidentyfikowano σ₂ jako najbardziej wiarygodny estymator, stabilny na przestrzeni sesji, bez szumu z luk otwarcia
  * Potwierdzono wysoką korelację między dzienną stopą zwrotu a miarami zmienności zrealizowanej
  * Wykazano, że proces cenowy nie jest czysto ciągły, bo różnica między RV a BV wskazuje na składową skokową
  * Testy zaawansowane (logarytmiczne i ilorazowe) wykryły tylko 1-2 statystycznie istotne skoki (przełom kwietnia i maja)
  * Testy liniowe wykrywały więcej skoków, ale z ryzykiem błędów I rodzaju przy ekstremalnej zmienności
  * Udokumentowano, że większość dni o podwyższonym RV to okresy wysokiej zmienności ciągłej (dyfuzji), a nie anomalie skokowe
  * Miara względnego skoku RJ wskazała dni, gdzie skoki odpowiadały za 50-60% całkowitej zmienności (marzec, maj, czerwiec)
  * Projekt zrealizowano w zespole 2-osobowym z pełną dokumentacją w R Markdown.

