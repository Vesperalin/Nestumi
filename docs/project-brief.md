# Nestumi — wybór tematu i zakres pierwszej wersji

## 1. Wybrany temat, użytkownicy i problem

**Nestumi** to robocza nazwa platformy umożliwiającej wyszukiwanie i porównywanie ofert zdrowia psychicznego oraz dobrostanu, a następnie rezerwowanie spotkań i zarządzanie zapisami. W pierwszej wersji obsługiwane są spotkania indywidualne. Kursy, zajęcia grupowe i wyjazdy pozostają kierunkami rozwoju.

Osoba szukająca oferty chce znaleźć właściwego specjalistę lub prowadzącego, sprawdzić charakter usługi, kwalifikacje, warunki i dostępność, a następnie zarezerwować spotkanie i zarządzać swoim zapisem. Prowadzący chce publikować oferty, udostępniać terminy oraz obsługiwać rezerwacje.

Pomoc psychologiczna i psychiatryczna jest wyraźnie odróżniana od praktyk dobrostanu, takich jak joga, medytacja, techniki oddechowe czy masaż. Jedna osoba może mieć wiele profesji i kwalifikacji oraz publikować różne oferty. Przy każdej ofercie ma być czytelne, jaki charakter ma usługa i w jakiej roli występuje prowadzący.

Projekt jest autorski i służy nauce fullstacka. Jego realizacja nie wymaga klienta, rzeczywistych usługodawców ani komercjalizacji. UI pozostaje ograniczone do obsługi ćwiczonych funkcji; nauka nie ma narzuconego harmonogramu.

## 2. Trzy główne czynności użytkownika

| Osoba szukająca oferty | Osoba publikująca ofertę |
| --- | --- |
| **1. Znaleźć i porównać oferty** według potrzeb, np. rodzaju usługi, kwalifikacji, miejsca i terminu. | **1. Przygotować i opublikować ofertę**, określając charakter usługi, prowadzącego i warunki skorzystania. |
| **2. Zarezerwować spotkanie lub zgłosić udział** i sprawdzić, czy zapis jest potwierdzony. W pierwszej wersji dotyczy to spotkań indywidualnych. | **2. Ustalić dostępność i harmonogram**; w przyszłych ofertach grupowych również liczbę miejsc. |
| **3. Zarządzać swoim zapisem:** sprawdzać szczegóły i zmiany, skontaktować się organizacyjnie albo zrezygnować. | **3. Obsługiwać rezerwacje i zapisy:** zarządzać zgłoszeniami, zmianami i informowaniem uczestników. |

To czynności w ogólnej wizji produktu. Ich zakres w pierwszej wersji określa następna sekcja; nie obejmuje ona jeszcze komunikatora ani procesu przekładania spotkań.

## 3. Zakres pierwszej wersji

**Główny proces:** prowadzący publikuje ofertę i dostępność, uczestnik znajduje ofertę i rezerwuje termin, a obie strony mogą sprawdzić spotkanie oraz je anulować.

| Obszar | Zakres |
| --- | --- |
| Oferty prowadzącego | Dodanie i publikacja oferty z opisem, charakterem usługi, ceną, czasem trwania oraz formą online lub miejscem spotkania. Cena jest informacją; aplikacja nie pobiera płatności. |
| Grafik na konkretne tygodnie | Ustawianie przedziałów dostępności dla poszczególnych dni oraz kopiowanie grafiku na wybrane tygodnie. Przykładowo można przygotować najbliższych pięć tygodni; liczba pięć nie jest ustalonym limitem. |
| Katalog ofert | Przeglądanie szczegółów, podstawowe filtry, np. rodzaj usługi i forma spotkania, oraz podział wyników na strony. |
| Rezerwacja | Wybór oferty i terminu; automatyczne potwierdzenie, jeżeli cały czas spotkania nadal jest dostępny. |
| Wspólna kontrola zajętości | Spotkania tej samej osoby nie mogą się nakładać pomiędzy jej różnymi ofertami, niezależnie od ich kategorii i późniejszego wyboru liczby profili. |
| Moje spotkania i anulowanie | Uczestnik i prowadzący widzą związane z nimi rezerwacje oraz mogą je anulować. Anulowanie zwalnia termin, a historia rezerwacji pozostaje. |
| Konta i dostęp | Logowanie, wylogowanie, wygasanie sesji i uprawnienia do własnych ofert lub rezerwacji. Początkowo można korzystać z przygotowanych kont testowych. |
| Odporność na ponowienie | Podwójne kliknięcie lub ponowne wysłanie tego samego żądania po problemie z połączeniem nie tworzy drugiej rezerwacji. |

### Uproszczenia przyjęte na początek

- Jedna oferta ma jedną ustaloną długość spotkania. Różne oferty mogą trwać np. 30, 60 lub 120 minut; są to przykłady, nie standardy narzucone dziedzinie.
- Rezerwacja jest potwierdzana automatycznie; nie czeka na ręczną akceptację prowadzącego.
- Grafik dotyczy konkretnych dat. Kopiowanie na wybrane tygodnie nie oznacza stałej reguły „każdy poniedziałek w przyszłości”. Reguły cykliczne z wyjątkami pozostają rozszerzeniem.
- Dostępność musi pomieścić cały czas spotkania. Medytacja 10:00–12:00 koliduje z zajęciami oddechowymi 11:30–12:00, mimo różnych godzin rozpoczęcia.
- Kopiowanie lub zmiana grafiku musi respektować istniejące rezerwacje. Szczegółowe zasady tych zmian doprecyzujemy podczas modelowania domeny.

### Poza pierwszą wersją

Kursy i zajęcia grupowe, wyjazdy i udostępnianie obiektów, płatności i abonamenty, przełożenie spotkania, stałe reguły cykliczne i rozbudowane wyjątki, zewnętrzny kalendarz, wyszukiwanie w promieniu, komunikator, rozbudowane powiadomienia oraz działanie offline.

## 4. Źródło danych i symulacja

Początkowe dane są fikcyjne i generowane seederem: użytkownicy, kwalifikacje, oferty, lokalizacje, dostępność i rezerwacje. Dane można również dodawać i zmieniać przez aplikację na kontach testowych. Nie jest potrzebny zewnętrzny katalog specjalistów ani ręczne zebranie dużej bazy ofert.

Dane mają obejmować konkretne scenariusze, a nie tylko losowe rekordy: osobę o kilku profesjach i ofertach o różnych długościach, wolne i zajęte terminy oraz anulowane rezerwacje. Przyszłe rozszerzenia mogą korzystać z fikcyjnych kursów, obiektów i uczestników, w tym kursu z ostatnim wolnym miejscem.

Konflikty sprawdzamy także przez wykonywanie operacji: równoczesne próby rezerwacji, anulowanie i ponowienie żądania. Same gotowe rekordy nie potwierdzają poprawności procesu. Początkowe lokalizacje mogą mieć przygotowane współrzędne. Integracja z kalendarzem jest osobnym rozszerzeniem, a nie źródłem katalogu ofert.

## 5. Wartość edukacyjna pierwszej wersji

| Etap | Materiał do nauki w Nestumi |
| --- | --- |
| **Modelowanie domeny i wymagań** | Znaczenie osoby, kwalifikacji, oferty, dostępności i rezerwacji; reguły kolizji, stany i anulowanie. |
| **Relacyjna baza i SQL** | Relacje i ograniczenia, daty i przedziały, historia, zapytania katalogu i list spotkań, filtrowanie i agregacje. |
| **Stos, szkielet i środowisko Claude Code** | Przygotowanie repozytorium i środowiska, wybór narzędzi, podstawowe CI i świadoma współpraca z AI. Nie wymaga dodatkowej funkcji produktu. |
| **Kompletna funkcjonalność fullstackowa** | Rezerwacja od UI do bazy, kontrakt API, walidacja, logowanie, sesje, uprawnienia, błędy, testy i logi. |
| **Spójność, współbieżność i wydajność danych** | Równoczesne rezerwacje i ponowienia, transakcje, analiza zapytań, paginacja i indeksy; osobne ćwiczenia migracji, backupu i odtworzenia. |
| **DDD, VSA i wzorce** | Organizacja kodu rezerwacji i anulowania, wspólna reguła zajętości, porównanie sposobów organizacji kodu przy zmianie wymagania. |
| **Wdrożenia** | Uruchamianie i wydawanie aplikacji, CI/CD, konfiguracja, diagnozowanie awarii i kontrolowane zmiany. |
| **Pomiary i optymalizacja** | Większy wygenerowany katalog i obciążenie; pomiary wyszukiwania oraz rezerwacji przed optymalizacją i po niej. |

## 6. Naturalne rozszerzenia i dalsza nauka

Poniższe możliwości nie powiększają zatwierdzonego zakresu pierwszej wersji.

| Rozszerzenie | Funkcjonalność i powiązanie z roadmapą |
| --- | --- |
| Lokalizacja | Wyszukiwanie ofert stacjonarnych w promieniu od wybranego punktu, połączone z innymi filtrami. Odległość geograficzna nie oznacza czasu dojazdu. |
| Zmiana terminu i kalendarz zewnętrzny | Utworzenie, zmiana i anulowanie wydarzenia oraz widoczny stan synchronizacji. Pierwsza integracja: jeden dostawca, kierunek Nestumi → kalendarz. Dostawca i strona podłączająca kalendarz pozostają do wyboru. |
| Zadania w tle i powiadomienia | Potwierdzenia, przypomnienia i synchronizacja kalendarza z obsługą błędów, ponowień i różnych skutków jednej zmiany.|
| Przyspieszanie odczytów | Cache i wcześniejsze przygotowywanie wybranych danych po pomiarach, również na sztucznym obciążeniu. Rozszerzenie edukacyjne wymagające uzasadnienia. |
| Wyszukiwanie tekstowe | Przeszukiwanie opisów i łączenie wyników z filtrami; porównanie metod oraz odtwarzanie indeksu. Funkcja jest naturalna, osobny silnik wymaga świadomej decyzji. |
| Aktualizacje na żywo | Aktualna dostępność i zmiany spotkań bez ręcznego odświeżania. Mała rozmowa organizacyjna może osobno posłużyć do ćwiczenia komunikacji dwukierunkowej. |
| PWA i Web Push | Podgląd wcześniej pobranego harmonogramu offline, oznaczenie nieaktualności i powiadomienia o zmianach. |

Szersza wizja obejmuje kursy, wyjazdy, gospodarzy obiektów i organizatorów, a potencjalnie także płatności uczestników, rozliczenia między stronami i osobny abonament prowadzących za platformę. Nie trzeba ich dodawać, żeby ćwiczyć większość roadmapy na procesie spotkań indywidualnych.

## 7. Najważniejsze ryzyka i otwarte decyzje

| Ryzyko | Przyjęte podejście |
| --- | --- |
| Rozrastanie się zakresu | Pierwsza wersja pozostaje przy spotkaniach indywidualnych. Pozostałe możliwości są wizją rozwoju. |
| Błędy w dostępności | Sprawdzamy różne długości, kolizje między ofertami, równoczesne operacje, ponowienia i wpływ kopiowania grafiku na istniejące rezerwacje. |
| Dostęp do cudzych danych | Publiczne są informacje przeznaczone do publikacji. Szczegóły rezerwacji widzą wyłącznie uprawnione osoby. |
| Mylący charakter oferty | Pomoc psychologiczna i psychiatryczna jest wyraźnie odróżniona od praktyk dobrostanu, również u tej samej osoby. |
| Zbyt proste dane testowe | Seeder obejmuje przypadki problematyczne, a poprawność procesu sprawdzamy również operacjami. |

**Liczba profili zawodowych w jednym koncie pozostaje do rozstrzygnięcia podczas modelowania domeny. Niezależnie od wybranego wariantu wszystkie oferty tej samej osoby podlegają wspólnej kontroli zajętości.**
