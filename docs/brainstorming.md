# Platforma ofert zdrowia psychicznego i dobrostanu

**Opis projektu i kierunki rozwoju · wersja robocza 0.4 · 25.10.2026**

Autorski projekt do nauki fullstacka: wyszukiwanie specjalistów, instruktorów i ofert, a następnie rezerwowanie spotkań oraz zapisy na zajęcia, kursy i potencjalnie wyjazdy. Pomoc psychologiczna i psychiatryczna ma być wyraźnie odróżniona od jogi, medytacji, masażu i innych praktyk dobrostanu.

Temat projektu został wybrany. Obecnie trwa burza mózgów nad funkcjonalnościami i kierunkami rozwoju; zakres MVP będzie ustalany później. Zebrane możliwości tworzą pulę funkcji i scenariuszy do oceny przyszłego modelu. Nie oznaczają zobowiązania do wdrożenia ich wszystkich ani gotowego projektu bazy danych.

Punktem odniesienia jest [roadmap.md](roadmap.md). Szczególny nacisk: model domeny, SQL, spójność, transakcje, API oraz uzasadnianie decyzji. Projekt nie ma narzuconego harmonogramu.

## 1. Ustalenia i otwarte decyzje

### Ustalenia

- Wybranym tematem jest połączenie wyszukiwania pomocy psychologicznej i psychiatrycznej z osobnym obszarem zajęć i praktyk związanych z dobrostanem.
- Obecnie zbieramy i rozwijamy pomysły na funkcjonalności. Nie określamy jeszcze MVP.
- Użytkownik ma rozumieć, kim jest prowadzący i jaki charakter ma konkretna oferta. Instruktor medytacji nie może być przedstawiany jako psycholog wyłącznie z racji obecności na platformie.
- Jedna osoba może równocześnie mieć wiele profesji i kwalifikacji, np. być psychologiem, psychiatrą i instruktorem jogi. Nie wymaga to osobnych kont. Charakter poszczególnych ofert pozostaje wyraźnie opisany.
- Do rozważenia są zarówno pojedyncze spotkania, jak i grupy oraz kursy obejmujące wiele spotkań.
- Dodatkowy pomysł obejmuje miejsca udostępniane organizatorom wyjazdów, porozumienie z właścicielem oraz późniejsze zapisy uczestników.
- Aktualnie planowany kierunek to organizacja zapisów. Płatności za usługi i rozliczenia między stronami pozostają możliwym przyszłym rozszerzeniem.
- Osobnym pomysłem na przyszłość jest abonament opłacany przez prowadzących za możliwość korzystania z platformy, publikacji ofert lub obsługi rezerwacji. Nie jest to element ustalonego MVP; MVP nie zostało jeszcze wybrane.
- Profile, oferty, obiekty, dostępności i zapisy można w całości symulować. Pozyskanie rzeczywistych klientów lub wykonawców nie jest warunkiem nauki.
- Przyszłe pomysły mają być zachowane jako materiał do wyboru MVP i późniejszego projektowania domeny oraz bazy.

### Kwestie do późniejszego doprecyzowania

- Zakres MVP i katalog profesji oraz praktyk w pierwszej wersji: decyzja świadomie odłożona do czasu zebrania funkcjonalności.
- Sposób prezentowania osoby o wielu profesjach: jedno konto i jeden wspólny profil albo jedno konto i kilka profili zawodowych. Wybór pozostaje otwarty; wariant kilku profili nie oznacza kilku niezależnych osób ani niezależnych grafików.
- Zasady czasu zajętości: długości poszczególnych usług, ewentualne warianty długości tej samej usługi, przerwy przed i po spotkaniu oraz czas przejazdu między miejscami. Różne długości usług trzeba uwzględnić niezależnie od późniejszego wyboru tych szczegółowych zasad.
- Organizacja wyjazdów: miejsce udostępnia jego właściciel lub zarządca, roboczo „gospodarz obiektu”. Nie ustalono, czy organizatorem jest prowadzący, gospodarz, czy inna osoba łącząca prowadzących i miejsce.
- Szczegółowe zasady publikowania wyjazdu i uzgadniania odpowiedzialności między stronami.
- Zakres ewentualnych płatności, rozliczeń i abonamentów w przyszłości.
- Widoczność danych: które informacje są dostępne wszystkim, a które tylko konkretnym osobom. Przykłady w sekcji 4 wyjaśniają to pytanie; ostateczne zasady pozostają do wyboru.

Nowe funkcjonalności poniżej są propozycjami do burzy mózgów, a nie zatwierdzonym zakresem realizacji. Powiązanie z roadmapą pokazuje ich wartość edukacyjną, nie wyznacza MVP.

## 2. Użytkownicy i problem

Użytkownik szukający oferty chce znaleźć odpowiednią osobę lub wydarzenie według rodzaju usługi, sposobu pracy, miejsca i terminu. Następnie chce jednoznacznie wiedzieć, czy termin lub miejsce są potwierdzone, oraz móc obsłużyć zmianę albo rezygnację.

Prowadzący chce opublikować ofertę, określić dostępność i zasady uczestnictwa oraz zarządzać potwierdzonymi spotkaniami lub zapisami. Organizator kursu potrzebuje również harmonogramu i limitu miejsc.

W przyszłym scenariuszu wyjazdowym właściciel obiektu chce udostępniać miejsce w wybranych okresach, a organizator potrzebuje uzgodnić pobyt grupy, przygotować wydarzenie i przyjmować uczestników.

Trzy główne czynności uczestnika:

1. Wyszukanie i porównanie ofert w odpowiednim obszarze.
2. Rezerwacja spotkania lub zgłoszenie udziału w kursie albo wyjeździe.
3. Sprawdzenie potwierdzenia, harmonogramu i zmian oraz obsługa rezygnacji.

Trzy główne czynności strony publikującej ofertę:

1. Przygotowanie profilu i konkretnej oferty.
2. Ustalenie terminów, dostępności, pojemności i zasad zapisów.
3. Obsługa zgłoszeń, potwierdzeń, zmian i komunikacji z uczestnikami.

## 3. Obszary ofert i sposób ich rozróżniania

### Pomoc psychologiczna i psychiatryczna

Możliwe oferty psychologów, psychoterapeutów i psychiatrów. Jedna osoba może mieć równocześnie kilka z tych profesji oraz dodatkowe kwalifikacje, np. instruktora jogi. Osobno opisujemy osobę, jej profesje i kwalifikacje, deklarowany zakres pracy oraz konkretną usługę. Przykładowe kryteria: podejście terapeutyczne, obszary pomocy, grupa odbiorców, forma online lub stacjonarna, cena i dostępność.

### Zajęcia i praktyki dobrostanu

Możliwe oferty instruktorów jogi, medytacji, technik oddechowych i relaksacyjnych oraz masaży, w tym masaży ajurwedyjskich. Opis dotyczy konkretnej praktyki i przygotowania prowadzącego. Umieszczenie oferty w tej części nie oznacza uprawnień do udzielania pomocy psychologicznej lub psychiatrycznej.

### Forma oferty jako osobny wymiar

W obrębie odpowiedniego obszaru oferta może obejmować spotkanie indywidualne, pojedyncze zajęcia grupowe, kurs z wieloma spotkaniami albo wyjazd. Kurs nie jest osobną profesją. Nazwa programu, np. MBSR lub MBCT, również nie zastępuje informacji o roli prowadzącego i charakterze oferty.

Konkretne programy trzeba sklasyfikować według ich rzeczywistego zakresu. Sama obecność elementów medytacji nie rozstrzyga, do którego obszaru należy oferta.

### Wiele profesji jednej osoby

Jedna osoba może przedstawiać się jako psycholog, psychiatra i instruktor jogi, jeśli odpowiada to jej rzeczywistym kwalifikacjom. Ta osoba może publikować konsultację psychiatryczną, spotkanie psychologiczne i zajęcia jogi. Przy każdej ofercie użytkownik widzi właściwy charakter usługi i rolę prowadzącego. Do rozważenia pozostają dwa warianty: wspólny profil z wyraźnie rozdzielonymi ofertami albo kilka profili zawodowych obsługiwanych z jednego konta, np. oddzielna prezentacja praktyki psychologicznej i działalności instruktorskiej. Wariant prezentacji nie został wybrany. Rozdzielenie profili nie tworzy osobnych osób ani nie może omijać wspólnej kontroli zajętości prowadzącego.

Wspólna dostępność tej osoby powinna zapobiegać konfliktom między jej ofertami. Potwierdzona konsultacja nie może pozwolić na potwierdzenie nakładających się zajęć jogi u tej samej osoby tylko dlatego, że oferty należą do różnych kategorii. Ewentualne wyjątki wymagają jawnej reguły.

Kontrola dotyczy całego przedziału zajętości, a nie wyłącznie godziny rozpoczęcia. Przykładowe długości do testowania: konsultacja 60 minut, medytacja 120 minut, zajęcia oddechowe 30 minut. Nie są to narzucone standardy usług. Medytacja 10:00–12:00 wyklucza zajęcia oddechowe 11:30–12:00 u tego samego prowadzącego, mimo różnych godzin rozpoczęcia. Spotkanie 12:00–12:30 może być dozwolone, jeśli ustalone zasady nie wymagają przerwy. Oferowane terminy muszą mieścić cały czas zajętości w dostępności osoby.

Do późniejszego rozważenia: jedna długość przypisana do oferty albo kilka jawnych wariantów, przerwy przed i po spotkaniu oraz przejazdy między miejscami. Dla zajęć grupowych czas prowadzącego zajmuje konkretne spotkanie; kolejny zapis uczestnika na to samo spotkanie wykorzystuje miejsce w grupie, a nie tworzy nowego konfliktującego spotkania. Zmiana długości oferty powinna mieć określony wpływ na przyszłe rezerwacje; proponowana zasada to zachowanie uzgodnionego czasu istniejących rezerwacji do osobnego uzgodnienia zmiany.

Profesja lub kwalifikacja opisuje przygotowanie osoby. Rola organizacyjna, np. prowadzący, organizator, gospodarz obiektu albo uczestnik, opisuje jej udział w konkretnej sytuacji. Same kwalifikacje nie przyznają dostępu do cudzych zapisów.

## 4. Role w przyszłym scenariuszu wyjazdu

| Rola | Przykładowa odpowiedzialność |
| --- | --- |
| Uczestnik | Wybór oferty, zgłoszenie, udział, rezygnacja |
| Prowadzący | Prowadzenie spotkań lub zajęć zgodnie z ofertą |
| Organizator | Ustalenie programu, warunków i zapisów na konkretną edycję |
| Gospodarz obiektu, czyli jego właściciel lub zarządca | Udostępnienie obiektu, określenie dostępności i warunków |
| Administrator platformy | Opcjonalna obsługa publikacji, zgłoszeń lub weryfikacji profili |

Jedna osoba może pełnić kilka ról. Właściciel obiektu nie musi prowadzić zajęć, a prowadzący nie musi być organizatorem ani właścicielem. Zakres uprawnień wobec konkretnej oferty wymaga późniejszego ustalenia.

### Możliwe modele organizacji wyjazdu

Pozostawiamy trzy warianty do rozważenia: prowadzący sam organizuje wyjazd i uzgadnia miejsce; gospodarz organizuje wyjazd i zaprasza prowadzących; osobny organizator łączy miejsce i prowadzących. To warianty produktu, nie wymóg zbudowania wszystkich naraz. Przykłady platform wyjazdowych pokazują zarówno łączenie prowadzenia z organizacją, jak i osobne zapytania grup do obiektu [5][6].

Określenie „gospodarz obiektu” jest roboczą nazwą funkcji w aplikacji. Nie przesądza, kto odpowiada za całą organizację wydarzenia.

### Co oznaczają dane publiczne i prywatne

Chodzi o to, kto może zobaczyć konkretną informację. Wyszukiwarka potrzebuje informacji o opublikowanej ofercie, ale nie potrzebuje ujawniać nazwisk zapisanych osób. Proponowane przykłady, do późniejszego zatwierdzenia:

| Informacja | Przykładowa widoczność |
| --- | --- |
| Opublikowany profil, profesje, opis oferty, cena i wolne terminy | Wszyscy odwiedzający, w zakresie wybranym do publikacji |
| Dane konkretnej rezerwacji, kontakt i wiadomości organizacyjne | Uczestnik oraz osoby uprawnione do obsługi tej rezerwacji |
| Nazwiska osób zapisanych na konsultację lub kurs | Osoby obsługujące dane spotkanie lub grupę; publicznie można pokazać liczbę wolnych miejsc |
| Link do spotkania online | Osoby uprawnione do udziału lub obsługi spotkania |
| Historia rezerwacji danej osoby | Ta osoba; prowadzący widzi informacje związane z obsługiwanymi przez niego rezerwacjami według ustalonych zasad |
| Informacje potrzebne gospodarzowi wyjazdu | Uzgodniony okres, liczebność i logistyka; zakres danych uczestników trzeba określić osobno |
| Dostęp administratora lub współorganizatora | Uprawnienia wynikające z powierzonego zadania, bez automatycznego dostępu do wszystkich danych |

Nie trzeba rozstrzygać teraz każdej pozycji. To materiał do ćwiczenia uprawnień: jedna osoba może mieć różne dostępy w różnych wydarzeniach. Zasady mają obejmować również wyszukiwanie, wiadomości, powiadomienia, eksport do kalendarza i widoki dostępne offline.

## 5. Pula funkcjonalności

Poniżej znajduje się rozszerzona pula pomysłów. Dotychczasowe kierunki oraz nowe propozycje są opisane jako zachowania aplikacji. Nie są zakresem MVP ani listą wszystkich funkcji obowiązkowych do wdrożenia.

Powiązania z roadmapą rozróżniają fundamenty z etapów 3–8, rozszerzenia projektu z etapów 9–12 oraz pogłębienie z etapów 13–17. Dany cel nauki można zrealizować na więcej niż jednej funkcji. Laboratoria z etapu 18 oraz opcjonalny Kubernetes z etapu 19 pozostają osobną ścieżką. Część kryteriów, np. migracje i odtwarzanie danych, wymaga ćwiczeń technicznych, a nie dodatkowego przycisku w aplikacji.

### 5.1. Konta, profile i publikowanie ofert

| Funkcjonalność | Przykładowe działanie | Co pokrywa z roadmapy |
| --- | --- | --- |
| Konto i własny panel | Użytkownik zakłada konto, loguje się, wylogowuje i widzi wyłącznie dostępne mu działania; wygasła sesja nie pozwala wykonać zmiany | 6: pełna funkcja, uwierzytelnianie, uprawnienia i obsługa błędów |
| Wiele profesji i sposób prezentacji | Ta sama osoba przedstawia różne kwalifikacje i oferty, np. konsultację psychiatryczną i jogę; do wyboru pozostaje wspólny profil albo kilka profili zawodowych w jednym koncie; każda oferta ma czytelny charakter | 3–4, 8: język domeny, relacje i odpowiedzialności |
| Szkic, publikacja i wycofanie oferty | Prowadzący przygotowuje szkic, publikuje ofertę i może ją wycofać; wcześniejsze rezerwacje zachowują historię i ustalone warunki | 3–4, 6–8, 15: cykl życia, reguły, historia i widoczność w wyszukiwaniu |
| Oferty w różnych miejscach i formach | Prowadzący ma spotkania w kilku gabinetach, studio lub online; oferta wskazuje właściwe miejsce realizacji | 3–4, 9: relacje i znaczenie lokalizacji |
| Delegowanie obsługi konkretnego wydarzenia | Organizator zaprasza współorganizatora albo osobę obsługującą zapisy i może cofnąć jej dostęp; zaproszenie nie daje dostępu do innych wydarzeń | 6, 8, 16: uprawnienia w kontekście zasobu i ich zmiana |

### 5.2. Dostępność i spotkania indywidualne

| Funkcjonalność | Przykładowe działanie | Co pokrywa z roadmapy |
| --- | --- | --- |
| Dostępność jednorazowa i powtarzalna | Prowadzący ustala konkretne daty albo regularne godziny i dodaje wyjątki, np. urlop; zmiana grafiku ma określony wpływ na potwierdzone wizyty | 3–4, 6–8, 10: reguły, cykle, daty i wyjątki |
| Wspólna kontrola zajętości osoby dla różnych ofert i profili | Potwierdzenie spotkania blokuje nakładające się przedziały u tej samej osoby, niezależnie od kategorii oferty i liczby jej profili | 4, 6–8: ograniczenia spójności, transakcje i równoczesne operacje |
| Różne długości usług i dopasowanie terminów | Konsultacja może trwać 60 minut, medytacja 120, a zajęcia oddechowe 30; system proponuje starty, dla których cały czas zajętości mieści się w grafiku i nie koliduje z innymi spotkaniami; długość usługi nie musi oznaczać takiego samego odstępu między proponowanymi startami | 3–4, 6–7: reguły czasu, przedziały, walidacja i konflikty rezerwacji |
| Przerwy i zachowanie ustalonego czasu | Możliwe rozszerzenie: czas na przygotowanie lub przejazd blokuje dodatkowy fragment grafiku; zmiana długości oferty nie zmienia samoczynnie czasu wcześniej uzgodnionych rezerwacji; szczegółowe zasady pozostają otwarte | 3–4, 6–8: reguły biznesowe, historia ustaleń i konsekwencje zmian |
| Rezerwacja i jej cykl życia | Użytkownik wybiera ofertę, czas i termin, widzi stan zgłoszenia oraz wynik potwierdzenia; zasady automatycznej lub ręcznej akceptacji pozostają do ustalenia | 3–4, 6–8: reguły, stany, kontrakt operacji, testowanie ważnych zachowań |
| Propozycja przełożenia | Jedna strona proponuje nowy termin, druga akceptuje albo odrzuca; można przyjąć regułę, że do akceptacji obowiązuje pierwotny termin | 3–4, 6–8, 10: proces uzgodnienia i atomowa zmiana zobowiązania |
| Anulowanie i historia ustaleń | Strona anuluje według ustalonych zasad; system zapisuje kto i kiedy wykonał zmianę oraz zachowuje wcześniejsze ustalenia | 3–4, 6–8: dozwolone przejścia, autoryzacja i zachowanie historii |
| Czasowe wstrzymanie wybranego terminu | Po wybraniu terminu jest on przez określony czas, np. 10 minut, niedostępny dla innych, jak miejsce przy zakupie biletu na pociąg lub wydarzenie; po wygaśnięciu wraca do wolnych terminów. Ma sens przy dłuższym kroku przed złożeniem rezerwacji, np. płatności online; trzeba ograniczyć blokowanie terminów przez porzucone lub powtarzane wstrzymania | 4, 7, 11: stan z wygasaniem, równoczesne operacje, zadania w tle |
| Odporność na ponowne wysłanie | Dwukrotne kliknięcie lub ponowienie po przerwie w połączeniu kończy się jednym zapisem i jednoznaczną odpowiedzią | 6–7, 10–11: idempotencja, błędy i powtórzenia |
| Terminy dla osób w różnych strefach | Spotkanie online jest poprawnie pokazane uczestnikowi i prowadzącemu także przy zmianie czasu; regularna godzina ma jasno określoną strefę | 10: daty, strefy i cykliczność |

### 5.3. Zajęcia grupowe i kursy

| Funkcjonalność | Przykładowe działanie | Co pokrywa z roadmapy |
| --- | --- | --- |
| Program, edycje i spotkania | Prowadzący publikuje kolejne edycje tego samego programu; każda ma swój harmonogram, prowadzących i zapisy; pojedyncze zajęcia stanowią prostszy wariant grupowy | 3–4, 8: pojęcia domenowe, relacje i granice odpowiedzialności |
| Zapis z limitem miejsc | Uczestnik zapisuje się, jeśli są miejsca; dwa równoczesne zgłoszenia nie mogą przekroczyć limitu | 4, 6–7: ograniczenia, transakcje i wyścigi |
| Zgłoszenie wymagające potwierdzenia | Wybrana oferta może wymagać rozmowy organizacyjnej lub akceptacji; użytkownik odróżnia zgłoszenie od potwierdzonego miejsca | 3–4, 6–8: stany, role i reguły przyjmowania |
| Lista rezerwowa i czas na odpowiedź | Po rezygnacji system proponuje miejsce oczekującej osobie; propozycja może wygasnąć, a ponowienie działania nie przyznaje miejsca drugi raz | 7, 10–11, 17: współbieżność, terminy, zadania w tle i powiadomienia |
| Zmiana spotkania lub odwołanie edycji | Organizator zmienia jedną datę albo odwołuje całą edycję; uczestnicy dostają aktualny harmonogram, a historia pozostaje spójna | 3–4, 6–8, 10–11, 16: różne zakresy zmiany i ich propagacja |

### 5.4. Miejsca i wyjazdy

| Funkcjonalność | Przykładowe działanie | Co pokrywa z roadmapy |
| --- | --- | --- |
| Oferta obiektu dla grup | Gospodarz opisuje miejsce, wyposażenie, pojemność i okresy udostępnienia; informacje o noclegach i salach mogą być doprecyzowane później | 3–4, 9: domena, relacje i dane przestrzenne |
| Uzgodnienie wykorzystania obiektu | Organizator wysyła zapytanie, strony ustalają zakres i okres, a potwierdzenie respektuje regułę wyłączności lub współdzielenia miejsca | 3–4, 6–8: negocjowany proces, stany i konflikty okresów |
| Przygotowanie i publikacja wyjazdu | Osoba odpowiedzialna za organizację łączy miejsce, prowadzących, program i terminy; warunki publikacji wymagają ustalenia | 3–4, 6–8: odpowiedzialności i zależności pomiędzy procesami |
| Zapisy i zmiany wyjazdu | Uczestnik zgłasza udział; organizator zarządza limitem i informuje o zmianie miejsca lub terminów; rezerwacja domu jest odróżniona od zapisu osoby | 4, 6–11, 16–17: spójność, lokalizacja, harmonogram i komunikacja |

### 5.5. Wyszukiwanie i odkrywanie ofert

| Funkcjonalność | Przykładowe działanie | Co pokrywa z roadmapy |
| --- | --- | --- |
| Łączenie filtrów i przeglądanie wyników | Użytkownik łączy obszar oferty, profesję, rodzaj spotkania, odbiorców, cenę, termin i formę; wybiera sortowanie i przegląda kolejne części wyników | 4, 7, 13, 15: zapytania, relacje, paginacja i pomiary |
| Wyszukiwanie w promieniu | Użytkownik znajduje gabinety, studia lub obiekty w zadanej odległości i łączy to z innymi filtrami; odległość nie jest opisana jako czas dojazdu | 9, 13: znaczenie obliczeń przestrzennych i ich wydajność |
| Wyszukiwanie po tekście i nazwach | Wyszukiwarka rozpoznaje uzgodnione skróty i pełne nazwy, np. CBT i terapia poznawczo-behawioralna, oraz przeszukuje publiczne opisy ofert | 4, 13, 15: wyszukiwanie tekstowe, ranking i porównanie metod |
| Obserwowanie ofert i kryteriów | Użytkownik zapisuje ulubione oferty albo warunki wyszukiwania i może dostać informację o nowej edycji, terminie lub miejscu | 4, 6, 11, 17: relacje, preferencje i kierowanie powiadomień |
| Szybkie i aktualizowane listy ofert | Często odwiedzane zestawienia mogą być przygotowywane wcześniej; zmiana, wycofanie lub ograniczenie widoczności oferty ma określony wpływ na wyniki, a przy rezerwacji ponownie sprawdza się aktualną dostępność | 13–15: pomiary, koszt przygotowania danych, nieaktualność i odbudowa wyników; uzasadnienie potrzebne po pomiarach |

### 5.6. Kalendarz, komunikacja i dostęp mobilny

| Funkcjonalność | Przykładowe działanie | Co pokrywa z roadmapy |
| --- | --- | --- |
| Dodanie spotkania do zewnętrznego kalendarza | Użytkownik upoważnia aplikację; utworzenie, przełożenie i anulowanie aktualizują wydarzenie; odłączenie konta ma określone skutki | 10: integracja, upoważnienie, cofnięcie dostępu i daty |
| Widoczny stan dodania do kalendarza | Rezerwacja jest zachowana także przy chwilowym błędzie dostawcy; użytkownik widzi, czy dodanie lub aktualizacja nadal trwa albo wymaga ponowienia; nie powstają duplikaty | 10–11: niezależne efekty, ponowienia i niejednoznaczny wynik |
| Integracja z narzędziem do spotkań online | Link do spotkania online, np. Google Meet, powstaje lub jest uzupełniany z pomocą zewnętrznego narzędzia zamiast ręcznego wklejania przez prowadzącego; sposób działania do ustalenia | 10: integracja z zewnętrznym dostawcą |
| Przypomnienia i powiadomienia o zmianach | Użytkownik wybiera rodzaje informacji i kanały, np. przypomnienie, nową edycję lub zmianę spotkania; może zrezygnować i ograniczyć szczegółowość treści | 6, 10–11, 17: preferencje, planowanie, routing i zgody |
| Wiadomości organizacyjne | Strony konkretnej rezerwacji lub współorganizatorzy prowadzą rozmowę; po powrocie do aplikacji widzą historię, a cofnięcie dostępu obowiązuje również w rozmowie | 6, 11, 16: komunikacja dwukierunkowa, historia, ponowne połączenie i autoryzacja |
| Aktualizacja otwartego panelu | Prowadzący widzi nowy zapis, a uczestnik zmianę terminu bez ręcznego odświeżania; po przerwie aplikacja odzyskuje bieżący stan | 16: aktualizacje jednokierunkowe, kolejność i odzyskiwanie widoku |
| Powiadomienie na urządzeniu | Użytkownik włącza powiadomienia, otwiera właściwe miejsce w aplikacji po kliknięciu i może się wypisać; aktualny stan jest pobierany po otwarciu | 11, 17: zadanie w tle, subskrypcja urządzenia i jej cykl życia |
| Wybrany widok bez połączenia | Ostatnio pobrany harmonogram lub szczegóły zapisu można przeczytać offline z informacją o nieaktualności; dane prywatne są usuwane z urządzenia po wylogowaniu według ustalonych zasad | 17: działanie offline, aktualizacje aplikacji i rozdzielenie danych użytkowników |

### 5.7. Widoczność, historia i zaufanie

| Funkcjonalność | Przykładowe działanie | Co pokrywa z roadmapy |
| --- | --- | --- |
| Widoczność zależna od udziału i zadania | Użytkownik widzi własny zapis, organizator swoją grupę, a gospodarz uzgodnioną logistykę; zmiana współorganizatora odbiera dostęp poprzedniej osobie | 6, 8, 14–17: autoryzacja w różnych kanałach i aktualność dostępu |
| Historia zmian i własne zestawienia | Użytkownik przegląda swoje zapisy, a prowadzący liczbę zgłoszeń, rezygnacji i zajętych miejsc; historia wskazuje autora i czas istotnej zmiany | 4, 6–7, 13: agregacje, audyt, filtrowanie i koszt zapytań |
| Publikacja po sprawdzeniu i obsługa zgłoszeń | Opcjonalny proces sprawdzenia deklarowanych kwalifikacji lub zgłoszenia dotyczącego oferty; osoba obsługująca sprawę ma dostęp właściwy do zadania | 3–4, 6–8: proces, uprawnienia, cykl życia i historia |
| Opinie po udziale | Jeżeli funkcja zostanie wybrana, zasady określają kto i kiedy może wystawić opinię, czy jest publiczna oraz jak powiązać ją z udziałem bez ujawniania zbędnych informacji | 3–4, 6–8, 15: relacje, reguły publikacji i wyszukiwanie |

### 5.8. Przyszłe płatności i abonament platformy

Obecny kierunek obejmuje organizację zapisów. Poniższe możliwości są osobnymi pomysłami na przyszłość, bez ustalonej ceny, dostawcy ani zakresu MVP.

| Funkcjonalność | Przykładowe działanie | Co pokrywa z roadmapy |
| --- | --- | --- |
| Płatność uczestnika za ofertę | Uczestnik opłaca spotkanie, kurs lub wyjazd; przyszłe zasady mogą obejmować zaliczkę, wygaśnięcie nieopłaconego miejsca i zwrot | 7, 10–11: spójność procesu, integracja, duplikaty i ponowienia |
| Abonament prowadzącego za platformę | Prowadzący opłaca dostęp np. miesięcznie; zasady określają publikację ofert, obsługę rezerwacji, wygaśnięcie, odnowienie i zmianę planu | 3–4, 6–8, 10–11: uprawnienia zależne od stanu usługi i cykliczne rozliczenia |
| Rozliczenia między stronami | Ewentualny podział wpłat między organizatora, gospodarza, prowadzących i platformę po ustaleniu modelu współpracy | Rozszerzenie o większej złożoności; 7, 10–11 i późniejsze procesy między systemami |

### 5.9. Przykład łączący kilka etapów

Organizator zmienia termin jednego spotkania kursu. Uczestnik widzi aktualny harmonogram; szczegóły oferty i wyniki wyszukiwania uwzględniają zmianę; aktualizowany jest kalendarz zewnętrzny i wysyłane wybrane powiadomienia. Otwarty panel pokazuje zmianę, a urządzenie może otrzymać powiadomienie także po zamknięciu karty.

Poszczególne efekty mogą kończyć się w różnym czasie. Użytkownik powinien móc ustalić aktualny stan, a ponowienie nie może tworzyć podwójnych zapisów ani wiadomości. Cofnięcie dostępu działa także wtedy, gdy część danych była wcześniej przygotowana do szybszego odczytu. Scenariusz daje spójny materiał do etapów 10–11 oraz 13–17 bez dodawania niepowiązanych funkcji.

### 5.10. Praktyki techniczne bez dodatkowych funkcji produktu

Logowanie błędów i śledzenie operacji, testy ważnych reguł, automatyczne sprawdzanie zmian, wdrożenia, kopie zapasowe, odtwarzanie danych i migracje są częścią pracy nad wybranymi funkcjami. Nie wymagają osobnego panelu administracyjnego. Podobnie porównanie organizacji kodu można przeprowadzić na tym samym przypadku użycia. Dotyczy to zwłaszcza etapów 5–8, 12 i 13.

Osobny silnik wyszukiwania, wcześniejsze przygotowywanie zestawień i komunikację na żywo należy oceniać względem potrzeb oraz pomiarów. Jeśli mały rzeczywisty zakres ich nie uzasadnia, można zbadać je na większych danych syntetycznych, jasno opisując ograniczenia eksperymentu. Opcjonalne laboratoria nie stają się przez to wymaganiami produktu.

## 6. Scenariusz domu na wsi

Fikcyjny scenariusz: właścicielka domu prowadzi masaże i udostępnia miejsce grupom przyjeżdżającym na zajęcia.

1. Właścicielka publikuje własne oferty masaży i ich dostępność.
2. Osobno opisuje obiekt jako miejsce możliwe do wykorzystania na pobyt grupowy.
3. Udostępnia wybrane okresy i warunki korzystania z obiektu.
4. Instruktor, gospodarz lub inny organizator inicjuje przygotowanie wyjazdu. W wariancie organizowanym przez instruktora znajduje on miejsce i kontaktuje się z gospodarzem.
5. Strony uzgadniają okres, zakres udostępnienia, pojemność i odpowiedzialności.
6. Po wymaganych potwierdzeniach powstaje konkretna edycja wyjazdu, np. tygodniowe zajęcia jogi lub medytacji.
7. Organizator publikuje opis oraz program i otwiera zapisy.
8. Uczestnicy zgłaszają udział i otrzymują potwierdzenia według ustalonych zasad.

To propozycja przebiegu do dalszego modelowania. Należy rozstrzygnąć, kto zakłada wydarzenie i czy publikacja zawsze wymaga uprzedniego potwierdzenia obiektu.

Najważniejsze rozróżnienia pojęciowe:

- Ogłoszenie dostępności obiektu nie jest jeszcze potwierdzoną rezerwacją.
- Rezerwacja obiektu przez organizatora jest innym zobowiązaniem niż zapis uczestnika na wyjazd.
- Dom, dostępny okres, program wyjazdu i konkretna edycja wydarzenia mają różne znaczenie.
- Tygodniowy pobyt jest okresem udostępnienia; zajęcia podczas pobytu mogą mieć własny harmonogram.
- Pojemność obiektu, liczba miejsc noclegowych i limit uczestników nie muszą być tą samą liczbą.

## 7. Pytania do scenariusza wyjazdowego

Pytania zapisujemy teraz, a odpowiedzi dobieramy przed realizacją odpowiedniej funkcji.

### Miejsce i dostępność

- Czy udostępniany jest cały obiekt, wybrane pokoje czy tylko przestrzeń do zajęć?
- Czy wynajem jest wyłączny, czy mogą współistnieć różne grupy?
- Czy podczas wyjazdu właścicielka nadal może przyjmować klientów indywidualnych?
- Czy zapytanie czasowo blokuje obiekt, czy dopiero potwierdzenie?
- Co dzieje się, gdy dwa zapytania dotyczą nakładających się okresów?

### Organizator i wydarzenie

- Kto publikuje wydarzenie: właściciel, instruktor czy osobny organizator?
- Czy oferta może mieć kilku prowadzących?
- Czy uczestnicy muszą mieć nocleg w obiekcie, czy mogą dojeżdżać?
- Czy zgłoszenie oznacza automatyczne przyjęcie, czy czeka na akceptację?
- Co się dzieje, gdy wyjazd zostanie odwołany lub zmieni się jego miejsce?

### Rozliczenia

- Komu uczestnik płaci za udział?
- Czy organizator rozlicza obiekt osobno, poza wpłatami uczestników?
- Czy platforma tylko przyjmuje płatność za ofertę, czy także dzieli środki między strony?
- Czy potwierdzenie miejsca zależy od zapłaty lub zaliczki?
- Jakie są zasady wygaśnięcia nieopłaconego zapisu i zwrotu po anulowaniu?

## 8. Płatności i abonament jako przyszłe kierunki rozwoju

Obecny kierunek obejmuje organizację zapisów. Nie podjęto decyzji o włączeniu płatności do realizowanego zakresu; MVP będzie ustalane później.

Rozróżniamy dwa niezależne pomysły: uczestnik płaci za konkretną usługę lub udział, a prowadzący może płacić abonament za korzystanie z platformy. Warianty mogą występować osobno albo łącznie. Abonament nie oznacza automatycznie pośredniczenia platformy w płatności za każdą wizytę.

### Płatności uczestników i rozliczenia między stronami

Jeżeli zostaną wybrane, płatności mogą zacząć się od testowego opłacania jednej rezerwacji u jednego odbiorcy. Rozliczanie uczestnika, organizatora, prowadzącego, gospodarza obiektu i platformy stanowi szerszy zakres.

Przed wyborem rozwiązania potrzebna jest odpowiedź, kto sprzedaje daną ofertę i komu należą się środki. Narzędzia dla platform, np. Stripe Connect, opisują odrębne mechanizmy przyjmowania płatności i wypłat dla usługodawców. To przykład do przyszłego porównania, a nie wybrany dostawca [3].

Warto zachować pojęciową różnicę między ustaloną ceną, zapisem lub rezerwacją, próbą zapłaty, potwierdzeniem płatności i ewentualnym zwrotem. Aktualizacja cennika oferty nie powinna przypadkowo zmieniać wcześniej uzgodnionej kwoty.

Potencjalne ćwiczenia: ponowiona próba zapłaty, powtórzone lub opóźnione zdarzenie operatora, płatność potwierdzona po wygaśnięciu miejsca, częściowy sukces procesu i ponowienie zadania. Webhooki umożliwiają odbieranie asynchronicznych zdarzeń operatora; ich obsługa wymaga uwzględnienia m.in. duplikatów i kolejności [4].

Zakres płatności, opłaty dostawcy, dostępność funkcji oraz warunki rzeczywistego uruchomienia wymagają sprawdzenia przy wyborze integracji. Pracę edukacyjną można rozpocząć od symulacji, a potem środowiska testowego wybranego operatora.

### Abonament za korzystanie z platformy

Prowadzący mógłby opłacać np. miesięczny dostęp do publikowania ofert lub obsługi rezerwacji. Nie ustalono ceny, planów ani zakresu płatnych możliwości. To pomysł na ewentualną monetyzację, poza obecnym zakresem organizacji zapisów i bez decyzji o MVP.

Pytania do przyszłego modelowania: czy abonament dotyczy osoby, organizacji czy kilku współpracowników; które możliwości obejmuje; co następuje po nieudanym odnowieniu lub rezygnacji; jak traktować istniejące rezerwacje i dostęp uczestników po wygaśnięciu abonamentu. Cofnięcie możliwości publikowania nowych ofert nie musi oznaczać odebrania dostępu do wcześniej umówionych spotkań — potrzebna jest jawna decyzja produktowa.

## 9. Jak wykorzystywać przyszłe scenariusze przy projektowaniu bazy

Lista przyszłych możliwości pomaga wykryć założenia, które już teraz są sprzeczne z wizją aplikacji. Nie wymaga tworzenia wszystkich przyszłych tabel i mechanizmów. Projektowanie ewolucyjne opiera się również na migracjach i kontrolowanej zmianie istniejących danych [1].

| Przyszły scenariusz | Zbyt wąskie założenie do zakwestionowania | Co rozważyć przy obecnym modelowaniu |
| --- | --- | --- |
| Właściciel udostępnia dom, instruktor prowadzi zajęcia | Każda oferta ma jedną osobę pełniącą wszystkie funkcje | Znaczenie prowadzącego, organizatora i właściciela miejsca |
| Jedna osoba publikuje różne oferty i sama uczestniczy w innych | Konto ma na zawsze jedną wyłączną rolę | Czy role dotyczą konta, konkretnej oferty lub wydarzenia |
| Instruktor prowadzi zajęcia w kilku miejscach | Osoba i jedyny adres jej gabinetu to nierozdzielna całość | Związek między osobą, ofertą i miejscem realizacji |
| Kurs ma kilka spotkań i kolejne edycje | Nazwa kursu, jedna data i jedna lista zapisów wystarczają do wszystkiego | Różnica między programem, konkretną edycją i jej spotkaniami |
| Organizator rezerwuje dom, a uczestnik miejsce w grupie | Każda rezerwacja ma identyczną jednostkę i regułę pojemności | Co jest rezerwowane i jaka reguła ma pozostać prawdziwa |
| Płatność może być ponowiona, a potem zwrócona | Jedno pole „opłacone” opisuje cały proces | Rozdzielenie znaczenia potwierdzonego udziału i przepływu płatności |

To pytania o znaczenie danych, nie gotowy schemat. Sposób reprezentacji należy ocenić na podstawie wybranego MVP i pierwszych scenariuszy. Przyszłe potrzeby mogą uzasadniać małą zmianę o niskim koszcie już teraz, ale kosztowne mechanizmy rozszerzalności również mają cenę utrzymania [2].

Praktyczny sposób pracy nad każdą decyzją:

1. Opisać obecny przypadek użycia i jego reguły.
2. Sprawdzić model na dwóch lub trzech konkretnych przyszłych scenariuszach.
3. Wskazać, jakie założenie utrudniłoby ich dodanie i dlaczego.
4. Porównać małą zmianę dzisiaj z późniejszą migracją.
5. Zapisać decyzję, koszt i warunek ponownego rozważenia; ważne granice omówić z Mikołajem.

Pożądaną cechą jest możliwość rozsądnej zmiany modelu z zachowaniem danych i reguł. Refaktoryzacja oraz migracja są normalną częścią rozwoju. Nie ma gwarancji obsłużenia nieznanych przyszłych wymagań bez zmian.

## 10. Wybór MVP odłożony do późniejszej decyzji

Temat projektu jest wybrany, a obecnie trwa burza mózgów nad pulą funkcjonalności. Nie wybieramy jeszcze procesu ani listy funkcji do MVP i nie przypisujemy nowych pomysłów do kolejności wdrożenia.

Po zebraniu propozycji będzie można porównać małe, kompletne procesy, np. rezerwację spotkania, zapis na edycję kursu albo uzgodnienie obiektu i zapis na wyjazd. Ostateczny zakres będzie wynikać z decyzji autorki, a nie z samej obecności funkcji w tym opisie.

Zakres pierwszej funkcji od UI do bazy może być mniejszy niż cała pierwsza wersja. MVP nie wymaga ukończenia wszystkich etapów roadmapy. Znajomość szerszej wizji nadal ma wspierać sprawdzanie założeń podczas późniejszego modelowania.

## 11. Źródła danych i symulacja

- Seeder może generować fikcyjnych specjalistów, instruktorów, klientów, obiekty, oferty, terminy, kursy i wyjazdy.
- Początkowe lokalizacje mogą mieć przygotowane współrzędne; geokodowanie jest późniejszą integracją.
- Scenariusz domu na wsi jest fikcyjny i nie zakłada rzeczywistego klienta.
- Testowe kwalifikacje i opisy profili muszą być rozpoznawalne jako fikcyjne. Nie ma potrzeby pobierania katalogu rzeczywistych specjalistów.
- Konflikty trzeba również odtwarzać operacjami: równoczesnymi zapisami, zmianą terminu, anulowaniem, ponowieniem i restartem workera. Same gotowe rekordy nie sprawdzają zachowania procesu.
- Dostawcę kalendarza i operatora płatności można początkowo zastąpić symulacją, a właściwe integracje dodać przy odpowiednich etapach nauki.

Pozyskanie rzeczywistych użytkowników nie jest warunkiem realizacji projektu edukacyjnego. Ewentualna walidacja popytu i komercjalizacja są osobnymi decyzjami.

## 12. Powiązanie z roadmapą

| Etap | Przykładowe zastosowanie |
| --- | --- |
| 3–4. Domena i SQL | Rozróżnienie osoby, roli, oferty, edycji, harmonogramu, miejsca i udziału; słownik, relacje i ograniczenia |
| 5. Stos, szkielet i środowisko Claude Code | Przygotowanie repozytorium, świadomy wybór stosu, odtwarzalne środowisko, podstawowe CI i zasady pracy z AI; te praktyki wspierają projekt i nie wymagają osobnej funkcji produktu |
| 6. Pełna funkcja i uprawnienia | Rezerwacja lub zapis od formularza do bazy; dostęp klienta, prowadzącego, współorganizatora i gospodarza według zadania |
| 7. Spójność i współbieżność | Wspólna dostępność osoby o kilku profesjach, ostatnie miejsce w grupie, nakładające się okresy udostępnienia domu, równoczesne anulowanie i potwierdzenie |
| 8. DDD i VSA | Porównanie organizacji kodu dla wybranego przypadku, np. potwierdzenia udziału; granice reguł i odpowiedzialności |
| 9. PostGIS | Gabinety, studia i obiekty wyjazdowe w promieniu; połączenie lokalizacji z filtrami oferty |
| 10. Kalendarz i integracje | Publikacja spotkania u jednego dostawcy, zmiana terminu i anulowanie; opcjonalnie w przyszłości płatności uczestnika lub abonament prowadzącego |
| 11. Kolejki i niezawodność | Niezależne zadania synchronizacji i powiadomień; powtórzenia, błędy i zapis zamiaru wykonania zadania |
| 12. Wdrożenia | Uruchamianie aplikacji, bazy i workera, CI/CD, logi, backup i kontrolowane zmiany |
| 13–14. Pomiary i cache | Wygenerowany katalog i obciążenie; pomiar kosztownych zapytań, potem ocena buforowania oraz jego nieaktualności |
| 15. Wyszukiwarka | Porównanie wyszukiwania PostgreSQL z odtwarzalnym indeksem ofert; filtrowanie i aktualizacja dostępności |
| 16. Komunikacja na żywo | Aktualizacja stanu zapisu lub wiadomości organizacyjne; porównanie SSE i WebSocket według kierunku komunikacji |
| 17. PWA i Web Push | Wybrany harmonogram offline, preferencje powiadomień, informacja o zmianie spotkania lub zwolnieniu miejsca |
| 18. Laboratoria porównawcze | Ten sam przypadek przez REST i GraphQL; małe porównania modeli danych, Kafka, gRPC i serverless |
| 19. Kubernetes — opcjonalnie | Osobne laboratorium wdrożenia backendu i workera; nie jest wymaganiem funkcjonalnym aplikacji |

Naturalne w projekcie są reguły zapisów, kalendarze, uprawnienia, lokalizacja i powiadomienia. Osobny silnik wyszukiwania, współdzielony cache i warmowanie wymagają uzasadnienia. Laboratoria porównawcze nie muszą stać się zależnościami głównej aplikacji.

## 13. Najważniejsze ryzyka i granice

- Zbyt szerokie MVP obejmujące od razu wizyty, kursy, nieruchomości, noclegi i płatności.
- Zacieranie różnicy między charakterem ofert i kwalifikacjami prowadzących.
- Rozbudowanie procesu rezerwacji o dokumentację kliniczną lub własne wideorozmowy, które stanowią osobne duże zakresy.
- Traktowanie wolnego obiektu jako automatycznej gwarancji miejsc dla uczestników.
- Zależności między dostępnością obiektu, prowadzącego i harmonogramem wydarzenia.
- Cykliczność, wyjątki i zmiany w już potwierdzonych zobowiązaniach.
- Ujawnienie informacji o udziale przez publiczną listę, opinię, powiadomienie lub eksport do kalendarza.
- Zbyt ogólny model, w którym różne procesy trafiają do jednej struktury i tracą czytelne reguły.
- Budowanie hipotetycznych mechanizmów przed poznaniem ich wymagań.

Migracje schematu i danych, testy istotnych reguł oraz krótkie zapisy decyzji mają towarzyszyć rozwojowi. Refaktoryzacja nie oznacza automatycznie błędnego pierwszego projektu.

## 14. Dalsza praca nad wybranym tematem

1. Rozwijać pulę funkcjonalności i zbierać konkretne scenariusze, bez wybierania teraz MVP.
2. Zachować pytania o organizację wyjazdów i widoczność danych; rozstrzygać je wtedy, gdy będą potrzebne do odpowiedniego przypadku użycia.
3. Po zakończeniu burzy mózgów osobno wybrać mały zakres pierwszej wersji i doprecyzować jego użytkowników, czynności oraz dane.
4. W kolejnych etapach samodzielnie szkicować reguły, model i bazę, sprawdzać je na przyszłych scenariuszach oraz omawiać decyzje z AI i Mikołajem.

## Źródła do decyzji technicznych

1. Pramod Sadalage i Martin Fowler, [Evolutionary Database Design](https://martinfowler.com/articles/evodb.html) — rozwój bazy przez migracje, kontrolowane zmiany i wersjonowanie.
2. Martin Fowler, [Yagni](https://martinfowler.com/bliki/Yagni.html) — koszty implementowania przyszłych możliwości i rozważania małych zmian ułatwiających późniejszą rozbudowę.
3. Stripe, [Connect](https://docs.stripe.com/connect) — przykład obsługi płatności i rozliczeń wielu stron platformy; dostawca nie został wybrany.
4. Stripe, [Webhooks](https://docs.stripe.com/webhooks) — asynchroniczne zdarzenia operatora i wymagania ich obsługi.
5. BookRetreats, [How to Run a Retreat](https://bookretreats.com/blog/how-to-run-a-retreat/) — przykłady współpracy osoby organizującej z obiektem i innymi prowadzącymi; opis nie przesądza modelu naszej aplikacji.
6. Mary & Joseph Retreat Center, [Group Retreat Inquiry Form](https://maryjoseph.secure.retreat.guru/rental/inquire) — przykład osobnego zapytania organizatora grupy do gospodarza miejsca.

Opis produktu nie zawiera pełnego schematu bazy ani wyboru operatora płatności.
