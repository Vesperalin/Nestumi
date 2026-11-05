# Nestumi — rejestr decyzji, założeń i otwartych kwestii

Jedno miejsce na to, co rozstrzygnięte, przyjęte na razie lub jeszcze otwarte. Znaczenie pojęć: `docs/glossary.md`.

**Rodzaj wpisu:**

- **Decyzja** — rozstrzygnęłam ją ja.
- **Założenie** — przyjmuję na razie, bez pełnej analizy; może się zmienić.
- **Propozycja Claude** — jeszcze nie przyjęta.
- **Otwarte** — świadomie nierozstrzygnięte.

Wpisów nie usuwam: zmieniona decyzja dostaje nowy wpis, a stary oznaczam jako zastąpiony. Pola oznaczone „(Claude)” uzupełnił Claude — do mojej weryfikacji.

## Wpisy

### R-001: Przeglądanie i wyszukiwanie bez konta

- **Rodzaj:** Decyzja
- **Treść:** Przeglądanie i wyszukiwanie ofert nie wymaga konta. Robi to anonimowy odwiedzający.
- **Powód:** do uzupełnienia
- **Rozważane alternatywy:** (Claude) katalog dostępny tylko po zalogowaniu.
- **Koszt / konsekwencje:** (Claude) publiczne informacje muszą być wyraźnie oddzielone od prywatnych; to, co widać w katalogu, nie może zależeć od tego, kto ogląda.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Anonimowy odwiedzający, Oferta, R-002, R-004
- **Do przeglądu z Mikołajem:** do ustalenia
- **Status wpisu:** aktualny

### R-002: Akcje wymagają konta

- **Rodzaj:** Decyzja
- **Treść:** Każda akcja, np. rezerwacja, wymaga konta i zalogowania.
- **Powód:** do uzupełnienia
- **Rozważane alternatywy:** (Claude) rezerwacja bez konta, np. tylko z adresem e-mail.
- **Koszt / konsekwencje:** (Claude) anonimowy odwiedzający, który chce zarezerwować, musi zalogować się w trakcie — scenariusz do kroku 2. Otwarte pozostaje, czy w v1 istnieje rejestracja, czy tylko konta testowe.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Anonimowy odwiedzający, Konto, Złożenie rezerwacji, R-001, R-003
- **Do przeglądu z Mikołajem:** do ustalenia
- **Status wpisu:** aktualny

### R-003: Rezerwacja składana po podsumowaniu, bez wcześniejszej blokady terminu

- **Rodzaj:** Decyzja
- **Treść:** Zanim termin zostanie zajęty, uczestnik potwierdza rezerwację po obejrzeniu podsumowania. Dotyczy to zarówno kogoś zalogowanego wcześniej, jak i kogoś, kto loguje się dopiero teraz. Do tego momentu termin nie jest blokowany.
- **Powód:** do uzupełnienia
- **Rozważane alternatywy:** (Claude) tymczasowa blokada terminu na kilka minut po jego wybraniu — większy mechanizm, poza v1.
- **Koszt / konsekwencje:** (Claude) termin może zostać zajęty przez kogoś innego między podsumowaniem a złożeniem rezerwacji. Wolny termin jest sprawdzany dopiero przy złożeniu — scenariusz błędu do kroku 2.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Złożenie rezerwacji, Potwierdzenie, Wolny termin, R-002, R-005
- **Do przeglądu z Mikołajem:** do ustalenia
- **Status wpisu:** aktualny

### R-004: Anonimowy odwiedzający widzi wolne terminy, nie grafik

- **Rodzaj:** Decyzja
- **Treść:** Anonimowy odwiedzający widzi publiczne, niekrytyczne informacje: oferty, profile prowadzących i wolne terminy. Nie widzi grafiku prowadzącego ani danych rezerwacji. Do wykonania akcji potrzebne jest konto (R-002).
- **Powód:** do uzupełnienia
- **Rozważane alternatywy:** (Claude) pokazywanie grafiku — odwiedzający nie wiedziałby wtedy, co jest naprawdę wolne.
- **Koszt / konsekwencje:** (Claude) z wolnych terminów można wywnioskować, kiedy prowadzący ma rezerwacje, choć nie z kim — przyjęte świadomie. Pełna lista „niekrytycznych informacji” wymaga doprecyzowania.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Anonimowy odwiedzający, Wolny termin, Grafik, R-001
- **Do przeglądu z Mikołajem:** do ustalenia
- **Status wpisu:** aktualny

### R-005: Wybór terminu zachowuje się po zalogowaniu w trakcie rezerwacji

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Anonimowy odwiedzający wybiera wolny termin i formę, a system prosi go o zalogowanie lub założenie konta. Po zalogowaniu wraca do podsumowania z tą samą ofertą, terminem i formą (UC-3, 3a). Zachowanie wyboru nie wstrzymuje terminu — inni nadal mogą go zarezerwować.
- **Powód:** osoba nie traci wyboru tuż przed rezerwacją; zajęcie terminu w międzyczasie obsługuje sprawdzenie przy złożeniu rezerwacji (R-037), więc nie trzeba wstrzymania terminu.
- **Rozważane alternatywy:** wybór od nowa po zalogowaniu; logowanie przed wyborem terminu (sprzeczne z R-001, R-004); czasowe wstrzymanie terminu (`docs/brainstorming.md`, 5.2).
- **Koszt / konsekwencje:** (Claude) osoba może wrócić do podsumowania terminu, który w międzyczasie przestał być wolny, i dostać odmowę dopiero przy złożeniu rezerwacji; termin może też w międzyczasie minąć — do rozważenia w rozszerzeniach UC-3. Jak długo system pamięta wybór — szczegół działania, etap 6.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Anonimowy odwiedzający, Złożenie rezerwacji, R-002, R-003, R-037
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-006: Oferta może być szkicem

- **Rodzaj:** Decyzja
- **Treść:** Oferta może istnieć jako szkic: nieopublikowana, niewidoczna w katalogu i niedostępna do rezerwacji.
- **Powód:** do uzupełnienia
- **Rozważane alternatywy:** (Claude) oferta od razu publikowana przy dodaniu.
- **Koszt / konsekwencje:** (Claude) szkic można swobodnie edytować, bo nie ma rezerwacji. Propozycja: usuwać można tylko szkic — opublikowanej oferty nie, bo rezerwacje straciłyby punkt odniesienia w historii. Pełny cykl życia oferty — krok 4.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Oferta, Publikacja, R-007
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-007: Rezerwacja zapisuje warunki oferty z chwili złożenia

- **Rodzaj:** Decyzja
- **Treść:** W chwili złożenia rezerwacja zapisuje wszystkie warunki oferty. Późniejsza edycja oferty dotyczy tylko nowych rezerwacji i nie zmienia istniejących.
- **Powód:** do uzupełnienia. (Claude) przewidywalność dla uczestnika; zachowana historia tego, na co strony się umówiły; zmiana czasu trwania oferty nie wywoła kolizji w istniejących rezerwacjach.
- **Rozważane alternatywy:** rezerwacja zawsze pokazuje aktualne dane oferty; wersje oferty; blokada edycji wybranych pól; nowa oferta zamiast edycji; zmiana obejmuje istniejące rezerwacje z powiadomieniem.
- **Koszt / konsekwencje:** (Claude) każda zmiana istniejącej rezerwacji musi być osobną, świadomą czynnością, a nie skutkiem edycji oferty. Później łatwo dodać wyjątki (pola przechodzące do istniejących rezerwacji, zmiany wymagające nowej oferty). Odwrotne przejście — od rezerwacji bez zapisanych warunków — utraciłoby historię uzgodnień.
- **Warunek ponownego rozważenia:** (Claude) potrzeba pełnej historii zmian samej oferty → wersje oferty.
- **Powiązane pojęcia i wpisy:** Rezerwacja, Oferta, Cena, Czas trwania, Miejsce spotkania, R-009
- **Do przeglądu z Mikołajem:** do ustalenia (Claude: proponuję tak — decyzja o modelu danych)
- **Status wpisu:** aktualny

### R-008: Powiadomienia w aplikacji w v1

- **Rodzaj:** Decyzja — zmiana zakresu względem `docs/project-brief.md`
- **Treść:** W v1 są powiadomienia w aplikacji. E-mail i push na urządzenie pozostają rozszerzeniami. (Claude) Przykłady zdarzeń: anulowanie rezerwacji przez drugą stronę.
- **Powód:** do uzupełnienia
- **Rozważane alternatywy:** brak powiadomień w v1; e-mail (zewnętrzny dostawca, wysyłka w tle — etapy 10–11); push (etap 17).
- **Koszt / konsekwencje:** (Claude) brief zaktualizowany (sekcja 3). Pełna lista zdarzeń, o których strony muszą wiedzieć — krok 3.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Anulowanie, Rezerwacja, R-009, R-038
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** zastąpiony przez R-038

### R-009: Zmiana miejsca spotkania w istniejącej rezerwacji (przeprowadzka)

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** W v1 prowadzący, który zmienia miejsce, anuluje istniejące rezerwacje; uczestnik widzi anulowanie na liście swoich rezerwacji (R-038) i może zarezerwować ponownie pod nowym adresem.
- **Powód:** korzysta tylko z czynności, które już są w v1 (anulowanie, rezerwacja) — bez nowej czynności i nowego stanu.
- **Rozważane alternatywy:** b) prowadzący zmienia miejsce w rezerwacji, uczestnik dostaje powiadomienie; c) prowadzący proponuje zmianę, uczestnik akceptuje lub odrzuca (proces jak przełożenie, poza v1).
- **Koszt / konsekwencje:** zwolniony czas może zająć ktoś inny, zanim uczestnik zarezerwuje ponownie; bez powiadomień (R-038) uczestnik może w ogóle nie zauważyć anulowania. Przejście później na b lub c to dodanie nowej czynności — anulowane rezerwacje zostają w historii, nie trzeba zmieniać istniejących danych.
- **Warunek ponownego rozważenia:** zmiany miejsca są częste albo uczestnicy tracą terminy przy ponownej rezerwacji → wariant c.
- **Powiązane pojęcia i wpisy:** Anulowanie, Miejsce spotkania, R-007, R-008, R-038
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-010: Profile zawodowe — jedna lub kilka pokrewnych profesji

- **Rodzaj:** Decyzja (rozstrzyga otwartą decyzję z briefu; zasada składu profilu — przyjęta propozycja Claude)
- **Treść:** Osoba ma jeden lub kilka profili zawodowych. Profil to prezentacja jednej lub kilku pokrewnych profesji osoby, które mają ten sam charakter usługi. Profil ma własne oferty i jeden grafik. Każda oferta należy do jednego profilu i wskazuje jedną jego profesję.
- **Powód:** profil dostaje własne zadanie (prezentacja profesji, opis, kwalifikacje), a przy każdej ofercie widać, w jakiej roli występuje prowadzący. Pokrewne profesje w jednym profilu pozwalają np. psycholożce i psychoterapeutce przyjmować na obie usługi w tym samym przedziale.
- **Rozważane alternatywy:** jeden wspólny profil osoby; jeden profil na profesję (wtedy psycholog-psychoterapeuta musi dzielić dzień między dwa grafiki); profil swobodnie nazwany, np. per miejsce; profil i nazwane grafiki jako dwie niezależne osie; (2026-11-01) jeden grafik na osobę bez profili, dla uproszczenia v1 — odrzucone, bo profil przechowuje profesję i kwalifikacje (R-029, R-032) i przez niego osoba zostaje prowadzącym (R-027).
- **Koszt / konsekwencje:** usługi o różnym charakterze (np. konsultacja i joga) nie mogą być oferowane w tym samym przedziale — świadomy koszt rozdzielenia zdrowia psychicznego od dobrostanu. Zakłada, że każda profesja ma charakter usługi. Wspólna zajętość osoby obowiązuje dla wszystkich profili.
- **Warunek ponownego rozważenia:** prowadzący potrzebują oferować usługi o różnym charakterze w tym samym czasie i miejscu.
- **Powiązane pojęcia i wpisy:** Profil zawodowy, Profesja, Charakter usługi, Oferta, Grafik, R-011, R-012, R-013
- **Do przeglądu z Mikołajem:** do ustalenia (Claude: proponuję tak — kluczowa decyzja modelu)
- **Status wpisu:** aktualny; doprecyzowany przez R-030 — charakter profilu to charakter jego profesji, a oferty profilu ze zdrowia psychicznego mogą mieć charakter dobrostanu

### R-011: Grafik profilu; miejsce i formy w przedziale dostępności

- **Rodzaj:** Decyzja
- **Treść:** Grafik należy do profilu. Przedział dostępności ma miejsce i formy, które prowadzący w nim prowadzi (np. „pon 9–17 tylko online”, „wt 12–15 Mokotów, stacjonarnie i online”). Oferta nie ma miejsca — deklaruje możliwe formy. Wolny termin istnieje tylko tam, gdzie forma oferty pasuje do form przedziału. Uczestnik wybiera formę przy rezerwacji. Cena oferty nie zależy od formy.
- **Powód:** odpowiada rzeczywistemu sposobowi pracy (te same usługi w różne dni z różnych miejsc, online z gabinetu); rozwiązuje pytanie, gdzie prowadzący jest danego dnia.
- **Rozważane alternatywy:** miejsce i forma w ofercie; grafik osoby lub oferty; nazwane grafiki niezależne od profili.
- **Koszt / konsekwencje:** rezerwacja zapisuje wybraną formę i miejsce (R-007). Zmiana miejsca prowadzenia spotkań (przeprowadzka, R-009) to teraz zmiana przedziałów grafiku — łączy się z otwartą kwestią „zmiana grafiku a istniejące rezerwacje”.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Grafik, Przedział dostępności, Forma spotkania, Miejsce spotkania, Wolny termin, R-010, R-016
- **Do przeglądu z Mikołajem:** do ustalenia
- **Status wpisu:** aktualny

### R-012: Przedziały grafików osoby nie nakładają się

- **Rodzaj:** Decyzja
- **Treść:** Przedziały dostępności we wszystkich grafikach (profilach) jednej osoby nie mogą się nakładać. Nestumi tego pilnuje.
- **Powód:** w każdej chwili osoba jest co najwyżej w jednym przedziale, więc wiadomo, gdzie i w jakiej formie prowadzi spotkania.
- **Rozważane alternatywy:** nakładające się grafiki chronione wyłącznie wspólną zajętością.
- **Koszt / konsekwencje:** (Claude) dodanie lub kopiowanie przedziału może zostać odrzucone z powodu przedziału innego profilu.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Przedział dostępności, Grafik, Kopiowanie grafiku, R-010, R-011
- **Do przeglądu z Mikołajem:** do ustalenia
- **Status wpisu:** aktualny

### R-013: Katalog pokazuje prowadzącego, nie profil

- **Rodzaj:** Decyzja
- **Treść:** Odwiedzający szuka prowadzących, nie profili. Prowadzący pojawia się w wynikach raz, a jego wolne terminy pochodzą z ofert pasujących do wybranych filtrów, niezależnie od profilu.
- **Powód:** odwiedzający szuka osoby; kilka kart tej samej osoby byłoby mylące.
- **Rozważane alternatywy:** osobna karta dla każdego profilu.
- **Koszt / konsekwencje:** (Claude) karta prowadzącego może grupować oferty według profili lub profesji.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Odwiedzający, Prowadzący, Profil zawodowy, Wolny termin, R-010
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-014: Przejazd między miejscami planuje prowadzący

- **Rodzaj:** Decyzja
- **Treść:** Nestumi nie pilnuje czasu przejazdu między przedziałami w różnych miejscach. Prowadzący sam zostawia odstęp w grafiku; jeśli tego nie zrobi, odpowiada za to on.
- **Powód:** prowadzący najlepiej zna swoje dojazdy; brak dodatkowej reguły w systemie.
- **Rozważane alternatywy:** automatyczny czas przejazdu między miejscami.
- **Koszt / konsekwencje:** możliwe rezerwacje „Mokotów do 15:00, Wilanów od 15:00”.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Przedział dostępności, Miejsce spotkania, R-015
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-015: Przerwa po spotkaniu ustawiana w ofercie

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Oferta ma czas trwania widoczny dla uczestnika i przerwę po spotkaniu, której uczestnik nie widzi (domyślnie 0). Czas zajętości rezerwacji = czas trwania + przerwa. Reguła kolizji i wolne terminy liczą się z czasu zajętości. Rezerwacja zapisuje także przerwę (R-007).
- **Powód:** prowadzący potrzebuje przerwy między spotkaniami w tym samym przedziale, różnej dla różnych usług (np. terapia 50 + 10, masaż 60 + 15).
- **Rozważane alternatywy:** brak przerw (sztucznie wydłużony czas trwania); jedna przerwa dla profilu lub osoby; rozpoczęcia tylko co ustalony odstęp; ręczne dzielenie przedziałów.
- **Koszt / konsekwencje:** nowe rozróżnienie: czas spotkania a czas zajętości.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Czas trwania, Przerwa po spotkaniu, Zajętość, Kolizja, Wolny termin, R-007, R-017
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-016: Oferty nie da się ograniczyć do wybranego miejsca (luka v1)

- **Rodzaj:** Decyzja — świadomie przyjęta luka
- **Treść:** Oferta profilu jest dostępna w każdym przedziale jego grafiku, którego formy pasują do oferty. Nie można jej ograniczyć do wybranego miejsca lub przedziału.
- **Powód:** prostszy model v1.
- **Rozważane alternatywy:** wybór ofert dostępnych w danym przedziale.
- **Koszt / konsekwencje:** np. terapii par nie da się ograniczyć do większego gabinetu na Wilanowie. Rozszerzenie później polega na dodaniu ograniczenia — istniejące przedziały zachowują znaczenie „wszystkie pasujące oferty”.
- **Warunek ponownego rozważenia:** prowadzący potrzebują ofert dostępnych tylko w wybranych miejscach.
- **Powiązane pojęcia i wpisy:** Oferta, Przedział dostępności, R-011
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-017: Czy przerwa po ostatnim spotkaniu musi zmieścić się w przedziale

- **Rodzaj:** Otwarte
- **Treść:** Przedział kończy się o 15:00, spotkanie trwa 14:10–15:00, przerwa wypada 15:00–15:10. Wariant „musi”: jedna reguła — cały czas zajętości mieści się w przedziale; ostatnie rozpoczęcie przesuwa się na 14:00. Wariant „nie musi”: lepsze wykorzystanie czasu, ale wyjątek w regule.
- **Czego brakuje do decyzji:** wyboru wariantu; wracamy przy regułach w kroku 3.
- **Powiązane pojęcia i wpisy:** Przerwa po spotkaniu, Przedział dostępności, Wolny termin, R-015
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** zastąpiony przez R-021

### R-018: Przedział dostępności od chwili do chwili, także przez północ

- **Rodzaj:** Decyzja
- **Treść:** Przedział dostępności to odcinek od chwili rozpoczęcia do chwili zakończenia i może przechodzić przez północ (np. 22:00–05:00). „Dzień” nie występuje w regułach — służy tylko do wyświetlania (każdy widzi godziny w swojej strefie) i do kopiowania grafiku, gdzie liczy się dzień w strefie prowadzącego.
- **Powód:** północ zależy od strefy czasowej patrzącego — spotkanie 23:30–01:00 w Polsce to 17:30–19:00 jednego dnia w Nowym Jorku. Reguła „spotkanie nie przechodzi przez północ” nie miałaby jednego znaczenia.
- **Rozważane alternatywy:** podział przedziału o północy (spotkania przez północ niemożliwe); podział z sąsiednimi przedziałami o tym samym miejscu i formach traktowanymi jako ciągłe.
- **Koszt / konsekwencje:** (Claude) kopiowanie grafiku musi ustalić dzień w strefie prowadzącego; przy zmianie czasu skopiowany przedział nocny może trwać godzinę dłużej lub krócej — otwarte w kwestii stref czasowych (krok 5).
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Przedział dostępności, Kopiowanie grafiku, Wolny termin, R-011
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-019: Krok rozpoczęć ustawiany w ofercie

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Oferta ma krok rozpoczęć — co ile minut proponujemy możliwe rozpoczęcia spotkania. Domyślnie krok równa się czasowi zajętości (czas trwania + przerwa). Krok wyznacza tylko kandydatów; o tym, czy kandydat jest wolnym terminem, decydują niezmienione reguły (mieszczenie się w przedziale, forma, brak kolizji czasu zajętości).
- **Powód:** czas zajętości różni się między ofertami; prowadzący dostaje elastyczność, a wartość domyślna układa spotkania jedno po drugim bez dziur.
- **Rozważane alternatywy:** stały krok dla całego systemu (np. 15 min); krok zawsze równy czasowi zajętości; rozpoczęcia dopasowane do końca istniejących rezerwacji.
- **Koszt / konsekwencje:** (Claude) przy różnych ofertach w jednym przedziale mogą powstawać dziury — prowadzący wpływa na nie krokiem. Krok większy niż czas zajętości działa jak dodatkowa przerwa — drugi sposób na przerwę, warto to pokazać prowadzącemu.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Krok rozpoczęć, Wolny termin, Czas trwania, Przerwa po spotkaniu, R-015, R-017
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-020: Krok rozpoczęć liczony od początku przedziału

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Kandydaci na wolny termin to początek przedziału i kolejne chwile co krok rozpoczęć oferty (przedział od 12:10, krok 60 → 12:10, 13:10, 14:10).
- **Powód:** działa dla każdego kroku, także nieokrągłego (np. 105 min); prowadzący, który chce okrągłych godzin, ustawia przedział od pełnej godziny.
- **Rozważane alternatywy:** liczenie od pełnych godzin zegara — „ładne” godziny, ale część przedziału przepada, a przy krokach niedzielących godziny kandydaci są nieprzewidywalni.
- **Koszt / konsekwencje:** godziny rozpoczęć zależą od tego, jak prowadzący ustawi początek przedziału.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Krok rozpoczęć, Przedział dostępności, Wolny termin, R-019
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-021: Przerwa po spotkaniu nie musi mieścić się w przedziale

- **Rodzaj:** Decyzja (rozstrzyga R-017)
- **Treść:** W przedziale dostępności musi mieścić się czas spotkania, nie przerwa. Przerwa może wykraczać poza koniec przedziału. Reguła kolizji nadal sprawdza czas zajętości (spotkanie + przerwa), niezależnie od przedziałów.
- **Powód:** przerwa oddziela spotkanie od kolejnego; po ostatnim spotkaniu w przedziale nie ma czego oddzielać.
- **Rozważane alternatywy:** cały czas zajętości mieści się w przedziale — jedna reguła, ale ostatnie rozpoczęcie wypada wcześniej.
- **Koszt / konsekwencje:** (Claude) przedział 12:00–15:00 przy konsultacji 50 + 10 pozwala na rozpoczęcie o 14:10. Gdy bezpośrednio po nim zaczyna się inny przedział (np. 15:00–18:00 online), rezerwacja na 15:00 zostanie odrzucona przez kolizję z przerwą do 15:10 — przerwa chroni także na granicy przedziałów.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Przerwa po spotkaniu, Przedział dostępności, Wolny termin, Kolizja, R-015, R-017
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-022: W v1 „rezerwacja” bez osobnego pojęcia „spotkanie”

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** W v1 jedna rezerwacja opisuje jedno spotkanie, więc słownik nie ma osobnego pojęcia „spotkanie”. W regułach używamy „rezerwacji”; „spotkanie” zostaje słowem potocznym (np. „czas spotkania”).
- **Powód:** relacja 1:1 w v1; mniej pojęć do pilnowania.
- **Rozważane alternatywy:** osobne pojęcie „spotkanie” już teraz.
- **Koszt / konsekwencje:** (Claude) przy zajęciach grupowych (jedno spotkanie, wiele rezerwacji) pojęcie trzeba będzie wprowadzić i rozdzielić reguły.
- **Warunek ponownego rozważenia:** zajęcia grupowe albo inny przypadek, w którym jedno spotkanie ma kilka rezerwacji.
- **Powiązane pojęcia i wpisy:** Rezerwacja
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-023: Nieudana próba rezerwacji niczego nie tworzy

- **Rodzaj:** Decyzja
- **Treść:** Jeśli w chwili złożenia rezerwacji termin nie jest już wolny, Nestumi nie tworzy rezerwacji — ani w stanie „odrzucona”, ani żadnym innym. Uczestnik dostaje informację, że termin jest zajęty.
- **Powód:** do uzupełnienia
- **Rozważane alternatywy:** rezerwacja w stanie „odrzucona”.
- **Koszt / konsekwencje:** (Claude) brak historii nieudanych prób. Razem z automatycznym potwierdzeniem oznacza, że każda istniejąca rezerwacja powstaje od razu jako potwierdzona — do sprawdzenia przy cyklu życia rezerwacji (krok 4).
- **Warunek ponownego rozważenia:** potrzeba analizy nieudanych prób albo ręczna akceptacja prowadzącego.
- **Powiązane pojęcia i wpisy:** Rezerwacja, Złożenie rezerwacji, Potwierdzenie, R-003
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-024: Brak przerwy przed spotkaniem

- **Rodzaj:** Decyzja
- **Treść:** Oferta ma tylko przerwę po spotkaniu (R-015). Przerwy przed spotkaniem nie ma.
- **Powód:** do uzupełnienia
- **Rozważane alternatywy:** przerwa przed i po spotkaniu, ustawiane osobno w ofercie.
- **Koszt / konsekwencje:** (Claude) czas na przygotowanie przed pierwszym spotkaniem w przedziale prowadzący zapewnia, ustawiając początek przedziału; między spotkaniami wystarcza przerwa po poprzednim.
- **Warunek ponownego rozważenia:** usługi wymagające przygotowania tuż przed spotkaniem, którego nie da się zapewnić przerwą po poprzednim.
- **Powiązane pojęcia i wpisy:** Przerwa po spotkaniu, R-015, R-021
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-025: Osoba nie może zarezerwować własnej oferty

- **Rodzaj:** Decyzja
- **Treść:** Uczestnik rezerwacji nie może być prowadzącym tej samej oferty.
- **Powód:** do uzupełnienia
- **Rozważane alternatywy:** pozwolić — np. jako sposób blokowania sobie czasu.
- **Koszt / konsekwencje:** (Claude) prowadzący, który chce zablokować czas, robi to przez grafik, nie przez rezerwację.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Uczestnik, Prowadzący, Rezerwacja
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-026: Rejestracja w v1, bez weryfikacji e-maila i resetu hasła

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** W v1 osoba zakłada konto przez rejestrację: e-mail i hasło. E-mail jest unikalny. Nie ma weryfikacji e-maila ani resetu hasła — świadoma luka do czasu pojawienia się kanału e-mail. Konta testowe nadal tworzy seeder.
- **Powód:** (Claude) aplikacja kompletna bez ręcznego zakładania kont; materiał do etapu 6 (hasła, walidacja, sesje) oraz etapów 4 i 7 (unikalność e-maila przy równoczesnych rejestracjach).
- **Rozważane alternatywy:** tylko przygotowane konta testowe; pełna rejestracja z weryfikacją e-maila i resetem hasła.
- **Koszt / konsekwencje:** zapomniane hasło oznacza utratę dostępu do konta; nieprawdziwy e-mail nie jest wykrywany.
- **Warunek ponownego rozważenia:** pojawienie się kanału e-mail (rozszerzenie z R-008).
- **Powiązane pojęcia i wpisy:** Osoba, R-002, R-008, R-027
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-027: Każda zarejestrowana osoba może rezerwować i zostać prowadzącym

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Każda zarejestrowana osoba może rezerwować. Prowadzącym zostaje, zakładając profil zawodowy — bez osobnego typu konta i bez akceptacji przez kogokolwiek. Może też publikować oferty bez akceptacji.
- **Powód:** zgodne z modelem „osoba ma jedno konto i może być uczestnikiem i prowadzącym”; projekt edukacyjny.
- **Rozważane alternatywy:** osobny typ konta prowadzącego; akceptacja profilu lub oferty przez administratora.
- **Koszt / konsekwencje:** (Claude) osoba bez kwalifikacji może opublikować np. „konsultację psychiatryczną”. W v1 ryzyko przyjęte świadomie, bez weryfikacji (R-029).
- **Warunek ponownego rozważenia:** rzeczywiste użycie platformy albo wprowadzenie weryfikacji kwalifikacji.
- **Powiązane pojęcia i wpisy:** Osoba, Prowadzący, Profil zawodowy, R-010, R-026
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-028: Anonimowy odwiedzający należy do obszaru dostępu i kont

- **Rodzaj:** Założenie (do sprawdzenia w kroku 6)
- **Treść:** Pojęcie „anonimowy odwiedzający” istnieje w obszarze dostępu i kont: opisuje, czego nie wolno bez zalogowania. Katalog pokazuje publiczne informacje wszystkim tak samo, więc nie musi wiedzieć, kto patrzy. Rezerwacja zawsze ma zalogowaną osobę.
- **Powód:** rezerwacja powstaje dopiero przy złożeniu, a to wymaga konta (R-002, R-003, R-023) — w obszarze rezerwacji odwiedzający się nie pojawia.
- **Rozważane alternatywy:** obszar rezerwacji; katalog.
- **Koszt / konsekwencje:** (Claude) założenie przestaje działać, jeśli katalog zacznie pokazywać zalogowanym coś więcej niż anonimowym albo jeśli wybór terminu sprzed logowania stanie się czymś trwałym w rezerwacji (R-005).
- **Warunek ponownego rozważenia:** krok 6; różne widoki katalogu dla zalogowanych i anonimowych; rozstrzygnięcie R-005.
- **Powiązane pojęcia i wpisy:** Anonimowy odwiedzający, R-001, R-002, R-004, R-005
- **Do przeglądu z Mikołajem:** tak, razem z granicami kontekstów
- **Status wpisu:** aktualny

### R-029: Brak weryfikacji kwalifikacji w v1

- **Rodzaj:** Decyzja
- **Treść:** W v1 platforma nie weryfikuje tożsamości ani kwalifikacji prowadzącego. Profesja i kwalifikacje są tylko deklarowane przez prowadzącego w profilu zawodowym. Ryzyko mylącego charakteru oferty jest przyjęte świadomie.
- **Powód:** projekt edukacyjny z fikcyjnymi danymi; brak roli administratora; dla większości profesji (np. psychoterapeuta, instruktor jogi) nie istnieje publiczny rejestr do automatycznego sprawdzenia.
- **Rozważane alternatywy:** oświadczenie w regulaminie; jawne oznaczenie „kwalifikacje deklarowane, niesprawdzone”; numer z rejestru zawodu do samodzielnego sprawdzenia przez uczestnika; automatyczne sprawdzenie w rejestrze; ręczna weryfikacja dokumentów przez administratora; weryfikacja tożsamości.
- **Koszt / konsekwencje:** (Claude) osoba bez kwalifikacji może opublikować ofertę wyglądającą na profesjonalną pomoc w zdrowiu psychicznym. Późniejsze dodanie weryfikacji jest zmianą przyrostową: istniejące profile stają się po prostu „niezweryfikowane”.
- **Warunek ponownego rozważenia:** rzeczywiste użycie platformy z prawdziwymi prowadzącymi; wprowadzenie roli administratora.
- **Powiązane pojęcia i wpisy:** Profil zawodowy, Profesja, Charakter usługi, R-027
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-030: Charakter oferty wynika z rodzaju usługi

- **Rodzaj:** Decyzja (przyjęta propozycja Claude — uproszczony wariant D)
- **Treść:** Każdy rodzaj usługi ma na stałe przypisany charakter usługi, a oferta bierze charakter ze swojego rodzaju. Rodzaje ze zdrowia psychicznego może wybrać tylko profesja ze zdrowia psychicznego. Rodzaje z dobrostanu może wybrać każda profesja.
- **Powód:** charakter oferty wynika z tego, czym jest usługa, a nie z tego, kto ją prowadzi — psycholog prowadzący medytację nie oznaczy jej jako zdrowia psychicznego. Przy braku weryfikacji kwalifikacji (R-029) blokuje najgroźniejsze przekłamanie: dobrostan udający pomoc psychologiczną.
- **Rozważane alternatywy:** A — charakter z profesji (medytacja psychologa wychodzi jako zdrowie psychiczne); B — swobodny wybór przy ofercie (instruktor jogi może oznaczyć ofertę jako zdrowie psychiczne); C — profesja wyznacza górną granicę, prowadzący wybiera (pozwala na dobry wybór, ale go nie wymusza); pełne D z tabelą „profesja → dozwolone rodzaje” (więcej do utrzymania).
- **Koszt / konsekwencje:** (Claude) poprawność zależy od listy rodzajów — medytacja jako część terapii wymaga osobnego rodzaju ze zdrowia psychicznego (np. MBCT, trening relaksacyjny w terapii). Profil ze zdrowia psychicznego może mieć oferty dobrostanowe, więc mogą one dzielić przedział z konsultacjami (doprecyzowanie R-010). Profesja nadal ma przypisany charakter.
- **Warunek ponownego rozważenia:** usługi, których charakteru nie da się ustalić z samego rodzaju; potrzeba ograniczenia rodzajów do konkretnych profesji (pełne D).
- **Powiązane pojęcia i wpisy:** Charakter usługi, Rodzaj usługi, Profesja, Oferta, R-010, R-029, R-031
- **Do przeglądu z Mikołajem:** tak — kluczowa reguła modelu oferty
- **Status wpisu:** aktualny; zaostrzony przez R-032 — rodzaje ze zdrowia psychicznego wymagają konkretnej profesji

### R-031: Zamknięte listy rodzajów usług i profesji tworzone przez seeder

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Rodzaj usługi i profesję wybiera się z zamkniętych list. Prowadzący nie dopisuje własnego rodzaju ani profesji. W v1 obie listy tworzy seeder.
- **Powód:** wymagane przez R-030 i R-032 — charakter musi być przypisany do każdego rodzaju i profesji z góry, a rodzaje ze zdrowia psychicznego wskazują wymaganą profesję; w v1 nie ma roli administratora.
- **Rozważane alternatywy:** rodzaj lub profesja wpisywane swobodnie przez prowadzącego; listy z możliwością dopisania własnej pozycji.
- **Koszt / konsekwencje:** usługi ani profesji spoza listy nie da się użyć; każda nowa usługa lub profesja wymaga zmiany listy.
- **Warunek ponownego rozważenia:** rola administratora albo prowadzący regularnie nie znajdują swojej usługi lub profesji na liście.
- **Powiązane pojęcia i wpisy:** Rodzaj usługi, Profesja, Charakter usługi, R-030, R-032
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-032: Rodzaje ze zdrowia psychicznego wymagają konkretnej profesji

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Każdy rodzaj usługi ze zdrowia psychicznego wymaga konkretnej profesji prowadzącego, np. konsultacja psychologiczna — psycholog; psychoterapia, MBCT — psychoterapeuta; konsultacja psychiatryczna — psychiatra. Rodzaje z dobrostanu może wybrać każda profesja. Dziedziny są rozdzielone na poziomie oferty, nie profilu ani grafiku.
- **Powód:** nie każdy psycholog jest psychoterapeutą, a psychiatra to lekarz — uczestnik musi widzieć, kto naprawdę prowadzi usługę. Wspólny profil i grafik (R-010) zostają, więc psycholożka-psychoterapeutka nadal przyjmuje na obie usługi w jednym przedziale. Przyszła weryfikacja dokumentów może dołączyć się do profesji, a nie do całego profilu.
- **Rozważane alternatywy:** osobny charakter dla psychiatrii albo psychologii (psychiatra-psychoterapeuta potrzebowałby dwóch profili i grafików); jeden profil na profesję (prowadzący musi z góry dzielić czas między grafiki, odrzucone już w R-010); tylko R-030 bez wymagania profesji (psycholog może opublikować psychoterapię).
- **Koszt / konsekwencje:** (Claude) seeder utrzymuje listę „rodzaj ze zdrowia psychicznego → wymagana profesja”. Reguła wymaga zamkniętej listy profesji (R-031) — dowolnie wpisana „psychoterapeutka” nie zostałaby rozpoznana. Przy deklarowanych profesjach (R-029) nie chroni przed osobą, która wpisze fałszywą profesję.
- **Warunek ponownego rozważenia:** usługa ze zdrowia psychicznego, którą może prowadzić kilka profesji; wprowadzenie weryfikacji dokumentów.
- **Powiązane pojęcia i wpisy:** Rodzaj usługi, Profesja, Charakter usługi, Profil zawodowy, R-010, R-029, R-030, R-031, R-033
- **Do przeglądu z Mikołajem:** tak, razem z R-030
- **Status wpisu:** aktualny

### R-033: Dwie wartości charakteru usługi

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Charakter usługi ma dwie wartości: zdrowie psychiczne i dobrostan. Psychiatrię, psychologię i psychoterapię rozróżniają rodzaj usługi i profesja (R-032), nie charakter.
- **Powód:** charakter służy do grupowania profesji w profilu i ofert w katalogu; osobne wartości rozdzieliłyby profile i grafiki prowadzących z kilkoma profesjami, np. psychiatry-psychoterapeuty.
- **Rozważane alternatywy:** trzy wartości (psychiatria, psychologia, dobrostan); osobne wartości dla rozwoju osobistego lub usług medycznych.
- **Koszt / konsekwencje:** dodanie wartości później wymaga przypisania części rodzajów do nowego charakteru i ewentualnego podziału profili.
- **Warunek ponownego rozważenia:** reguła, która traktuje jedną z dziedzin inaczej (np. recepty, refundacja); usługa, której nie da się przypisać do żadnej z dwóch wartości.
- **Powiązane pojęcia i wpisy:** Charakter usługi, Profil zawodowy, R-010, R-030, R-032
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-034: Link do spotkania online w rezerwacji

- **Rodzaj:** Decyzja
- **Treść:** Rezerwacja w formie online ma link do spotkania, który prowadzący wkleja ręcznie po złożeniu rezerwacji; system go nie generuje. Prowadzący może link zmienić, a rezerwacja zawsze pokazuje aktualny link — link nie jest warunkiem zapisanym w chwili złożenia (odstępstwo od R-007). Link widzą tylko prowadzący i uczestnik tej rezerwacji, dopóki rezerwacja nie jest anulowana.
- **Powód:** osobny pokój dla każdego spotkania — osoba, która znała link z wcześniejszej rezerwacji, nie wejdzie na cudze spotkanie; ważne przy terapii.
- **Rozważane alternatywy:** stały link w profilu; link w ofercie; link w przedziale dostępności (wszystkie dają ten sam link wielu uczestnikom); automatyczne tworzenie spotkania przez integrację (poza v1 — zewnętrzny kalendarz).
- **Koszt / konsekwencje:** (Claude) rezerwacja online powstaje bez linku i jest go pozbawiona, dopóki prowadzący go nie doda — kiedy prowadzący ma to zrobić i co, jeśli linku brak w chwili spotkania, otwarte (krok 2). Dodanie i zmiana linku to kandydaci na zdarzenia wywołujące powiadomienie (krok 3). Brak linku nie jest osobnym stanem rezerwacji — do sprawdzenia w kroku 4.
- **Warunek ponownego rozważenia:** prowadzący regularnie zapominają dodać link; integracja z narzędziem do spotkań online.
- **Powiązane pojęcia i wpisy:** Link do spotkania, Forma spotkania, Rezerwacja, Powiadomienie, R-007, R-011
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** zastąpiony przez R-039

### R-035: Styk rezerwacji nie jest kolizją

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Rezerwacja zaczynająca się dokładnie w chwili zakończenia czasu zajętości innej rezerwacji tego samego prowadzącego nie koliduje z nią. Przykład: terapia 12:00–12:50 z przerwą 10 min zajmuje prowadzącego do 13:00; inna terapia od 13:00 jest dozwolona, od 12:59 — nie.
- **Powód:** prowadzący może ustawić spotkania jedno po drugim, a odstęp między nimi wyznacza przerwa po spotkaniu (R-015), nie ukryta reguła.
- **Rozważane alternatywy:** (Claude) zakaz styku — wymuszałby niewidoczny odstęp nawet przy przerwie 0.
- **Koszt / konsekwencje:** (Claude) czas zajętości liczy się od chwili rozpoczęcia włącznie do chwili zakończenia wyłącznie. Czas przejazdu przy styku spotkań w różnych miejscach planuje prowadzący (R-014).
- **Warunek ponownego rozważenia:** prowadzący oczekują minimalnego odstępu niezależnego od przerwy w ofercie.
- **Powiązane pojęcia i wpisy:** Kolizja, Zajętość, Przerwa po spotkaniu, R-014, R-015
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-036: Zajętość obejmuje rezerwacje w obu rolach

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Zajętość osoby to wszystkie jej aktywne rezerwacje: jako prowadzącej (czas trwania + przerwa po spotkaniu) i jako uczestniczki (sam czas trwania — przerwa należy do prowadzącego). Nowa rezerwacja, w dowolnej roli, nie może kolidować z zajętością żadnej ze swoich osób. Przedział dostępności może nachodzić na rezerwację osoby jako uczestniczki; ten czas po prostu nie daje wolnych terminów. Przykład: Anna jest na masażu u Marka 10:00–11:00 — Kasia nie zarezerwuje u niej konsultacji na 10:30, a Anna nie zapisze się na inne spotkanie o 10:30.
- **Powód:** osoba nie może być w dwóch miejscach naraz, niezależnie od roli; jedna reguła zamyka też przypadek, gdy przedział zostanie dodany lub skopiowany po rezerwacji jako uczestniczka.
- **Rozważane alternatywy:** zajętość tylko z rezerwacji jako prowadzącej (osoba sama pilnuje grafiku); zakaz rezerwacji jako uczestniczka w czasie własnego przedziału dostępności (propozycja Klaudii — surowsza, wymaga drugiej reguły i blokuje osoby z szerokim grafikiem); odrzucenie dodania lub skopiowania przedziału nachodzącego na rezerwację jako uczestniczka.
- **Koszt / konsekwencje:** (Claude) zajętość przestaje być pojęciem tylko prowadzącego. Uczestnik nie widzi powodu niedostępności terminu, co chroni prywatność prowadzącej. Uczestnik nie zarezerwuje dwóch spotkań w tym samym czasie.
- **Warunek ponownego rozważenia:** prowadzący chcą, by grafik był wiążącą obietnicą dostępności; spotkania grupowe lub z wieloma uczestnikami.
- **Powiązane pojęcia i wpisy:** Zajętość, Kolizja, Wolny termin, Przedział dostępności, R-010, R-012, R-015, R-027, R-035
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-037: Termin przestał być wolny przed złożeniem rezerwacji

- **Rodzaj:** Decyzja
- **Treść:** Jeśli w chwili złożenia rezerwacji wybrany termin nie jest już wolnym terminem, rezerwacja nie powstaje (R-023). Gdy powodem jest kolizja z inną rezerwacją samego uczestnika, widzi on informację, że ma już wtedy rezerwację. W pozostałych przypadkach widzi informację, że termin nie jest już dostępny. W obu przypadkach dostaje przycisk powrotu do wybierania terminu; system nie podsuwa konkretnych terminów. Przykład: Kasia czyta podsumowanie terminu u Ewy we wtorek 12:00, w tym czasie Tomek rezerwuje ten termin — Kasia po kliknięciu „Zarezerwuj” dostaje odmowę i przycisk wyboru innego terminu.
- **Powód:** v1 bez płatności ma krótki krok między wyborem a złożeniem, a spór dwóch osób o jeden termin u jednego prowadzącego jest rzadki. Informacja o własnej kolizji dotyczy danych uczestnika, więc niczego nie zdradza o prowadzącym.
- **Rozważane alternatywy:** czasowe wstrzymanie terminu, np. na 10 minut (odłożone do `docs/brainstorming.md`, 5.2 — nie zastępuje odmowy, bo wstrzymanie może wygasnąć); podsuwanie najbliższych wolnych terminów tej samej oferty; jeden komunikat dla wszystkich powodów.
- **Koszt / konsekwencje:** (Claude) komunikat ogólny nie mówi „ktoś zarezerwował”, bo termin może przestać być wolny także przez rezerwację prowadzącej jako uczestniczki (R-036), usunięcie przedziału lub wycofanie oferty. Równoczesne kliknięcie dwóch osób rozstrzyga reguła, że powstaje co najwyżej jedna rezerwacja — sposób zapewnienia tego to etap 7.
- **Warunek ponownego rozważenia:** płatność online lub dłuższy formularz przed złożeniem rezerwacji.
- **Powiązane pojęcia i wpisy:** Złożenie rezerwacji, Wolny termin, Kolizja, Zajętość, R-003, R-023, R-028, R-036
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-038: Powiadomienia poza v1

- **Rodzaj:** Decyzja (przyjęta propozycja Claude) — zmiana zakresu, zastępuje R-008
- **Treść:** W v1 nie ma powiadomień w aplikacji. Uczestnik i prowadzący dowiadują się o zmianach, np. o anulowaniu przez drugą stronę, z listy swoich rezerwacji.
- **Powód:** w etapach 6–8 powiadomienia to głównie dodatkowy zapis i odczyt, bez nowego materiału. Pełną wartość do nauki dają w etapach 11 (zdarzenie rozsyłane do niezależnych odbiorców, transactional outbox), 16 (aktualizacje na żywo) i 17 (Web Push). Odciąża v1, które i tak nie mieści się w etapie 6 (`6-8-roadmap.md`).
- **Rozważane alternatywy:** powiadomienia w aplikacji w v1 (R-008).
- **Koszt / konsekwencje:** uczestnik dowie się o anulowaniu przez prowadzącego dopiero, gdy zajrzy na listę rezerwacji — dotyczy też przeprowadzki (R-009). Świadomie przyjęte, bo projekt nie ma prawdziwych użytkowników. (Claude) Czy lista pokazuje, kto anulował, pozostaje otwarte (kroki 3–4).
- **Warunek ponownego rozważenia:** etap 11 — powiadomienie jako odbiorca zdarzenia; najpierw zwykły zapis, potem przeniesienie do workera.
- **Powiązane pojęcia i wpisy:** Powiadomienie, Anulowanie, R-008, R-009, R-039
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-039: Link do spotkania online poza v1

- **Rodzaj:** Decyzja (przyjęta propozycja Claude) — zastępuje R-034
- **Treść:** W v1 aplikacja nie przekazuje linku do spotkania online. Rezerwacja w formie online nie daje uczestnikowi w aplikacji żadnej drogi do linku — świadoma luka v1.
- **Powód:** link był wyjątkiem od R-007 (zmienia się po złożeniu rezerwacji), otwierał pytanie o brak linku w chwili spotkania i dokładał zdarzenia do powiadomień, których w v1 nie ma (R-038). Uprawnienia do danych rezerwacji ćwiczę i tak przy anulowaniu.
- **Rozważane alternatywy:** link w rezerwacji wklejany przez prowadzącego (R-034).
- **Koszt / konsekwencje:** forma online w v1 jest tylko deklaracją sposobu spotkania. (Claude) Powrót do R-034 to dodanie nowej informacji do rezerwacji, bez zmiany istniejących danych.
- **Warunek ponownego rozważenia:** powrót powiadomień (R-038); integracja z narzędziem do spotkań online (`docs/brainstorming.md`, 5.6); prawdziwi użytkownicy.
- **Powiązane pojęcia i wpisy:** Link do spotkania, Forma spotkania, R-007, R-034, R-038
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-040: Opublikowana oferta bez wolnych terminów jest widoczna w katalogu

- **Rodzaj:** Decyzja
- **Treść:** Opublikowana oferta jest widoczna w katalogu także wtedy, gdy nie ma żadnego wolnego terminu. Odwiedzający może ją otworzyć, ale nie ma czego wybrać (UC-3, rozszerzenie w kroku 2).
- **Powód:** odwiedzający wie, że prowadzący ma taką usługę, nawet jeśli teraz nie ma terminów.
- **Rozważane alternatywy:** (Claude) ukrywanie ofert bez wolnych terminów.
- **Koszt / konsekwencje:** (Claude) prowadzący, który przestał ustawiać grafik, zostaje w katalogu z ofertami bez terminów; filtr po dacie lub terminie, jeśli powstanie, i tak takich ofert nie pokaże.
- **Warunek ponownego rozważenia:** (Claude) katalog zapełnia się ofertami bez terminów.
- **Powiązane pojęcia i wpisy:** Oferta, Wolny termin, R-006, R-013
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-041: Anulowanie przez prowadzącego zwalnia czas tak samo jak przez uczestnika

- **Rodzaj:** Decyzja
- **Treść:** Niezależnie od tego, kto anuluje rezerwację, czas spotkania razem z przerwą przestaje być zajęty dla obu osób. Wolne terminy prowadzącego pojawiają się znowu tam, gdzie nadal istnieje przedział dostępności. Anulowanie przez uczestnika i przez prowadzącego to jeden przypadek użycia (UC-4).
- **Powód:** skutek anulowania zależy od ról w rezerwacji, a nie od tego, kto anulował — kroki i wynik są takie same.
- **Rozważane alternatywy:** (Claude) anulowanie przez prowadzącego nie zwalnia terminu; dwa osobne przypadki użycia.
- **Koszt / konsekwencje:** (Claude) prowadzący, który anuluje, bo nie może prowadzić (np. choroba), musi osobno usunąć przedział dostępności (UC-12) — inaczej termin od razu wraca jako wolny i ktoś może go zarezerwować.
- **Warunek ponownego rozważenia:** (Claude) prowadzący często dostają nowe rezerwacje na czas, który właśnie odwołali.
- **Powiązane pojęcia i wpisy:** Anulowanie, Zajętość, Przedział dostępności, R-009, R-036
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-042: Anulowanie jest nieodwracalne

- **Rodzaj:** Decyzja
- **Treść:** Anulowanej rezerwacji nie da się przywrócić. Przed anulowaniem system pokazuje szczegóły rezerwacji (data, godzina, oferta, druga osoba) i prosi o zatwierdzenie (UC-4).
- **Powód:** (Claude) prostota v1 — przywrócenie wymagałoby ponownego sprawdzenia, czy czas jest nadal wolny, czyli w praktyce nowej rezerwacji.
- **Rozważane alternatywy:** (Claude) cofnięcie anulowania przez krótki czas po nim.
- **Koszt / konsekwencje:** (Claude) pomyłka kosztuje: uczestnik może zarezerwować ponownie (UC-3), ale termin mógł już zająć ktoś inny. Jedyną ochroną jest potwierdzenie ze szczegółami.
- **Warunek ponownego rozważenia:** (Claude) osoby często anulują nie tę rezerwację.
- **Powiązane pojęcia i wpisy:** Anulowanie, Rezerwacja, R-043
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-043: Anulować można do rozpoczęcia spotkania

- **Rodzaj:** Decyzja
- **Treść:** Uczestnik i prowadzący mogą anulować aktywną rezerwację do chwili rozpoczęcia spotkania. Po rozpoczęciu anulowanie nie jest możliwe (UC-4, warunek wstępny).
- **Powód:** (Claude) najprostsza granica, ta sama dla obu ról.
- **Rozważane alternatywy:** (Claude) minimalne wyprzedzenie dla uczestnika (np. 24 h); różne granice dla uczestnika i prowadzącego.
- **Koszt / konsekwencje:** (Claude) uczestnik może anulować minutę przed spotkaniem, a prowadzący traci ten czas, bo nikt go już nie zarezerwuje. Spotkanie może się zacząć w trakcie anulowania (otwarta lista o 9:59, zatwierdzenie o 10:01) — potrzebne rozszerzenie w UC-4.
- **Warunek ponownego rozważenia:** (Claude) prowadzący tracą dużo czasu przez anulowania tuż przed spotkaniem.
- **Powiązane pojęcia i wpisy:** Anulowanie, Rezerwacja, R-041, R-042
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-044: Dodawanie przedziałów — wszystkie albo żaden

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** Gdy prowadzący dodaje kilka przedziałów dostępności naraz, a choć jeden jest niepoprawny, system nie zapisuje żadnego. Wpisane przedziały nie znikają: system pokazuje, który jest niepoprawny i dlaczego, a prowadzący poprawia go i zapisuje ponownie (UC-11).
- **Powód:** stan jest zawsze jasny — zapisane wszystko albo nic. Przy częściowym zapisie ponowne wysłanie całego formularza zderzyłoby poprawne przedziały z ich już zapisanymi kopiami.
- **Rozważane alternatywy:** zapisać poprawne, odrzucić tylko niepoprawne.
- **Koszt / konsekwencje:** jedna pomyłka blokuje zapis całego tygodnia, dopóki prowadzący jej nie poprawi.
- **Warunek ponownego rozważenia:** prowadzący dodają naraz bardzo dużo przedziałów i często utykają na pojedynczych błędach.
- **Powiązane pojęcia i wpisy:** Przedział dostępności, Grafik, R-012, R-045
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-045: Odrzucany jest tylko przedział w całości w przeszłości

- **Rodzaj:** Decyzja (przyjęta propozycja Claude)
- **Treść:** System odrzuca przedział dostępności, który kończy się przed chwilą zapisu. Przedział, który zaczął się w przeszłości, ale jeszcze trwa (np. dziś 8:00–17:00 dodany o 10:00), jest przyjmowany (UC-11).
- **Powód:** część w przeszłości i tak nie daje wolnych terminów; ścisła reguła odrzucałaby przedziały poprawne w chwili wpisywania (formularz otwarty o 9:58, zapis o 10:01).
- **Rozważane alternatywy:** odrzucać każdy przedział, który zaczyna się w przeszłości.
- **Koszt / konsekwencje:** w grafiku zostają przedziały z częścią w przeszłości. Zakłada regułę, że wolny termin zawsze zaczyna się w przyszłości — do spisania w kroku 3.
- **Warunek ponownego rozważenia:** do uzupełnienia
- **Powiązane pojęcia i wpisy:** Przedział dostępności, Wolny termin, R-018, R-044
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

### R-046: Katalog pokazuje wolne terminy niezależnie od zajętości oglądającego

- **Rodzaj:** Decyzja
- **Treść:** Wolne terminy w katalogu są takie same dla wszystkich oglądających — zalogowanych i anonimowych. Katalog nie ukrywa terminów, które kolidują z zajętością oglądającej osoby; kolizję wykrywa sprawdzenie przy składaniu rezerwacji (UC-3, krok 5, rozszerzenie 5b).
- **Powód:** wolny termin wynika z oferty, grafiku i zajętości prowadzącego, nie oglądającego — definicja ze słownika zostaje bez zmian. (Claude) Prostsze: jedna lista wolnych terminów zamiast osobnej dla każdej osoby.
- **Rozważane alternatywy:** (Claude) ukrywanie kolidujących terminów przed zalogowaną osobą; pokazywanie ich z oznaczeniem „masz wtedy inną rezerwację” (decyzja o interfejsie, na później).
- **Koszt / konsekwencje:** osoba może wybrać termin, którego nie zarezerwuje, i dowiedzieć się o tym dopiero przy składaniu rezerwacji.
- **Warunek ponownego rozważenia:** (Claude) osoby często trafiają na odmowę z powodu własnej kolizji.
- **Powiązane pojęcia i wpisy:** Wolny termin, Zajętość, Kolizja, R-028, R-036, R-037
- **Do przeglądu z Mikołajem:** nie
- **Status wpisu:** aktualny

<!--
Szablon nowego wpisu:

### R-XXX: <krótki tytuł>

- **Rodzaj:**
- **Treść:**
- **Powód:**
- **Rozważane alternatywy:**
- **Koszt / konsekwencje:**
- **Warunek ponownego rozważenia:**
- **Powiązane pojęcia i wpisy:**
- **Do przeglądu z Mikołajem:** tak / nie
- **Status wpisu:** aktualny / zastąpiony przez R-…

Założenie: wystarczą Treść i Powód.
Otwarte: zamiast Powodu wpisz, czego brakuje do decyzji i w którym kroku wracamy.
-->
