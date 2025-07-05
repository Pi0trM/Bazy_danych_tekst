Schemat bazy danych - definicja i znaczenie
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Autor: Bartłomiej Czyż

Czym jest schemat bazy danych?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Schemat bazy danych to logiczna struktura opisująca organizację danych, typy danych, relacje między tabelami, ograniczenia integralności, procedury składowane, widoki i inne obiekty. Innymi słowy, schemat jest "szkieletem" bazy danych.

Przykładowe elementy schematu:

- Tabele (np. users, orders),

- Typy danych (np. INT, VARCHAR, DATE),

- Klucze główne i obce,

- Indeksy,

- Widoki (VIEW),

- Procedury i funkcje (STORED PROCEDURES),

- Ograniczenia (CHECK, NOT NULL, UNIQUE).

Rola schematu w konserwacji bazy danych
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Schemat ma kluczowe znaczenie dla utrzymania spójności i integralności danych, dlatego jego kontrola i konserwacja obejmuje m.in.:

- Dokumentację schematu - niezbędna przy aktualizacjach i migracjach,

- Weryfikację integralności relacji - sprawdzenie czy klucze obce i reguły są respektowane,

- Normalizację - kontrola nad nadmiarem danych i poprawnością logiczną,

- Aktualizacje schematu - np. dodawanie nowych kolumn, zmiana typu danych,

- Kontrola zgodności - wersjonowanie schematu (np. za pomocą narzędzi typu Liquibase, Flyway),

- Zabezpieczenia schematów - nadawanie uprawnień tylko zaufanym użytkownikom.

Przykład konserwacji:

W PostgreSQL można analizować i optymalizować strukturę przy pomocy pgAdmin oraz narzędzi takich jak pg_dump --schema-only.

Różnice w implementacji schematu w różnych systemach
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- MySQL - obsługuje wiele schematów w jednej bazie; ograniczone typy kolumn w starszych wersjach,

- PostgreSQL - bardzo elastyczny system schematów - możliwość teorzenia przestrzeni nazw,

- SQLite - pojedynczy schemat, uproszczony system typów,

- SQL Server - schemat jako logiczna przestrzeń obiektów, np. dbo, hr, finance.

Transakcje - definicja i rola w kontroli danych
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Autor: Bartłomiej Czyż

Czym jest transakcja?
^^^^^^^^^^^^^^^^^^^^^

Transakcja to zbiór operacji na bazie danych, które są traktowane jako jedna, nierozdzielna całość. Albo wykonują się wszystkie operacje, albo żadna - zasada atomiczności. Transakcje są podstawą do zachowania spójności danych, szczególnie w środowiskach wieloużytkownikowych.

Zasady ACID
^^^^^^^^^^^

Transakcje w bazach danych opierają się na czterech podstawowych zasadach, znanych jako ACID:

- A - Atomicity (Atomowość) - operacje wchodzące w skład transakcji są niepodzielne - wszystkie muszą się powieść, lub wszystkie są wycofywane,

- C - Consistency (Spójność) - transakcje przekształcają dane ze stanu spójnego w stan spójny,

- I - Isolation (Izolacja) - równoczesne transakcje nie wpływają na siebie nawzajem,

- D - Durability (Trwałość) - po zatwierdzeniu transakcji dane są trwale zapisane, nawet w przypadku awarii.

Rola transakcji w kontroli i konserwacji
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Transakcje mają ogromne znaczenie dla bezpieczeństwa danych, dlatego są nieodłącznym elementem procesów konserwacyjnych. Ich zastosowanie obejmuje:

- Zabezpieczenie operacji aktualizacji - np. przy masowych zmianach danych,

- Replikacja i synchronizacja danych - transakcje zapewniają spójność między główną bazą, a replikami,

- Zarządzanie błędami - w przypadku błędu można wykonać ROLLBACK i przywrócić stan bazy,

- Tworzenie backupów spójnych z punktu w czasie - snapshoty danych często wymagają wsparcia transakcyjnego,

- Ochrona przed uszkodzeniami logicznymi - np. przez niekompletne aktualizacje.

Różnice w implementacji transakcji w różnych systemach
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

- MySQL - w pełni wspierane w silniku InnoDB; START TRANSACTION, COMMIT, ROLLBACK,

- PostgreSQL - silne wsparcie ACID, zaawansowana izolacja (REPEATABLE READ, SERIALIZABLE),

- SQLite - transakcje działają w trybie plikowym; BEGIN, COMMIT i ROLLBACK są wspierane,

- SQL Server - zaawansowany mechanizm transakcji z kontrolą poziomów izolacji, także eksplicytny SAVEPOINT.
