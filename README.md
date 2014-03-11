Projekt w Github.com: https://github.com/gpsv1/gps.git

1. Instalacja Git:
	a) Windows:
		- Pobieramy najnowszą wersję z http://git-scm.com/download/win
		- Instalujemy jak każdy inny program zaznaczając po drodze opcje Use Git Bash only, Use OpenSSH, Checkout Windows-style, commit Unix-style line endings,
		- Dodajemy do zmiennej środowiskowej 'Path' katalog 'bin' progrmu Git:
			- Z menu „Start” wybrać pozycję „Komputer”.
			- Z menu podręcznego wybrać pozycję „Właściwości systemu”.
			- Wybrać „Zaawansowane ustawienia systemu” > karta „Zaawansowane”.
			- Wybrać pozycję „Zmienne środowiskowe”. W obszarze „Zmienne systemowe” odszukać zmienną PATH i kliknąć na niej.
			- W oknie „Edytowanie” zmienić wartość zmiennej PATH, dodając do wartości zmiennej PATH lokalizację katalogu 'bin' używając jako separatora ;(średnik). Poprawna ścieżka do katalogu to np.: "C:\Program Files (x86)\Git\bin"
		- Uruchamiamy ponownie cmd i sprawdzamy czy wszystko działa wykonując 'git --version'.
	b) Linux:
		- Wykonujemy polecenie 'sudo apt-get install git' (lub instalujemy z poziomu innego programu zarządzania pakietami, np. Synaptic)

2. Instalacja Maven:
	a) Windows:
		- Pobieramy Maven z http://ftp.ps.pl/pub/apache/maven/maven-3/3.0.5/binaries/apache-maven-3.0.5-bin.zip
		- Rozpakowujemy archiwum bezpośrednio na dysku C: (można gdzieś indziej, ale zmienią się wtedy ścieżki do plików wykonywalnych)
		- Dodajemy zmienną środowiskową 'M2_PATH' z wartością 'C:\pache-maven-3.0.5-bin\'
		- Do zmiennej środowiskowej 'Path' dodajemy 'M2_PATH\bin'
		- Sprawdzamy, czy mamy zdefiniowaną zmienną 'JAVA_HOME'. Jeżeli nie, dodajemy ją z wartością określającą ścieżkę do katalogu domowego Javy (zakładam, że Java >= 1.6 jest zainstalowana i ścieżka z do katalogu 'bin' jest dodana do zmiennej 'Path')
		- Uruchamiamy ponownie cmd i sprawdzamy czy wszystko działa wykonując 'mvn -version'.
	b) Linux:
		- Wykonujemy polecenie 'sudo apt-get install maven2'

3. Konfiguracja Git:
	a) Uruchamiamy terminal i wykonujemy po koleii:
		- git config --global user.name "Imię Nazwisko"
		- git config --global user.email mail@mial.pl
		- git config --global core.autocrlf true (tylko na Windows)

4. Pobranie projektu:
	a) Przechodzimy do katalogu (z poziomu terminala) gdzie chcemy utrzymywać nasz projekt i wykonujemy 'git clone https://github.com/gpsv1/gps.git'
	b) Uruchamiamy Ideę i klikamy na 'Import project'.
	c) Przechodzimy do katalogu z naszym projektem i zaznaczamy plik pom.xml.
	d) W kolejnym oknie zaznaczamy dodatkowo opcję 'Import Maven projects automatically' i klikamy na 'Next'.
	e) Po drodze wskazujemy na zainstalowaną Javę (jeżeli nie wykryło to klikamy na zielony plus u góry ekranu i wskazujemy główny katalog Javy)
	f) Lecimy 'Next' i na koniec 'Finish'

5. Kompilacja i uruchomienie projektu:
    a) W głównym oknie Ideii klikamy na 'Run' -> 'Edit Configurations'
    b) Klikamy na zielony plus u góry ekranu i wymieramy 'Maven'
    c) Wpisujemy nazwę 'Run GPS', katalog pozostawiamy domyślny, a w pole 'Command line' wpisujemy 'mvn clean install'.
    d) Klikamy na Ok.

    Od teraz aby:
        - skompilować program: klikamy na zieloną strzałkę skierowną w dół z jakimiś tam bitami (Ctrl+F9),
        - skompilować, wyczyścić poprzednie pliki kompilacji, wybudować jar-a, uruchomić testy jednostkowe: zielona strzałka w prawo (Shift+F10) (upewnić się że byrany jest profil 'Run GPS'),
        - debugować: zielony robak (Shift+F9).
    Wszytko to w sekcji umieszczonej u góry po prawej.