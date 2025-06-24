Podział konserwacji baz danych
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Autor: Bartłomiej Czyż

Konserwacja fizyczna
^^^^^^^^^^^^^^^^^^^^

Konserwacja fizyczna obejmuje wszystkie działania związane z infrastrukturą sprzętową i zasobami systemowymi, na których działa baza danych. Do najważniejszych elementów tej konserwacji należą:

- Monitorowanie stanu dysków twardych – pozostała przestrzeń na dyskach, zużycie dysków oraz fragmentacja danych,

- Zabezpieczenie fizyczne serwerów – kontrola dostępu, ochrona przeciwpożarowa, klimatyzacja,

- Zasilanie awaryjne (UPS) - zabezpieczenie bazy przed skutkami nagłego zaniku zasilania,

- Monitoring stanu sieci – wydajność i stabilność połączenia między bazą a klientami,

- Tworzenie kopii zapasowych na nośnikach fizycznych – np. dyskach zewnętrznych czy taśmach LTO.

Konserwacja programowa
^^^^^^^^^^^^^^^^^^^^^^

Konserwacja programowa odnosi się do czynności wykonywanych na poziomie oprogramowania i logiki działania systemu bazy danych. Obejmuje:

- Zarządzanie użytkownikami i ich uprawnieniami,

- Optymalizację zapytań SQL,

- Aktualizację oprogramowania bazodanowego (np. MySQL, PostgreSQL),

- Defragmentację indeksów,

- Weryfikację integralności danych i naprawę uszkodzonych rekordów,

- Automatyczne zadania konserwacyjne (cron, schedulery),

- Reduplikację i redundancję - konfiguracja serwerów zapasowych.
