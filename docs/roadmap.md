# Roadmapa rozwoju: frontend → fullstack

**Wersja 3.2 · 25.10.2026 · środowisko projektu i Claude Code do nauki**

Plan obejmuje fundamenty backendu, projektowanie danych i rozwój własnej aplikacji, a następnie zagadnienia optymalizacji i komunikacji wskazane przez doświadczonego developera. Alternatywne technologie oraz Kubernetes mają osobne, opcjonalne laboratoria. Szczegółowe lekcje i zadania będą powstawały dopiero przy realizacji danego etapu.

## Cel i punkt wyjścia

Cel: samodzielnie projektować, implementować i diagnozować funkcjonalności fullstackowe, ze szczególnym naciskiem na model domeny, bazy danych i świadome decyzje projektowe. AI ma wspierać rozumienie i wykonanie pracy, ale nie zastępować samodzielnego myślenia.

Punkt wyjścia: około 4 lata doświadczenia frontendowego, inżynierka z informatyki stosowanej i magisterka z inżynierii zarządzania, specjalność zarządzanie projektami. W pracy mam kontakt z backendem w Node.js / TypeScript. Własny projekt pozwala mi systematycznie zbudować podstawy: endpointy, SQL i projektowanie tabel.

## Założenia nauki

- Brak terminów i ram czasowych. O przejściu dalej decyduje opanowanie umiejętności.
- Teoria przeplata się z małymi eksperymentami i rozwojem własnego projektu.
- Projekt jest autorski, bez klienta. Potrzeby, reguły i zakres określa jego autorka; może być też główną użytkowniczką.
- Stos bazowy: Node.js, TypeScript, Express, PostgreSQL; później PostGIS i potrzebne integracje.
- Początkowa architektura: modularny monolit i jedna główna baza. Frontend oparty na znanym React; wariant stosu wybieram świadomie w etapie 5. UI pozostaje ograniczone do obsługi ćwiczonych funkcji.
- DDD obejmuje język, reguły i granice modelu. Projektowanie tabel jest częścią tej pracy, nie całym DDD.
- Git, debugowanie i testowanie ważnych zachowań towarzyszą nauce od początku. Zaawansowane zagadnienia pojawiają się później.
- Dodatkowe narzędzia można poznawać w osobnych laboratoriach; nie trzeba umieszczać ich wszystkich w głównej aplikacji.

## Kolejność, zależności i priorytety

| Część                                            | Rola i kolejność                                                                                                                                                                                                                                                          |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1–8: fundamenty**                              | Realizuję w podanej kolejności. Temat projektu wybieram w etapie 2, po małym ćwiczeniu backendowym. Etap 5 przygotowuje repozytorium, stos i środowisko pracy z AI; po etapie 6 mam pierwszą działającą funkcję.                                                          |
| **9–11: rozszerzenia projektu**                  | Geolokalizacja i kalendarz wynikają z moich zainteresowań. Etapy 9 i 10 można zamienić kolejnością. Kolejki ćwiczę po integracji, gdy mam konkretne zadanie do wykonania w tle.                                                                                           |
| **12: uruchamianie i wydawanie aplikacji**       | Pełny etap po 11; podstawy Git, kontener do bazy i prosty CI pojawiają się wcześniej. Pierwsze wdrożenie można wykonać już po 6, wracając do niego wraz z rozwojem aplikacji.                                                                                             |
| **13–17: pogłębienie zagdanień** | Najpierw pomiary (13), potem cache (14). Wyszukiwarka (15) wymaga podstaw danych i kolejek (7, 11); nie wymaga Redis. Komunikacja na żywo (16) i PWA/push (17) mogą być osobnymi ścieżkami po integracjach, kolejkach i wdrożeniu (10–12). Web Push nie wymaga WebSocket. |
| **18: laboratoria do wyboru**                    | GraphQL, modele danych, Kafka, gRPC i serverless. Każde ma własne warunki wejścia; numer 18 nie oznacza konieczności ukończenia etapów 1–17.                                                                                                                              |
| **19 i dalsze kierunki: horyzont rozwoju**       | Kubernetes po kontenerach, wdrożeniach i pomiarach (12–13), niezależnie od laboratoriów 18. Pozostałe tematy wybieram według potrzeb.                                                                                                                                     |

Etapy 1–12 budują pierwszą wersję aplikacji i umiejętność jej utrzymania w ćwiczonym zakresie. Etapy 13–17 pogłębiają projektowanie; nie trzeba ukończyć całego katalogu, aby zacząć podejmować zadania fullstackowe. Każde nowe narzędzie powinno odpowiadać na konkretny problem albo pozostać osobnym eksperymentem.

Kryterium ukończenia oznacza, że potrafię wyjaśnić mechanizm, wykonać ćwiczenie i zdiagnozować jego typowe błędy. Nie oznacza eksperckiego opanowania całej technologii. Decyzje dotyczące modelu danych, transakcji i granic odpowiedzialności warto dodatkowo poddać przeglądowi doświadczonego developera.

## Etapy

### 1. Podstawy backendu w Node.js

- **Zakres:** Node.js jako proces i środowisko serwerowe; uruchamianie TypeScriptu, moduły i konfiguracja; droga żądania od adresu URL przez DNS i port do procesu; HTTP, routing i middleware Expressa; async/await i podstawy event loop; walidacja wejścia, obsługa błędów, logi i debugger.
- **Praktyka:** małe API przechowujące dane w pamięci: lista, odczyt rekordu, dodawanie, walidacja i wspólna obsługa błędów. Bez bazy, Dockera i rozbudowanego UI.
- **Kryterium ukończenia:** potrafię prześledzić żądanie, wyjaśnić odpowiedź i znaleźć przyczynę błędu. Rozumiem różnicę między typami TypeScript a walidacją danych w czasie działania.

### 2. Wymyślenie i wybór tematyki projektu

- **Zakres:** problem użytkownika, wartość aplikacji, realny zakres pierwszej wersji i możliwości późniejszej rozbudowy.
- **Praktyka:** porównuję własne pomysły i wybieram jeden. Zapisuję: dla kogo jest aplikacja, jaki problem rozwiązuje, trzy główne czynności użytkownika, źródło danych oraz możliwe rozszerzenia o lokalizację i kalendarz. Dane początkowo mogą być symulowane. Zakładam repozytorium Git na notatki, decyzje i późniejsze migracje; pełny setup przygotowuję w etapie 5.
- **Kryterium ukończenia:** mam krótki opis projektu i mały zakres pierwszej wersji. Temat pozwala ćwiczyć relacje danych, reguły biznesowe i integracje. Nie projektuję jeszcze całej architektury ani wszystkich tabel.

### 3. Modelowanie domeny i wymagań

- **Zakres:** przypadki użycia / user stories, wspólny język, reguły biznesowe, cykle życia i stany obiektów, podstawy bounded contexts.
- **Praktyka:** tworzę słownik pojęć, scenariusze użytkownika, reguły oraz dozwolone i niedozwolone zmiany stanu. Samodzielnie podejmowane decyzje produktowe zapisuję jako założenia.
- **Kryterium ukończenia:** potrafię wyjaśnić działanie systemu bez odwoływania się do technologii i podać przykłady naruszenia ważnych reguł.

### 4. Projektowanie relacyjnej bazy i SQL

- **Zakres:** relacje, klucze, normalizacja, typy danych, NULL, ograniczenia spójności, polityka usuwania danych; JOIN, agregacje, podzapytania i CTE. Podstawy migracji.
- **Praktyka:** projektuję schemat PostgreSQL na podstawie scenariuszy, tworzę tabele i dane testowe, piszę zapytania odpowiadające na pytania użytkownika. Sprawdzam odrzucanie niepoprawnych danych. Na tym etapie uruchamiam bazę przez Docker Compose i poznaję podstawy portów, konfiguracji i wolumenów. Pierwsze ćwiczenia wykonuję w SQL, przed ORM-em.
- **Kryterium ukończenia:** umiem uzasadnić relacje i ograniczenia, odtworzyć schemat migracjami i napisać podstawowe zapytania bez generowania całego rozwiązania przez AI.

### 5. Dobór stosu, szkielet projektu i środowisko Claude Code

**Cel:** przygotować odtwarzalne środowisko fullstackowe oraz świadomy sposób pracy z AI, dostosowany do nauki i potrzeb wybranego projektu. Konfiguracja Claude Code jest osobną kompetencją do przećwiczenia, a nie tylko dodatkiem do instalacji bibliotek.

**5A. Repozytorium, stos i narzędzia**

- **Zakres:** GitHub, branch → PR → review → merge; jedno repo z frontendem i backendem, podstawy workspaces, wersja Node.js, jeden menedżer pakietów i lockfile. README, konfiguracja środowiskowa, `.env.example` i sekrety poza repozytorium. TypeScript strict, linter i formatter, narzędzia testowe oraz skrypty `dev`, `lint`, `format`, `typecheck`, `test` i `build`.
- **Wybór stosu:** porównuję 2–3 warianty według wymagań i celów nauki. Punkt wyjścia: Express + TypeScript oraz React + Vite; rozważam TanStack Router, TanStack Query i Tailwind. Rozróżniam Router/Query od pełnego frameworka TanStack Start. Next.js lub Start wybieram, jeśli potrafię uzasadnić ich dodatkowe mechanizmy i odpowiedzialność względem Expressa. Decyzję zapisuję w krótkim ADR; wybieram też bibliotekę walidacji, sposób dostępu do DB i migracji, zachowując SQL z etapu 4.
- **Praktyka:** przygotowuję szkielet, połączenie z PostgreSQL oraz podstawowe CI w GitHub Actions. Instaluję zależności potrzebne teraz; dalsze technologie dochodzą przy odpowiednich etapach. Rozumiem działanie wygenerowanej konfiguracji i skryptów.

**5B. Claude Code jako środowisko pracy i nauki**

- **Koncepcje i konfiguracja:** `CLAUDE.md`, reguły projektu i katalogów, skills/komendy użytkownika, subagenci, hooki oraz ustawienia i uprawnienia narzędzi. Dobieram mechanizm do zadania: procedura nie zawsze wymaga osobnego agenta. Zapisuję kontekst domeny, komendy, konwencje, cele nauki i granice pomocy AI. Konfigurację projektu wersjonuję, ustawienia prywatne oddzielam.
- **Zasady współpracy:** przy nowym zagadnieniu najpierw przedstawiam własne rozumowanie. Rozróżniam tryb wskazówek od trybu wspólnej implementacji. Claude wskazuje założenia i niepewność; zmiany są małe, a wynik obejmuje uzasadnienie, diff oraz faktycznie wykonane kontrole. Rozumiem, że instrukcja w promptcie nie jest techniczną blokadą uprawnień.

| Mechanizm                     | Zadanie i oczekiwany wynik                                                                                                                                                                                                                                                                                                                                                             |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Code review                   | Reviewer analizuje wskazany diff i kontekst bez samodzielnego poprawiania kodu. Zwraca konkretne problemy z lokalizacją, skutkiem, priorytetem i sposobem weryfikacji; odróżnia błąd od sugestii stylistycznej. Sprawdza reguły, uprawnienia, SQL/transakcje i brakujące scenariusze.                                                                                                  |
| Tutor i wyjaśnianie kodu      | Wyjaśnia wskazany fragment oraz przepływ danych w repozytorium, podaje mały przykład i sprawdza moje zrozumienie pytaniem lub ćwiczeniem. Domyślnie podpowiada stopniowo, zamiast od razu podawać kompletne rozwiązanie.                                                                                                                                                               |
| Ekspert od decyzji            | Krytycznie ocenia mój model danych, kod lub ADR. Wskazuje alternatywy, kompromisy i kontrprzykłady, oddziela fakty od subiektywnej rekomendacji oraz proponuje eksperyment rozstrzygający. Opinie sprawdzam dokumentacją i pomiarami; kolejny agent nie gwarantuje niezależnej ani poprawnej oceny.                                                                                    |
| Partner do implementacji      | Na podstawie uzgodnionego celu i mojego szkicu proponuje małą zmianę, wyjaśnia nowe elementy i pomaga w implementacji. Powtarzalny kod może wykonać sam; kluczowe decyzje i pierwszy przykład nowego mechanizmu omawiamy. Na koniec potrafię samodzielnie prześledzić i zmienić rozwiązanie.                                                                                           |
| Automatyczna kontrola jakości | Hook po edycjach uruchamia formatter i bezpieczny autofix lintera dla właściwych plików. Sprawdzam także zmiany wykonane przez polecenia shellowe. Pozostałe błędy wracają do Claude z komunikatem; typecheck i wybrane testy uruchamiam na końcu zadania, pełne kontrole również w CI. Ograniczam czas i powtórzenia; hook nie ukrywa błędów ani nie uruchamia nieskończonych napraw. |

- **Dodatkowo:** przygotowuję procedurę zakończenia sesji: wykonane zmiany, decyzje, niewyjaśnione pytania i następny krok. Dobieram model i kontekst do zadania, obserwuję koszt oraz czas; nie wczytuję całej dokumentacji do każdej rozmowy. Rozdzielam uprawnienia review/wyjaśniania od implementacji i sprawdzam ich rzeczywiste działanie.
- **Sprawdzian konfiguracji:** na małej próbce z celowym błędem biznesowym i stylistycznym sprawdzam review, wyjaśnienie, implementację i automatyczne poprawki. Rejestruję przeoczenia i fałszywe alarmy. Sprawdzam również, że błąd typechecku lub testu jest widoczny, a kontrolę można uruchomić bez Claude. Część ocen biznesowych ponawiam na pierwszej funkcji z etapu 6.

**Kryterium ukończenia:** po świeżym sklonowaniu repo uruchamiam projekt według README; frontend wywołuje testowy endpoint, backend potwierdza połączenie z DB, a build i kontrole działają lokalnie oraz w CI. Potrafię wyjaśnić rolę zależności, wskazać kiedy użyć skilla, subagenta lub hooka oraz prześledzić ich działanie. Mam działające mechanizmy review, nauki, oceny decyzji, implementacji i kontroli jakości; umiem je modyfikować i opisać ich ograniczenia. Setup rozwijam wraz z projektem.

### 6. Pierwsza kompletna funkcjonalność fullstackowa

- **Wprowadzenie architektoniczne:** poznaję ideę Vertical Slice Architecture (VSA), czyli organizowania kodu wokół przypadków użycia. Odróżniam realizację funkcji od UI do bazy od świadomego zastosowania VSA; porównanie sposobów organizacji kodu wykonuję w etapie 8.
- **Zakres:** kontrakt API i podstawy OpenAPI; rozdzielenie HTTP, logiki aplikacji i dostępu do danych; exception management. Uwierzytelnianie a autoryzacja; sesja przechowywana na serwerze z identyfikatorem a samowystarczalny token, np. JWT; osobno sposób przekazania poświadczeń, np. cookie lub nagłówek Authorization. Cookies HttpOnly/Secure/SameSite, CSRF i CORS. Cykl życia sesji, wylogowanie i wygasanie; hashowanie haseł z gotową biblioteką a szyfrowanie. Zapytania parametryzowane i ochrona sekretów.
- **Praktyka:** realizuję jeden przypadek użycia od prostego UI do bazy i uzasadniam sposób logowania. Sprawdzam regułę testem jednostkowym, integrację API z testową bazą oraz najważniejszą ścieżkę przez UI. Uwzględniam błędne dane, wygasłą sesję i dostęp do cudzego zasobu. Rozszerzam CI z etapu 5 o testy tej funkcjonalności; pełne wydawanie aplikacji rozwijam w etapie 12. W logach łączę operacje identyfikatorem żądania, bez zapisywania sekretów.
- **Kryterium ukończenia:** funkcjonalność poprawnie obsługuje sukces i błędy, pilnuje uprawnień, a jej zachowanie można sprawdzić testami i logami.

### 7. Spójność, współbieżność i wydajność danych

- **Zakres:** transakcje i ACID, podstawy MVCC, izolacja, blokady i wyścigi; indeksy, EXPLAIN ANALYZE, N+1, paginacja i pula połączeń; bezpieczna ewolucja schematu, backup i odtwarzanie.
- **Praktyka:** symuluję równoczesne operacje naruszające tę samą regułę oraz awarię w trakcie zapisu. Analizuję zapytanie przed dodaniem indeksu i po nim. Wykonuję migrację z zachowaniem danych oraz odtwarzam kopię bazy.
- **Kryterium ukończenia:** mam dowód poprawności ważnej reguły przy współbieżności, potrafię uzasadnić indeks i bezpiecznie zmienić schemat z istniejącymi danymi.

### 8. DDD w kodzie, Vertical Slice Architecture i wzorce projektowe

- **Zakres:** encje, value objects, agregaty i granice spójności; logika domenowa i przypadki użycia; oddzielenie domeny od HTTP i infrastruktury. Adapter, factory, strategy, decorator i facade; rozróżnienie wzorca Decorator i dekoratorów TypeScript. Wzorzec outbox
- **Vertical Slice Architecture:** organizacja kodu według przypadków użycia, porównanie z podziałem warstwowym oraz łączenie VSA z DDD wewnątrz modularnego monolitu. Granice zależności między funkcjami, współdzielenie reguł domenowych i infrastruktury oraz ryzyko powielania logiki. VSA nie wymaga osobnego projektu ani zastosowania w całej aplikacji.
- **Praktyka:** na podstawie doświadczeń z działającą funkcją poprawiam podział na moduły. Wydzielam istotną regułę do testowania bez bazy i HTTP. Stosuję wzorce tam, gdzie rozwiązują konkretny problem; do integracji wracam z adapterem w etapie 10.
- **Ćwiczenie VSA:** na małym fragmencie działającego projektu porównuję podział warstwowy z podziałem według przypadków użycia. Wprowadzam tę samą zmianę wymagania w obu wariantach, sprawdzam jej wpływ na kod i testy oraz uzasadniam wybór. Wspólne reguły biznesowe zachowują jedno źródło definicji.
- **Kryterium ukończenia:** umiem uzasadnić granice odpowiedzialności i koszt abstrakcji. Proste operacje pozostają proste; nie wdrażam wzorców tylko po to, aby je wykorzystać.

### 9. Geolokalizacja i PostGIS

- **Zakres:** współrzędne, SRID, geometry/geography, indeksy przestrzenne i ST_DWithin. Różnica między odległością geograficzną, trasą drogową i czasem dojazdu; geokodowanie jako osobna integracja.
- **Praktyka:** dodaję wyszukiwanie w promieniu, łączę je z innymi filtrami i sprawdzam przypadki graniczne oraz plan zapytania. Zaczynam od gotowych współrzędnych.
- **Kryterium ukończenia:** potrafię wyjaśnić znaczenie wyniku, jednostki i ograniczenia obliczeń. Przybliżenia typu „odległość +15%” traktuję jako hipotezy wymagające weryfikacji, nie uniwersalną regułę.

### 10. Integracje zewnętrzne i kalendarze

- **Zakres:** OAuth 2.0, zakresy dostępu i tokeny; OpenID Connect i różnica między logowaniem a upoważnieniem do zewnętrznego API. Limity API, timeouty, ograniczone ponowienia z opóźnieniem i jitterem, idempotencja; daty, strefy czasowe i zmiana czasu. Rozróżnienie eksportu ICS, utworzenia wydarzenia, zaproszenia uczestnika, przypomnienia i webhooka o zmianie.
- **Praktyka:** integruję jednego dostawcę kalendarza w jednym kierunku. Obsługuję utworzenie, zmianę i anulowanie wydarzenia, powiązanie identyfikatorów oraz cofnięcie dostępu. Sprawdzam ponowienie po niejednoznacznym wyniku operacji.
- **Kryterium ukończenia:** sprawdzam ochronę przed duplikatami w wybranym API i opisuję granice jej gwarancji. Po niejednoznacznym wyniku potrafię ustalić stan u dostawcy albo skierować operację do wyjaśnienia. Błędy, uprawnienia i daty są świadomie obsłużone. Synchronizacja dwukierunkowa i złożone cykle wydarzeń są późniejszym rozszerzeniem.

### 11. Kolejki, routing wiadomości i niezawodność

- **Zakres:** producent, exchange, binding, routing key, kolejka i konsument w RabbitMQ/AMQP 0-9-1. Typy exchange: direct, fanout, topic; orientacyjnie headers. Polecenie a zdarzenie, podział pracy między konsumentów jednej kolejki a rozsyłanie zdarzenia do niezależnych kolejek. Potwierdzenia publikacji i przetwarzania, trwałość, prefetch, retry z opóźnieniem, dead-lettering, idempotencja, ograniczenia kolejności i transactional outbox.
- **Praktyka:** projektuję topologię dla zadania jednego rodzaju, rozgłoszenia zdarzenia do kilku odbiorców i routingu według wzorca. Rysuję przepływ i uzasadniam liczbę kolejek. Przenoszę integrację do workera, testuję duplikaty, awarię po wykonaniu efektu, wolnego konsumenta i wiadomość stale kończącą się błędem. Mierzę zaległości i wiek wiadomości; sprawdzam wpływ prefetch oraz liczby konsumentów. Rozwiązuję problem zapisu zmiany w bazie i zamiaru wysłania wiadomości.
- **Kryterium ukończenia:** potrafię przewidzieć, którzy odbiorcy dostaną wiadomość, wskazać możliwe duplikaty i utratę kolejności oraz bezpiecznie ponowić zadanie. Wiem, jak odizolować wadliwą wiadomość i nie przeciążyć zależności.

**Rozróżnienie pojęć:** direct, fanout i topic są tutaj typami exchange. Topic w Kafce to inne pojęcie, poznawane w etapie 18. Direct może skierować wiadomość do kilku pasujących kolejek; podział pracy między konsumentów odbywa się wewnątrz kolejki.

### 12. Wdrożenia: Linux, Nginx, Docker, Git i CI/CD

Etap dzielę na cztery mniejsze części. Nie muszę opanować ich wszystkich przed pierwszym wdrożeniem.

| Część                       | Zakres i praktyczny sprawdzian                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **12A. Linux i sieci**      | Procesy, wątki, sygnały, uprawnienia, konfiguracja, SSH i logi; DNS, IP, TCP, porty, interfejs nasłuchu i TLS. Używam np. curl, dig, ss i ps do rozpoznania błędnej nazwy hosta, zajętego portu i niedostępnego procesu.                                                                                                                                                                                                                                                                     |
| **12B. Docker i Nginx**     | Kontener a VM; obrazy, Dockerfile, warstwy, multi-stage build, sieci, wolumeny, healthchecki i Compose. Konteneryzuję aplikację. Nginx serwuje frontend i przekazuje /api do Node.js przez reverse proxy; konfiguruję HTTPS, przekazywane nagłówki, zaufanie do proxy, timeouty i logi. Waliduję konfigurację, diagnozuję 502/504.                                                                                                                                                           |
| **12C. Git i wydania**      | Obiekty, graf historii, HEAD, index, merge/rebase, reset/revert, reflog i tagi. Odtwarzam pomyłkę i odzyskuję zmianę. Porównuję prosty workflow z Gitflow; ćwiczę release branch, hotfix, release candidate i wydanie finalne. Nie narzucam Gitflow jednoosobowemu projektowi.                                                                                                                                                                                                               |
| **12D. CI/CD i środowisko** | GitHub Actions: workflows, joby, runnery, artefakty, registry, środowiska i sekrety. Rozszerzam CI z etapów 5–6 o budowę obrazu i wdrożenie. GitLab CI/CD poznaję porównawczo, także pod kątem zastosowania w pracy. Stosuję wybrane zasady Twelve-Factor App: konfiguracja, bezstanowe procesy, logi i rozdzielenie budowy od uruchomienia. Sprawdzam dostęp sieciowy, uprawnienia i koszt wybranego hostingu. Wdrażam wersję i przywracam działanie po błędzie, uwzględniając migracje DB. |

- **Kryterium ukończenia:** uruchamiam system od zera, wdrażam wskazaną wersję, rozpoznaję błąd aplikacji, proxy lub konfiguracji i oceniam możliwość cofnięcia wdrożenia. Sprawdzam podstawowe metryki oraz bezpieczne kończenie procesu i pracy workera. Rozumiem, kiedy hosting zapewnia reverse proxy bez własnego Nginx.
- **Powrót w dalszych etapach:** pomiary i limity ruchu (13), cache HTTP (14), load balancing dwóch instancji i ustawienia WebSocket/SSE, w tym buforowanie i timeouty (16).

### 13. Optymalizacja całej aplikacji na podstawie pomiarów

- **Zakres:** profil obciążenia i wielkość danych, pomiar bazowy, przepustowość, opóźnienia p50/p95/p99, błędy i zużycie zasobów. Łączenie logów i metryk z żądaniem lub zadaniem z kolejki. Testy obciążeniowe i przeciążeniowe; profilowanie Node.js, opóźnienie event loop, pamięć, SQL, pula połączeń, rozmiar odpowiedzi oraz liczba żądań z UI. Podstawy ograniczania współbieżności i ruchu przy przeciążeniu.
- **Praktyka:** wybieram ważny scenariusz użytkownika i mierzalny cel. Przygotowuję reprezentatywne dane oraz test, np. w k6. Znajduję wąskie gardło, zmieniam jeden element i porównuję wyniki przy tym samym obciążeniu. Rejestruję też błędy i koszt zasobów; samo skrócenie średniego czasu nie wystarcza.
- **Kryterium ukończenia:** pokazuję pomiar przed zmianą i po niej, wyjaśniam przyczynę poprawy oraz jej koszt. Umiem określić ograniczenia testu i wykryć regresję. Pomiary powtarzam w etapach 14–17.

### 14. Świadomy cache i warmupery

- **Zakres:** co i na jakiej warstwie buforować: pamięć procesu, Redis, HTTP/cache przeglądarki lub CDN. Cache-aside, TTL, unieważnianie, klucze uwzględniające użytkownika i parametry, limit pamięci i eviction. Porównanie odświeżania na żądanie i w tle; orientacyjnie write-through/write-behind i ich koszty. Cache stampede, rozproszenie wygasania przez jitter, łączenie równoczesnych odczytów i dopuszczalna nieaktualność.
- **Praktyka:** przyspieszam zmierzony odczyt. Projektuję warmer — zadanie wcześniej przygotowujące wybrane popularne dane — z limitem obciążenia i strategią odświeżania. Porównuję zimny i rozgrzany cache; sprawdzam zmianę danych, równoczesne wygaśnięcie klucza, restart i awarię Redis. Mierzę hit ratio, p95, obciążenie bazy i koszt warmowania.
- **Kryterium ukończenia:** potrafię uzasadnić, co warto rozgrzewać, a co pomijać. Nie ujawniam danych między użytkownikami. Po utracie cache aplikacja zachowuje kontrolę nad obciążeniem bazy; wiem, kiedy obsłużyć odczyt bez cache, a kiedy ograniczyć ruch.

### 15. Podział odpowiedzialności: PostgreSQL i OpenSearch/Elasticsearch

- **Zakres:** w tym projekcie PostgreSQL jest źródłem prawdy dla danych biznesowych, relacji, ograniczeń i transakcji; wyszukiwarka przechowuje odtwarzalny model do wyszukiwania, rankingu, filtrów i agregacji. Porównanie z full-text search PostgreSQL. Denormalizacja dokumentów, mapping, analyzery, opóźnienie synchronizacji i refresh, wersjonowanie zmian, usuwanie dokumentów, reindeksacja i aliasy. Przypisanie odpowiedzialności zależy od wymagań, nie od samej nazwy narzędzia.
- **Praktyka:** wybieram jeden silnik i określam, które zapytania trafiają do niego, a które do DB. Zasilam indeks zmianami z bazy z wykorzystaniem poznanego outboxa, obsługuję powtórzenia i starsze zdarzenia. Symuluję brak wyszukiwarki, usunięcie lub zmianę uprawnień do rekordu i opóźnione indeksowanie. Odbudowuję indeks ze źródła prawdy, uwzględniając zmiany zachodzące podczas odbudowy, i przełączam alias.
- **Kryterium ukończenia:** potrafię odtworzyć indeks i wykryć rozbieżności. Zapis biznesowy nie zależy od udanego jednoczesnego zapisu w dwóch systemach. Ochrona uprawnień obejmuje również wyniki wyszukiwania, fragmenty i agregacje — opóźniony indeks nie może ujawniać prywatnych danych. Dla danych wrażliwych weryfikuję aktualny dostęp w źródle prawdy przed zwróceniem wyniku; operacje biznesowe dodatkowo sprawdzają bieżące reguły.

### 16. Komunikacja w czasie rzeczywistym: polling, SSE i WebSocket

- **Zakres:** porównanie okresowego odpytywania, SSE (strumień serwer → klient przez HTTP) i WebSocket (komunikacja dwukierunkowa). Obsługa połączeń na serwerze, uwierzytelnianie, autoryzacja subskrypcji, heartbeat, reconnect z opóźnieniem, duplikaty, kolejność, wolny klient i ograniczanie buforów. Kilka instancji backendu i przekazywanie zdarzeń między nimi.
- **Praktyka:** implementuję mały przepływ dwukierunkowy przez WebSocket oraz porównuję go z SSE dla aktualizacji jednokierunkowych. Testuję rozłączenie, ponowne połączenie i zmianę uprawnień. Po przerwie klient pobiera aktualny stan lub brakujące zdarzenia, zależnie od wymagań. Sprawdzam obsługę klientów podłączonych do dwóch instancji backendu.
- **Kryterium ukończenia:** dobieram mechanizm do kierunku i częstotliwości komunikacji. Użytkownik odzyskuje spójny widok po przerwie. Rozumiem, że samo połączenie WebSocket nie zapewnia historii, trwałości ani dostarczenia wiadomości podczas rozłączenia.

API oznacza interfejs. HTTP, WebSocket i AMQP opisują protokoły; SSE jest mechanizmem przesyłania zdarzeń przez HTTP. W ćwiczeniach rozdzielam kontrakt operacji od sposobu transportu.

### 17. PWA, service worker i powiadomienia Web Push

- **Zakres:** manifest, HTTPS, cykl życia i aktualizacje service workera; Cache Storage i strategie offline; rozdzielenie cache zasobów i danych użytkownika. Push API, Notifications API, zgoda użytkownika, subskrypcja urządzenia, usługa push przeglądarki i VAPID. Wersje aplikacji, czyszczenie prywatnych danych po wylogowaniu, wygasłe subskrypcje i preferencje powiadomień.
- **Praktyka:** dodaję działanie wybranego widoku offline z oznaczeniem nieaktualności. Backend zapisuje subskrypcję i zleca wysłanie powiadomienia przez worker oraz usługę push. Service worker obsługuje odbiór i kliknięcie; aplikacja pobiera aktualne dane po otwarciu. Testuję brak zgody, wypisanie, wygasłą subskrypcję, aktualizację service workera i dostarczenie przy zamkniętej karcie na wspieranej platformie.
- **Kryterium ukończenia:** potrafię prześledzić cały przepływ od zdarzenia biznesowego do urządzenia, obsłużyć odwołanie zgody i opisać ograniczenia platform. Nie zakładam gwarantowanego ani natychmiastowego dostarczenia push. Service worker może być zatrzymywany przez przeglądarkę; nie służy jako stale działający proces. Synchronizacja zapisów offline jest dalszym rozszerzeniem.

Web Push to inny kanał niż WebSocket oraz webhook od dostawcy kalendarza. Wszystkie mogą reagować na to samo zdarzenie biznesowe, ale pełnią różne role.

### 18. Laboratoria porównawcze

Każdy temat kończy się małym eksperymentem i decyzją, czy ma zastosowanie w głównym projekcie.

| Temat                            | Zakres i ćwiczenie                                                                                                                                                                                                                                                                                                                                                                               | Kryterium ukończenia                                                                                                                                                              |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| GraphQL a REST                   | Schemat SDL, typy i nullability, query/mutation, resolvery i context, paginacja, częściowe błędy, autoryzacja obiektów i pól. Potrzeby widoku a model API; generowanie typów operacji dla frontendu, ewolucja schematu i deprecations. Implementuję ten sam przypadek użycia przez REST i GraphQL, korzystając ze wspólnej logiki biznesowej. Podstawowe laboratorium można wykonać po etapie 7. | Uzasadniam wybór dla danego widoku, porównuję liczbę żądań HTTP, rozmiar odpowiedzi i liczbę zapytań SQL. Rozumiem, że schemat GraphQL jest kontraktem API, a nie schematem bazy. |
| Modele NoSQL a PostgreSQL        | Przegląd modeli dokumentowych, key-value, grafowych i szeregów czasowych. Po etapie 7 wybieram jeden, np. dokumentowy MongoDB, i porównuję ten sam przypadek z PostgreSQL: embedding/referencje, wzorce odczytu, indeksy, walidacja i transakcje.                                                                                                                                                | Uzasadniam model konkretnymi operacjami i ograniczeniami; elastyczny schemat nadal jest świadomie projektowany. Nie muszę wdrażać każdej rodziny baz.                             |
| EAV / JSONB                      | Ten sam problem zmiennych atrybutów modeluję zwykłymi tabelami, JSONB i EAV; porównuję walidację, zapytania i indeksowanie. Można wykonać po etapie 7.                                                                                                                                                                                                                                           | Potrafię wskazać koszty i zastosowania każdego modelu.                                                                                                                            |
| Kafka                            | Topic, partycje, klucze, offsety, grupy konsumentów, retencja, replay i rebalance; porównanie z routingiem RabbitMQ. Można wykonać po etapie 11.                                                                                                                                                                                                                                                 | Rozumiem kolejność w partycji, wpływ podziału na partycje i ponowień oraz granice gwarancji przetwarzania, szczególnie przy zewnętrznym efekcie biznesowym.                       |
| gRPC / Protobuf                  | Kontrakt, serializacja i komunikacja między backendami; mała operacja unary oraz porównanie z HTTP/JSON po etapach 8 i 10. Streaming jako późniejsze rozszerzenie; WebSocket nie jest warunkiem wejścia.                                                                                                                                                                                         | Potrafię uzasadnić wybór i wskazać ograniczenia integracji przeglądarkowej oraz koszty narzędziowe.                                                                               |
| Serverless a worker w kontenerze | Po etapach 11–13 uruchamiam małe zadanie jako funkcję reagującą na zdarzenie, np. AWS Lambda. Porównuję model wykonania, cold start, timeout, współbieżność, ponowienia, połączenia do DB, uprawnienia i koszt przy różnym ruchu.                                                                                                                                                                | Potrafię zdecydować, kiedy funkcja jest uzasadniona, oraz obsłużyć jej ponowne wykonanie bez powielania efektów.                                                                  |

**GraphQL — część podstawowego laboratorium:** sprawdzam N+1 przy zagnieżdżonym pobieraniu, stosuję batching/DataLoader z cache ograniczonym do żądania i odróżniam go od cache klienta lub współdzielonego cache serwera. Ograniczam wielkość list i koszt operacji oraz testuję dostęp do cudzych danych na różnych ścieżkach zapytania. Kryterium: pojedyncze żądanie HTTP nie ukrywa niekontrolowanej liczby zapytań SQL, a uprawnienia obowiązują niezależnie od sposobu dojścia do obiektu. Tych podstaw nie odkładam na później. Po etapach 13–14 pogłębiam pomiary i cache; po 16 mogę dodać subscription i porównać obsługę przez WebSocket/SSE. GraphQL sam nie narzuca transportu. Federation zostawiam na sytuację wymagającą współpracy kilku niezależnie rozwijanych API.

### 19. Kubernetes z perspektywy developera — opcjonalne rozszerzenie

- **Warunek wejścia:** rozumiem Docker/Compose, sieci, wdrożenia, healthchecki i pomiary z etapów 12–13. Zaczynam od lokalnego klastra, np. kind albo minikube.
- **Zakres:** stan deklarowany i kontrolery, klaster/node/Pod, Deployment, Service, labels/selectors, ConfigMap i Secret wraz z kontrolą dostępu. Requests/limits, startup/readiness/liveness probes, rolling update, rollback i skalowanie replik. Gateway API z odpowiednim kontrolerem; orientacyjnie Ingress. Rola trwałych wolumenów i różnica między procesem bezstanowym a usługą przechowującą dane.
- **Praktyka:** wdrażam backend i worker korzystające z zewnętrznej bazy. Konfiguruję routing i sondy, zmieniam liczbę replik, usuwam Pod i obserwuję jego odtworzenie. Wdrażam wadliwą wersję, diagnozuję ją przez logs/describe/events, następnie cofam wdrożenie. Sprawdzam zamykanie procesu i dokończenie lub ponowienie zadań. Zewnętrzny dostęp testuję przez wybraną implementację Gateway API.
- **Kryterium ukończenia:** umiem odróżnić awarię aplikacji, brak zasobów, problem konfiguracji i routingu; wyjaśniam, co zapewniają kontrolery, a co nadal musi obsłużyć aplikacja. Potrafię porównać koszt obsługi z Compose lub zarządzaną platformą.
- **Późniejsze pogłębienie:** HPA na podstawie metryk, Jobs/CronJobs, Helm/Kustomize, service accounts/RBAC, NetworkPolicy i zarządzany klaster. Utrzymanie produkcyjnych baz w klastrze jest osobnym zagadnieniem.

## Dalsze kierunki — propozycje

Nie są automatycznie obowiązkowymi kolejnymi etapami. Wybieram jeden problem i eksperyment, zamiast dodawać całą listę do projektu.

| Priorytet i kierunek                               | Koncepty do pogłębienia                                                                                                                                                                                                                                                                | Przykład sprawdzianu                                                                                                                          |
| -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Wysoki: obserwowalność i cele jakości              | Łączenie logów, metryk i traces; OpenTelemetry, propagacja kontekstu przez kolejkę, SLI/SLO i użyteczne alerty. Podstawy logów zaczynają się wcześniej; tu pogłębiam etapy 12–13.                                                                                                      | Od wolnej akcji w UI dochodzę do konkretnego zapytania lub zależności; wykrywam wzrost opóźnienia kolejki.                                    |
| Wysoki: odporność na przeciążenia i awarie         | Budżety timeoutów i ponowień, circuit breaker, bulkhead, backpressure, rate limiting, ograniczona funkcjonalność podczas awarii i graceful shutdown. Po etapach 10–11, z pomiarami z etapu 13.                                                                                         | Awaria kalendarza nie blokuje odczytu danych ani nie tworzy nieograniczonej liczby ponowień; restart workera nie gubi zadania.                |
| Wysoki: ewolucja kontraktów                        | Rozwinięcie OpenAPI i testów z etapu 6: schematy zdarzeń, kompatybilność wsteczna, contract tests, migracje expand/contract i współistnienie wersji. Po etapach 11–12.                                                                                                                 | Starszy klient i konsument działają podczas wdrażania nowego pola; test wykrywa zmianę łamiącą kontrakt.                                      |
| Wysoki: bezpieczeństwo projektowania               | Modelowanie zagrożeń, sesje i cykl życia tokenów, XSS/CSRF/SSRF, autoryzacja obiektów i subskrypcji, izolacja użytkowników/organizacji, minimalizacja danych i audyt. Podstawy obowiązują od etapu 6, a każdy nowy kanał rozszerza analizę.                                            | Próba odczytu cudzego zasobu lub kanału jest blokowana także przez cache, wyszukiwarkę i WebSocket.                                           |
| Później: procesy między systemami i zapisy offline | Pogłębienie spójności poznanej przy kolejkach i indeksie: read-your-writes, modele odczytu/CQRS, orkiestracja i choreografia, saga i kompensacje po etapach 11 i 15. Osobno konflikty zapisów offline po 17.                                                                           | Proces z częściowym sukcesem ma jawny stan i odzyskiwanie; w osobnym ćwiczeniu dwa urządzenia zmieniają rekord bez cichego nadpisania danych. |
| Później: skalowanie, chmura i odtwarzanie          | Jeden dostawca chmury: IAM, sieć i reguły dostępu, zarządzana baza, object storage, sekrety i koszt. Skalowanie poziome, load balancing, replikacja i opóźnienie replik, partycjonowanie/sharding, kompromisy CAP przy podziale sieci, podstawy IaC, RPO/RTO. Po pomiarach z etapu 13. | Odtwarzam środowisko z konfiguracji i backupu, mierzę czas oraz możliwą utratę danych; uzasadniam każdą dodatkową instancję.                  |
| Zależnie od projektu: pliki i strumienie           | Object storage, upload bezpośredni przez podpisany URL, autoryzacja plików, limity, streams/backpressure i przetwarzanie w tle.                                                                                                                                                        | Duży upload nie wyczerpuje pamięci Node.js; prywatny plik pozostaje prywatny, a przerwane przetwarzanie da się ponowić.                       |

Pierwszeństwo w dalszym pogłębianiu mają obserwowalność, odporność i kontrakty; ich podstawy oraz bezpieczeństwo rozwijam już podczas budowania funkcji. Kubernetes poznaję w ograniczonym laboratorium z etapu 19. Mikroserwisy, service mesh i event sourcing rozważam przy konkretnym problemie; ich wdrożenie nie jest warunkiem opanowania tej roadmapy. Przy wyborze architektury oceniam granice odpowiedzialności, sprzężenia, spójność i koszt eksploatacji.

roadmap.sh/backend służy jako katalog porównawczy. Nie jest listą technologii, które muszę wszystkie wdrożyć.

## Ćwiczenie łączące kolejne etapy

W miarę realizacji etapów 13–17 rozwijam jeden scenariusz, np. zmianę terminu obserwowanego wydarzenia. Zapis w DB i outbox uruchamia aktualizację indeksu, unieważnienie cache oraz niezależne zadania powiadomień. Otwarty klient dostaje aktualizację przez SSE/WebSocket, a subskrybent może dostać Web Push. Dokładam tylko mechanizmy już poznane i uzasadnione w projekcie. W UI widać stan synchronizacji; nie zakładam atomowego sukcesu wszystkich kanałów.

Sprawdzam duplikaty, awarię wybranego odbiorcy, zmianę uprawnień i opóźnienie synchronizacji. Potrafię prześledzić zdarzenie w logach i metrykach oraz uzasadnić każdą granicę odpowiedzialności. To przykład integrujący naukę, nie obowiązkowa tematyka projektu.

## Sposób pracy i rola AI

Cykl pracy: **pojęcie → własna propozycja → krytyka → eksperyment → weryfikacja → krótki zapis decyzji**.

- Pierwszy szkic modelu, schematu, reguł i oczekiwanych wyników testów przygotowuję samodzielnie.
- AI wyjaśnia pojęcia, zadaje pytania, szuka kontrprzykładów i ocenia propozycje. Korzystam z mechanizmów skonfigurowanych w etapie 5; może pomagać w implementacji i danych testowych, przy zachowaniu mojego udziału w decyzjach i weryfikacji.
- Pierwszy mały przykład nowego mechanizmu implementuję na tyle samodzielnie, aby umieć prześledzić jego działanie.
- Odpowiedzi AI weryfikuję dokumentacją, testami i obserwacją działania. Ważne decyzje poddaję również ocenie doświadczonego developera.
- Zapisuję krótkie ADR-y: decyzja, powód, alternatywa, koszt i warunek ponownego rozważenia.
- Regularnie wykonuję małe ćwiczenia modelowania innych domen, żeby nie ograniczać nauki do jednego schematu.
- Po sesji zapisuję stan pracy, niewyjaśnioną kwestię i następny mały krok. Pozwala to wracać po przerwach bez harmonogramu.

## Materiały odniesienia

Lista startowa do korzystania przy odpowiednim etapie, nie obowiązek czytania całości przed praktyką.

- [Node.js Learn](https://nodejs.org/en/learn) i [Express — routing](https://expressjs.com/en/starter/basic-routing/) / [obsługa błędów](https://expressjs.com/en/guide/error-handling/).
- [PostgreSQL — dokumentacja](https://www.postgresql.org/docs/current/), szczególnie constraints, transactions, concurrency control, indexes i EXPLAIN.
- [Microsoft — analiza domeny](https://learn.microsoft.com/en-us/azure/architecture/microservices/model/domain-analysis); materiał opisuje mikroserwisy, ale służy tutaj nauce modelowania, nie narzuceniu takiej architektury.
- [Jimmy Bogard — Vertical Slice Architecture](https://www.jimmybogard.com/vertical-slice-architecture/) — organizacja według przypadków użycia, zależności i kompromisy.
- [PostGIS — ST_DWithin](https://postgis.net/docs/ST_DWithin.html).
- [Google Calendar — tworzenie wydarzeń](https://developers.google.com/workspace/calendar/api/guides/create-events) i [powiadomienia push](https://developers.google.com/workspace/calendar/api/guides/push).
- [RabbitMQ — exchange i routing](https://www.rabbitmq.com/docs/exchanges) oraz [potwierdzenia](https://www.rabbitmq.com/docs/confirms).
- [Claude Code — instrukcje projektu](https://code.claude.com/docs/en/memory), [skills i komendy](https://code.claude.com/docs/en/skills), [subagenci](https://code.claude.com/docs/en/sub-agents) i [hooki](https://code.claude.com/docs/en/hooks).
- [Vite](https://vite.dev/guide/), [TanStack Router](https://tanstack.com/router/latest/docs/quick-start) i [GitHub Actions](https://docs.github.com/en/actions).
- [Docker Compose](https://docs.docker.com/compose/intro/compose-application-model/), [Pro Git](https://git-scm.com/book/en/v2) i [GitLab CI/CD](https://docs.gitlab.com/ci/).
- [k6 — progi oceny testów](https://grafana.com/docs/k6/latest/using-k6/thresholds/) i [OpenTelemetry — sygnały](https://opentelemetry.io/docs/concepts/signals/).
- [Cache-aside i wstępne zasilanie cache](https://learn.microsoft.com/en-us/azure/architecture/patterns/cache-aside) oraz [MDN — HTTP caching](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Caching).
- [OpenSearch — odbudowa indeksów](https://docs.opensearch.org/latest/im-plugin/reindex-data/), [aliasy](https://docs.opensearch.org/latest/im-plugin/index-alias/) i [refresh](https://opensearch.org/blog/optimize-refresh-interval/).
- [MDN — WebSocket](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API), [SSE](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events), [cache w PWA](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Guides/Caching) i [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API).
- [Circuit breaker](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker), [saga](https://learn.microsoft.com/en-us/azure/architecture/patterns/saga), [OWASP API Security](https://api-security.owasp.org/editions/2023/en/0x11-t10/) i [gRPC — wprowadzenie](https://grpc.io/docs/what-is-grpc/introduction/).
- [GraphQL — podstawy](https://graphql.org/learn/), [wydajność](https://graphql.org/learn/performance/), [autoryzacja](https://graphql.org/learn/authorization/), [bezpieczeństwo](https://graphql.org/learn/security/) oraz [DataLoader](https://github.com/graphql/dataloader).
- [roadmap.sh/backend](https://roadmap.sh/backend) i [mapa w PDF](https://roadmap.sh/pdfs/roadmaps/backend.pdf) — katalog porównawczy.
- [Nginx — podstawy](https://nginx.org/en/docs/beginners_guide.html) i [WebSocket proxying](https://nginx.org/en/docs/http/websocket.html); [Twelve-Factor App](https://12factor.net/).
- [Kubernetes — podstawowe ćwiczenia](https://kubernetes.io/docs/tutorials/kubernetes-basics/) i [Gateway API](https://kubernetes.io/docs/concepts/services-networking/gateway/).
- [OWASP — sesje](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html) i [przechowywanie haseł](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html).
- [OpenID Connect — mechanizm logowania na przykładzie Microsoft identity platform](https://learn.microsoft.com/en-us/entra/identity-platform/v2-protocols-oidc).
- [MongoDB — modelowanie danych](https://www.mongodb.com/docs/manual/data-modeling/) i [AWS Lambda — wprowadzenie](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html).

Szczegółowe lekcje i zadania będą rozpisywane przy rozpoczynaniu poszczególnych etapów, po uwzględnieniu uwag z przeglądu tej roadmapy.
