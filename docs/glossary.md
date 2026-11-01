# Nestumi — słownik pojęć domenowych

Wspólny język pierwszej wersji. Definicje bez odwołań do technologii. Zakres: `docs/project-brief.md`. Reguły i decyzje: `docs/decisions.md`. Otwarte pytania do pojęć: `uwagi_glossary.md`.

**Kiedy dodaję pojęcie:** gdy występuje w regule lub cyklu życia albo spowodowało nieporozumienie. Słownik mówi, co słowo znaczy — nie, jakie reguły go dotyczą.

## Oferta, czas i rezerwacja

### Oferta

- **Definicja:** Przygotowany przez prowadzącego opis usługi, którą po publikacji można zarezerwować: rodzaj usługi, charakter usługi, profesja, w ramach której prowadzący ją realizuje, opis, czas trwania, przerwa po spotkaniu, krok rozpoczęć, możliwe formy spotkania oraz cena. Należy do jednego profilu zawodowego. Najpierw jest szkicem; po publikacji pojawia się w katalogu i można ją rezerwować.
- **Nazwa w kodzie (EN):** Offer
- **Przykład:** Anna w profilu „Joga” publikuje „Joga indywidualna, 60 min, stacjonarnie lub online, 150 zł” jako instruktorka jogi.
- **To nie jest:** konkretna godzina ani wolny termin; to nie jest też profil prowadzącego.

### Grafik

- **Definicja:** Zbiór przedziałów dostępności jednego profilu zawodowego na konkretne daty. Każdy profil ma jeden grafik.
- **Nazwa w kodzie (EN):** Schedule
- **Przykład:** Grafik profilu „Psychologia” Maćka na tydzień 2–8 listopada: poniedziałek 9:00–17:00 online; wtorek 12:00–15:00 Mokotów, stacjonarnie i online.
- **To nie jest:** stała reguła („każdy wtorek”); to nie jest lista rezerwacji.

### Przedział dostępności

- **Definicja:** Ciągły odcinek czasu od chwili rozpoczęcia do chwili zakończenia, w którym prowadzący deklaruje gotowość prowadzenia spotkań w ramach profilu, razem z miejscem i formami, które w tym czasie prowadzi. Może przechodzić przez północ.
- **Nazwa w kodzie (EN):** AvailabilityWindow
- **Przykład:** Wtorek 3 listopada, 12:00–15:00, gabinet na Mokotowie, stacjonarnie i online. Poniedziałek 2 listopada, 9:00–17:00, tylko online.
- **To nie jest:** wolny termin dla konkretnej oferty; nie oznacza, że cały odcinek jest wolny — część mogą zajmować rezerwacje.

### Wolny termin

- **Definicja:** Możliwe rozpoczęcie i zakończenie spotkania dla konkretnej oferty, w którym czas spotkania mieści się w przedziale dostępności profilu tej oferty, forma oferty pasuje do form przedziału, a czas zajętości nie koliduje z zajętością prowadzącego.
- **Nazwa w kodzie (EN):** AvailableSlot
- **Przykład:** Przy przedziale 9:00–13:00 i ofercie 60 min wolnym terminem może być 9:00–10:00; przy rezerwacji 10:00–11:00 nie jest nim 9:30–10:30.
- **To nie jest:** coś, co prowadzący sam tworzy — wynika z grafiku, czasu trwania oferty i istniejących rezerwacji.

### Rezerwacja

- **Definicja:** Zobowiązanie uczestnika i prowadzącego do spotkania w ramach konkretnej oferty, w konkretnym czasie. Pozostaje w historii także po anulowaniu.
- **Nazwa w kodzie (EN):** Booking
- **Przykład:** Ola zarezerwowała u Anny „Joga indywidualna” na wtorek 3 listopada 10:00–11:00.
- **To nie jest:** wolny termin; nieudana próba rezerwacji.

### Czas trwania

- **Definicja:** Ustalona długość spotkania w ramach danej oferty. W v1 jedna oferta ma jeden czas trwania.
- **Nazwa w kodzie (EN):** Duration
- **Przykład:** Medytacja — 120 min, zajęcia oddechowe — 30 min.
- **To nie jest:** czas zajętości (czas trwania + przerwa po spotkaniu, R-015); czas przejazdu.

### Przerwa po spotkaniu

- **Definicja:** Ustalony w ofercie czas po spotkaniu, w którym prowadzący nie może mieć kolejnego spotkania. Uczestnik go nie widzi. Domyślnie 0.
- **Nazwa w kodzie (EN):** BufferAfter
- **Przykład:** Terapia: 50 min + 10 min przerwy — rezerwacja 12:00–12:50 zajmuje prowadzącego do 13:00. Masaż: 60 min + 15 min na przygotowanie gabinetu.
- **To nie jest:** czas przejazdu między miejscami (planuje go prowadzący, R-014); część czasu trwania widoczna dla uczestnika.

### Krok rozpoczęć

- **Definicja:** Ustalony w ofercie odstęp między kolejnymi proponowanymi rozpoczęciami spotkania. Domyślnie równy czasowi zajętości (czas trwania + przerwa). Wyznacza tylko kandydatów na wolny termin.
- **Nazwa w kodzie (EN):** StartInterval
- **Przykład:** Konsultacja 50 + 10 min, krok 60 → kandydaci 12:00, 13:00, 14:00. Oddech 30 min, krok 30 → 12:00, 12:30, 13:00…
- **To nie jest:** przerwa po spotkaniu; reguła kolizji — kandydat nadal musi spełnić reguły wolnego terminu.

## Kto jest kim

### Osoba

- **Definicja:** Człowiek korzystający z Nestumi. Ma jedno konto, na które się loguje. Ta sama osoba może prowadzić spotkania i uczestniczyć w cudzych.
- **Nazwa w kodzie (EN):** Person
- **Przykład:** Anna jest psycholożką i instruktorką jogi, a sama rezerwuje masaż u Marka.
- **To nie jest:** rola (prowadzący, uczestnik).

### Prowadzący

- **Definicja:** Rola osoby, która prowadzi spotkanie w ramach swojej oferty.
- **Nazwa w kodzie (EN):** Provider
- **Przykład:** Anna jest prowadzącą dla rezerwacji Oli na jogę.
- **To nie jest:** typ konta; profesja.

### Uczestnik

- **Definicja:** Rola osoby, która ma rezerwację na spotkanie u prowadzącego.
- **Nazwa w kodzie (EN):** Participant
- **Przykład:** Ola jest uczestniczką rezerwacji u Anny.
- **To nie jest:** osoba, która tylko przegląda katalog.

### Anonimowy odwiedzający

- **Definicja:** Osoba korzystająca z Nestumi bez zalogowania. Jest nim także osoba, która ma konto, ale się nie zalogowała.
- **Nazwa w kodzie (EN):** AnonymousVisitor
- **Przykład:** Ola bez logowania wyszukuje oferty jogi online i ogląda wolne terminy u Anny. Gdy chce zarezerwować, musi się zalogować.
- **To nie jest:** uczestnik ani prowadzący. Nie zostawia w Nestumi żadnych danych.

### Profil zawodowy

- **Definicja:** Prezentacja jednej lub kilku pokrewnych profesji osoby o tym samym charakterze usługi (opis, kwalifikacje). Ma własne oferty i jeden grafik. Osoba ma jeden lub kilka profili.
- **Nazwa w kodzie (EN):** ProfessionalProfile
- **Przykład:** Ewa ma profil „Psychologia i psychoterapia” (psycholog + psychoterapeuta). Maciek ma profile „Psychologia” i „Joga”.
- **To nie jest:** osobna osoba; osobna karta w katalogu — katalog pokazuje prowadzącego (R-013).

### Profesja

- **Definicja:** Zawód lub specjalność z zamkniętej listy, którą osoba deklaruje i w ramach której może prowadzić oferty; każda profesja należy do jednego charakteru usługi.
- **Nazwa w kodzie (EN):** Profession
- **Przykład:** psycholog, psychiatra, psychoterapeuta, instruktor jogi, masażysta.
- **To nie jest:** rola (prowadzący, uczestnik); kwalifikacja (dokument potwierdzający przygotowanie).

## Cechy oferty

### Charakter usługi

- **Definicja:** Nadrzędny podział ofert: zdrowie psychiczne (pomoc psychologiczna i psychiatryczna) albo dobrostan.
- **Nazwa w kodzie (EN):** ServiceArea
- **Przykład:** Konsultacja psychiatryczna — zdrowie psychiczne; joga — dobrostan.
- **To nie jest:** rodzaj usługi; nie wynika z nazwy oferty ani z profesji prowadzącego.

### Rodzaj usługi

- **Definicja:** Konkretny typ usługi z zamkniętej listy; każdy rodzaj należy do jednego charakteru usługi.
- **Nazwa w kodzie (EN):** ServiceType
- **Przykład:** konsultacja psychologiczna, psychoterapia, MBCT — zdrowie psychiczne; joga, medytacja, masaż — dobrostan.
- **To nie jest:** charakter usługi; profesja.

### Forma spotkania

- **Definicja:** Sposób odbycia spotkania: online albo stacjonarnie.
- **Nazwa w kodzie (EN):** MeetingMode
- **Przykład:** Konsultacja psychologiczna: stacjonarnie lub online; masaż: tylko stacjonarnie.
- **To nie jest:** miejsce spotkania.

### Miejsce spotkania

- **Definicja:** Adres, pod którym odbywa się spotkanie stacjonarne.
- **Nazwa w kodzie (EN):** Location
- **Przykład:** Studio jogi, ul. Puławska 10, Warszawa.
- **To nie jest:** link do spotkania online; obiekt wyjazdowy (przyszłość).

## Reguły i czynności

### Kolizja

- **Definicja:** Sytuacja, w której dwie rezerwacje tej samej osoby, w dowolnej roli, zajmują jej czas w części wspólnej (zob. Zajętość). Rezerwacja zaczynająca się dokładnie w chwili zakończenia zajętości innej nie koliduje (R-035).
- **Nazwa w kodzie (EN):** Overlap
- **Przykład:** Medytacja 10:00–12:00 koliduje z zajęciami oddechowymi 11:30–12:00. Spotkanie 12:00–12:30 nie koliduje z medytacją 10:00–12:00. Masaż Anny u Marka 10:00–11:00 koliduje z konsultacją, którą Anna prowadzi 10:30–11:30.
- **To nie jest:** dwa spotkania o tej samej godzinie z różnymi prowadzącymi i różnymi uczestnikami.

### Zajętość

- **Definicja:** Czas osoby zajęty przez jej aktywne (nieanulowane) rezerwacje w obu rolach (R-036): jako prowadzącego — łącznie dla wszystkich jej ofert i profili, czas spotkania i przerwa po nim (czas zajętości, R-015); jako uczestnika — sam czas spotkania.
- **Nazwa w kodzie (EN):** BusyTime
- **Przykład:** Anna ma konsultację 10:00–11:00 — nikt nie może zarezerwować u niej jogi 10:30–11:30. Anna jest na masażu u Marka 13:00–14:00 — nikt nie zarezerwuje u niej konsultacji na 13:30, a ona nie zapisze się na inne spotkanie o 13:30.
- **To nie jest:** grafik; to, co osoba zadeklarowała jako dostępne.

### Złożenie rezerwacji

- **Definicja:** Czynność uczestnika: po obejrzeniu podsumowania (oferta, wolny termin, warunki) zgłasza, że chce zarezerwować. Dopiero wtedy Nestumi sprawdza, czy termin nadal jest wolny.
- **Nazwa w kodzie (EN):** Submit
- **Przykład:** Ola widzi podsumowanie „Joga indywidualna, wtorek 10:00–11:00, 150 zł” i klika „Rezerwuję”.
- **To nie jest:** potwierdzenie (to robi Nestumi); wybór terminu — przed złożeniem termin nie jest blokowany (R-003).

### Potwierdzenie

- **Definicja:** Automatyczne przyjęcie rezerwacji przez Nestumi, jeśli w chwili złożenia rezerwacji cały czas spotkania nadal jest wolnym terminem.
- **Nazwa w kodzie (EN):** Confirm
- **Przykład:** Ola składa rezerwację na 10:00–11:00, termin jest wolny — rezerwacja zostaje potwierdzona od razu.
- **To nie jest:** złożenie rezerwacji przez uczestnika; ręczna akceptacja prowadzącego (poza v1); potwierdzenie płatności.

### Anulowanie

- **Definicja:** Zakończenie rezerwacji przez uczestnika albo prowadzącego, zanim doszło do spotkania. Zwalnia czas prowadzącego; rezerwacja zostaje w historii.
- **Nazwa w kodzie (EN):** Cancel
- **Przykład:** Ola anuluje rezerwację na wtorek 10:00 — Anna znów ma ten czas wolny.
- **To nie jest:** usunięcie przedziału dostępności; usunięcie rezerwacji z historii.

### Kopiowanie grafiku

- **Definicja:** Jednorazowe utworzenie przedziałów dostępności na wybrane tygodnie na wzór wskazanego tygodnia.
- **Nazwa w kodzie (EN):** CopySchedule
- **Przykład:** Anna kopiuje grafik z tygodnia 2–8 listopada na pięć kolejnych tygodni.
- **To nie jest:** stała reguła cykliczna; nie tworzy rezerwacji.

<!--
Szablon nowego wpisu:

### <Pojęcie>

- **Definicja:** 
- **Nazwa w kodzie (EN):** 
- **Przykład:** 
- **To nie jest:** 
-->

## Słowa niejednoznaczne — nie używam ich bez doprecyzowania

| Słowo | Możliwe znaczenia | Czego używam zamiast |
| --- | --- | --- |
| termin | wolny termin; zarezerwowane spotkanie; po prostu data | Wolny termin, Rezerwacja, data |
| spotkanie | rezerwacja; samo wydarzenie; w przyszłości zajęcia grupowe z wieloma rezerwacjami | Rezerwacja (v1); „spotkanie” w zwykłym znaczeniu, np. „czas spotkania” |
| dostępność | to, co osoba zadeklarowała w grafiku; to, co zostało wolne po odjęciu rezerwacji | Przedział dostępności, Wolny termin |
| czas spotkania / czas zajętości | czas trwania widoczny dla uczestnika; czas trwania + przerwa po spotkaniu | Czas trwania; „czas zajętości” tylko w znaczeniu z przerwą |
| rola | prowadzący / uczestnik; profesja, w ramach której prowadzi ofertę („występuje jako psycholog”) | Prowadzący, Uczestnik, Profesja |
| kategoria / obszar | charakter usługi; rodzaj usługi | Charakter usługi, Rodzaj usługi |
| zapis | rezerwacja spotkania indywidualnego; przyszły zapis na zajęcia grupowe | Rezerwacja (v1) |
| sesja | spotkanie (np. sesja terapeutyczna); sesja logowania | Rezerwacja; „sesja” tylko w znaczeniu logowania |
| użytkownik | osoba; konto; odwiedzający bez zalogowania | Osoba, Anonimowy odwiedzający |
| gość | anonimowy odwiedzający; w przyszłych wyjazdach osoba nocująca w obiekcie | Anonimowy odwiedzający |
| potwierdzenie | czynność uczestnika po obejrzeniu podsumowania; automatyczne przyjęcie rezerwacji przez Nestumi | Złożenie rezerwacji, Potwierdzenie |
| specjalista / terapeuta / instruktor | prowadzący; profesja | Prowadzący, Profesja |
| uprawnienia | kwalifikacje zawodowe; dostęp w aplikacji | kwalifikacje (część profilu zawodowego); „uprawnienia” tylko w znaczeniu dostępu |
| slot | wolny termin; przedział dostępności; krok rozpoczęć | Wolny termin, Przedział dostępności, Krok rozpoczęć |
| wizyta | rezerwacja; skojarzenie medyczne, nieprawdziwe dla dobrostanu | Rezerwacja |
| klient / pacjent | uczestnik; „pacjent” sugeruje kontekst medyczny | Uczestnik |
| appointment / reservation (EN) | rezerwacja albo spotkanie | Booking |
| host (EN) | prowadzący; przyszły gospodarz obiektu | Provider |
| konflikt | kolizja; spór między stronami | Kolizja |
| akceptacja / zatwierdzenie | automatyczne potwierdzenie; ręczna akceptacja prowadzącego (poza v1); złożenie rezerwacji | Potwierdzenie, Złożenie rezerwacji |
| odwołanie / usunięcie | anulowanie (rezerwacja zostaje w historii); trwałe usunięcie | Anulowanie |
| powtarzanie / cykl | jednorazowe kopiowanie grafiku; stała reguła cykliczna (poza v1) | Kopiowanie grafiku |
| gabinet | miejsce spotkania; tylko jeden z rodzajów miejsca | Miejsce spotkania |
