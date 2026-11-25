# Etap 3, krok 3 — reguły biznesowe z przykładami i kontrprzykładami

## Po co to jest

Scenariusze (krok 2) mówią, *jak* przebiega rezerwacja czy anulowanie. Reguły mówią, *co zawsze musi być prawdą* i *kiedy wolno coś zrobić*. Są dziś rozsiane po krokach scenariuszy i rozszerzeniach. Ten krok wyciąga je w jedno miejsce i sprawdza każdą konkretnymi przykładami, żeby później baza (etap 4), backend i testy pilnowały tego samego.

## Pojęcia

### 1. Reguła biznesowa

- **Definicja:** jedno zdanie o domenie, które system musi egzekwować niezależnie od tego, jak wygląda ekran czy API. Da się je złamać, więc ma sens pytanie „co, jeśli ktoś spróbuje?”.
- **Nestumi:** R-025 „Osoba nie może zarezerwować własnej oferty”. Obowiązuje tak samo, gdy ktoś kliknie w UI, jak i wtedy, gdy wyśle żądanie z Postmana.
- **To nie jest:**
  - krok scenariusza („uczestnik wybiera termin”), bo opisuje przebieg, a nie ograniczenie,
  - sposób egzekwowania w UI („przycisk jest wyszarzony”). To tylko jedna z reakcji na regułę,
  - definicja ze słownika. Słownik mówi, *czym jest* kolizja, a reguła mówi, że kolizji *nie wolno* dopuścić.

**Analogia z frontu:** walidacja formularza w React to *jedno z miejsc*, gdzie reguła jest pilnowana. Samą regułą jest zdanie, z którego ta walidacja wynika, i backend musi go pilnować tak samo.

### 2. Example Mapping (Matt Wynne)

- **Definicja:** krótka sesja, w której dla jednej historii rozpisujesz:
  - **reguły** (karty niebieskie),
  - pod każdą regułą **przykłady** (karty zielone): konkretne sytuacje z wynikiem,
  - **pytania** (karty czerwone): to, czego nie wiesz i nie rozstrzygasz od razu.

  Historia to karta żółta. Kolory pochodzą z artykułu Wynne'a, w Nestumi wystarczy lista w markdownie.
- **Sygnały ostrzegawcze** (wg Wynne'a):
  - dużo czerwonych kart → za wcześnie na implementację,
  - dużo niebieskich → historia jest za duża,
  - reguła bez zielonych → nie wiesz jeszcze, co znaczy.
- **Przykład gotowego wyniku na innej domenie (siłownia):**

  > **Reguła:** Na zajęcia grupowe wchodzi tylko osoba z karnetem ważnym w dniu zajęć.
  >
  > Przykłady zgodne:
  > - Marta ma karnet ważny do 30.11, zajęcia 29.11 o 18:00 → wchodzi.
  > - Marta ma karnet ważny do 30.11, zajęcia 30.11 o 20:00 → wchodzi (ostatni dzień ważności się liczy).
  >
  > Przykład naruszenia:
  > - Marta ma karnet ważny do 30.11, zapisuje się na zajęcia 1.12 → zapis odrzucony, komunikat „karnet wygasł przed terminem zajęć”, nic nie zostaje zapisane.
  >
  > Pytania:
  > - Zajęcia zaczynają się 30.11 o 23:30, a kończą 1.12 o 0:30. Liczy się początek czy koniec?
  > - Co z zapisem złożonym przy ważnym karnecie, jeśli klub później skróci karnet?

- **To nie jest:** pisanie testów ani scenariuszy Gherkin (Given/When/Then). Przykłady są surowcem, z którego testy powstaną później. Tu wystarczy jedno zdanie: sytuacja → wynik.

**Analogia z frontu:** to jak tabela przypadków w `it.each([...])` w Jest, tylko napisana *przed* kodem, w języku domeny, bez wywołań funkcji.

### 3. Niezmiennik

- **Definicja:** reguła, która musi być prawdziwa **w każdej chwili**, dla każdego zapisanego stanu. Test: robisz „zdjęcie” danych w dowolnym momencie i patrzysz, czy reguła jest złamana. Nie musisz wiedzieć, kto i co właśnie robi.
- **Nestumi:** brak kolizji w zajętości jednej osoby (słownik: Kolizja, Zajętość; R-035, R-036). W żadnej chwili Anna nie może mieć dwóch aktywnych rezerwacji, których czasy zajętości mają część wspólną.
- **To nie jest:** warunek, który sprawdzasz tylko przy jednej czynności. Jeśli reguła mówi „*kiedy wolno* coś zrobić”, to raczej warunek operacji.

### 4. Warunek operacji

- **Definicja:** reguła przypięta do konkretnej czynności. Mówi, *kto* i *kiedy* może ją wykonać. Sprawdzasz ją w chwili, gdy ktoś próbuje działać. Na samym „zdjęciu” danych nie widać jej złamania.
- **Nestumi:** R-043 „Anulować można do rozpoczęcia spotkania”. Rezerwacja na wczoraj, która nie jest anulowana, niczego nie łamie. Złamaniem jest dopiero *próba* anulowania jej dziś. Podobnie R-025: dotyczy złożenia rezerwacji.
- **To nie jest:** uprawnienie techniczne w rodzaju „zalogowany / niezalogowany”. Logowanie to warunek dostępu (R-002), a warunek operacji opisuje sens biznesowy, na przykład czyja to rezerwacja albo czy spotkanie już się zaczęło.

### 5. Polityka

- **Definicja:** reguła, która jest **wyborem biznesu**, a nie koniecznością logiczną. Inna firma mogłaby rozsądnie wybrać inaczej. Często ma wartość domyślną albo da się ją wyobrazić jako ustawienie.
- **Nestumi:** automatyczne potwierdzenie rezerwacji (słownik: Potwierdzenie; ręczna akceptacja prowadzącego jest poza v1). Domyślny krok rozpoczęć równy czasowi zajętości (R-019).
- **To nie jest:** niezmiennik. Brak kolizji to konieczność, bo inaczej prowadzący fizycznie nie zdąży. Automatyczne potwierdzenie to wybór i można go zmienić bez psucia sensu systemu.

**Po co rozróżniać te trzy rodzaje?**

- Niezmiennik trzeba chronić przy *każdej* czynności, która go dotyka. Przykład: kolizja może powstać przy rezerwacji, ale też przy zmianie grafiku.
- Warunek operacji sprawdzasz w jednym miejscu.
- Politykę warto trzymać tak, żeby jej zmiana nie ruszała reszty.

## W praktyce: od use case'a do kart

Przykłady poniżej dotyczą siłowni i są hipotetyczne, a ich use case brzmi „zapisać się na zajęcia grupowe”.

### Skąd brać reguły

Czytasz use case linijka po linijce i w każdym z tych miejsc szukasz kandydatów na reguły:

- **Warunki wstępne** to zwykle warunek operacji: „zapisać się można tylko na zajęcia z grafiku”.
- **Linie „Wynik”** to często niezmiennik albo skutek reguły: „na zajęciach jest najwyżej tylu uczestników, ile wynosi limit”.
- **Kroki „system sprawdza…”**: każda sprawdzana rzecz to osobna reguła. Krok „system sprawdza ważność karnetu i wolne miejsca” daje dwie karty.
- **Rozszerzenia**: każde „nie da się, bo…” to naruszenie jakiejś reguły. Jeśli nie umiesz wskazać której, brakuje ci karty.
- **Słowa-sygnały**: „tylko”, „nie może”, „zawsze”, „co najwyżej”, „dopóki”.
- **Rzeczy oczywiste, których use case nie mówi wprost**, np. zapis działa od razu, bez akceptacji trenera. Jeśli inny klub mógłby rozsądnie zrobić inaczej, to jest polityka.

Filtr: jeśli nikt nie może spróbować tego złamać („system pokazuje grafik”), to krok przebiegu, a nie reguła.

### Przykłady zgodne (zielone)

- Zacznij od najprostszego przypadku. Każdy kolejny przykład zmienia **jedną** rzecz: granicę (ostatnia dozwolona wartość), czas (stan zmienił się tuż przed próbą) albo osobę lub rolę.
- Dwa przykłady, które różnią się tylko imieniem albo godziną z tego samego zakresu, sprawdzają to samo, więc jeden z nich jest zbędny.
- Forma: stan → próba → wynik w języku biznesu. Na przykład: „Karnet Marty jest ważny do 30.11, Marta zapisuje się na 30.11 20:00 → zapis powstaje”.

### Kontrprzykłady (naruszenia)

- **Musi być osiągalny**: osoba naprawdę może spróbować. Prowadzą do tego m.in. otwarta stara strona, drugie kliknięcie albo zmiana stanu w trakcie. Jeśli nie da się dojść do próby, przykład niczego nie testuje.
- **Bierz pierwszą wartość za granicą**: karnet do 30.11, zajęcia 1.12.
- **Wynik = co system robi + powód z tej reguły.** Jeśli powód odmowy pasuje do innej reguły („brak miejsc” zamiast „karnet wygasł”), to przykład testuje tamtą regułę.

### Pytania (czerwone): heurystyki

| Heurystyka | Pytanie na siłowni |
| --- | --- |
| granica | Zajęcia 23:30–0:30: liczy się dzień początku czy końca? |
| dwa naraz | Dwie osoby biorą ostatnie miejsce w tej samej sekundzie. |
| zmieni się później | Klub skraca karnet po tym, jak ktoś się zapisał. |
| ta sama osoba w dwóch rolach | Trener zapisuje się na zajęcia innego trenera albo na swoje. |
| zero / brak / dużo | Zajęcia z limitem 0? Karnet bez wejść? 50 zapisów naraz? |
| ktoś się pomyli | Marta zapisała się na złą godzinę. |
| kto to widzi | Czy inni uczestnicy widzą, kto jest zapisany? |

Zanim przykleisz czerwoną kartę, sprawdź dokumenty. Jeśli odpowiedź już tam jest, wskaż wpis zamiast pytać. Jeśli odpowiadasz sama (biała karta), podjęłaś nową decyzję i musi ona trafić do `docs/decisions.md`. Nie rozstrzygaj pytania przez analogię do podobnej decyzji. Podobny skutek nie oznacza tego samego powodu.

## Typowe błędy

1. **Reguła zapisana jako zachowanie UI.**
   - Źle: „Przycisk »Anuluj« znika po rozpoczęciu spotkania”.
   - Dobrze: „Anulować można do rozpoczęcia spotkania”. Ukryty przycisk to tylko jedna z reakcji. Żądanie wysłane z pominięciem UI i tak musi zostać odrzucone.
2. **Same „szczęśliwe” przykłady, bez naruszenia i bez przypadków granicznych.**
   - Źle: jedynym przykładem dla reguły o karnecie jest wejście 15.11.
   - Dobrze: dodaj ostatni dzień ważności (30.11) i pierwszy dzień po nim (1.12). Najwięcej uczą przykłady na granicy, jak styk w R-035.
3. **Przykład abstrakcyjny.**
   - Źle: „rezerwacja A koliduje z rezerwacją B”.
   - Dobrze: konkretne osoby, oferty, godziny, długości, jak w słowniku przy Kolizji: medytacja 10:00–12:00 a zajęcia oddechowe 11:30–12:00. Bez liczb nie widać, gdzie przebiega granica.
4. **Dwie reguły w jednym zdaniu albo naruszenie bez reakcji.**
   - Źle: „Można anulować własną rezerwację do rozpoczęcia i wtedy czas się zwalnia”. To trzy rzeczy naraz: kto, do kiedy i jaki jest skutek.
   - Źle: przykład naruszenia kończy się na „to niedozwolone”.
   - Dobrze: przy każdym naruszeniu dopisz, *co system wtedy robi*, czyli co widzi osoba i co (nie) zostaje zapisane. Tego wymaga kryterium „gotowe, gdy”.

## Pytania sprawdzające

1. *(przykład hipotetyczny)* Siłownia ma regułę „Trener nie może prowadzić dwóch zajęć jednocześnie” i drugą: „Zajęcia można odwołać najpóźniej 2 godziny przed startem”. Który rodzaj reguły to który? Po czym to poznajesz, używając testu „zdjęcia”?
2. Dlaczego przykład styku z R-035 (spotkanie 12:00–12:30 po medytacji 10:00–12:00) jest dla reguły kolizji cenniejszy niż przykład spotkań o 10:00 i o 15:00?
3. Ktoś proponuje: „Reguła R-025 jest zbędna, bo prowadzący nie widzi przycisku »Rezerwuję« na własnej ofercie”. Co odpowiesz?

## Skąd to wiem

Przeczytane teraz przez Claude: `etap3-plan.md` (krok 3 i rejestr), `docs/roadmap.md` (etap 3), `docs/glossary.md` (Kolizja, Zajętość, Potwierdzenie, Złożenie rezerwacji, Anulowanie) i nagłówki R-025, R-035, R-036, R-041, R-043, R-044, R-045, R-015, R-037 w `docs/decisions.md`. Z pamięci, bez sprawdzenia teraz: opis Example Mapping z artykułu Matta Wynne'a (kolory kart, sygnały ostrzegawcze) i podział na niezmienniki, warunki operacji i polityki jako ogólna praktyka modelowania. Sekcja „W praktyce” opiera się na strukturze use case'ów z `docs/use-cases.md` (warunki wstępne, wynik, kroki, rozszerzenia) i heurystykach z instrukcji przeglądu reguł (`.claude/skills/review-business-rules`); przykłady z siłowni są wymyślone.
