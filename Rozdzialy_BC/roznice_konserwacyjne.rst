Różnice konserwacyjne w zależności od rodzaju bazy danych
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Autor: Bartłomiej Czyż

PostgreSQL
^^^^^^^^^^

PostgreSQL to zaawansowany system RDBMS, znany z silnego wsparcia dla różnych typów danych i transakcyjności.

1. Fizyczna konserwacja:
	
	- Złożona struktura katalogów danych (base, pg_wal, pg_tblspc) – wymaga regularnego monitoringu,

	- Możliwość wykorzystania narzędzia pg_basebackup do tworzenia pełnych kopii fizycznych.

2. Programowa konserwacja:
	
	- Automatyczne zadania VACUUM, ANALYZE – zapewniają odzyskiwanie przestrzeni po usunięciu rekordów,

	- Możliwość używania pg_repack do defragmentacji bez przestojów,

	- Silne wsparcie dla replikacji strumieniowej i klastrów wysokiej dostępności (HA).

MySQL
^^^^^

MySQL jest obecnie jedną z najpopularniejszych relacyjnych baz danych, szeroko stosowana w aplikacjach webowych.

1. Fizyczna konserwacja:

	- Wymaga monitorowania plików .ibd (w przypadku silknika InnoDB), które mogą znacznie rosnąć,

	- Backup danych realizowany poprzez mysqldump lub system replikacji binlogów.

2. Programowa konserwacja:

	- Regularne sprawdzanie indeksów (ANALYZE TABLE, OPTIMIZE TABLE),

	- Używanie narzędzi typu mysqlcheck do weryfikacji i naprawy tabel,

	- Konfiguracja pliku my.cnf w celu dostosowania do wymagań aplikacji.

SQLite (np. LightSQL)
^^^^^^^^^^^^^^^^^^^^^

SQLite, używana w aplikacjach mobilnych i desktopowych, różni się znacznie od serwerowych baz danych.

1. Fizyczna konserwacja:

	- Brak klasycznego serwera – baza to pojedynczy plik .db,

	- Konieczność regularnego kopiowania pliku bazy danych jako backup.

2. Programowa konserwacja:
	
	- Użycie polecenia VACUUM do defragmentacji i zmniejszenia rozmiaru pliku,

	- Ograniczone możliwości równoczesnego dostępu – wymaga uwagi w aplikacjach wielowątkowych,

	- Nie wymaga osobnych usług do zarządzania – działa bezpośrednio w aplikacji.

Microsoft SQL Server
^^^^^^^^^^^^^^^^^^^^

System korporacyjny, szeroko wykorzystywany w dużych organizacjach.

1. Fizyczna konserwacja:

	- Obsługuje macierze RAID i pamięci masowe SAN,

	- Regularne kopie pełne, różnicowe i dzienniki transakcyjne.

2. Programowa konserwacja:

	- Zaawansowany SQL Server Agent – możliwość harmonogramowania zadań,

	- Narzędzia do monitorowania stanu instancji (SQL Profiler, Database Tuning Advisor),

	- Wsparcie dla Always On Availability Groups dla wysokiej dostępności.
