# Zajęcia 1 - Praca zdalna
## SSH
> ***Secure Shell*** - standard protokołów komunikacyjnych używanych w sieciach komputerowych TCP/IP, w architekturze klient-serwer.

Następca protokołu Telnet służącego do terminalowego łączenia się ze zdalnym komputerem. W SSH transfer wszelkich danych jest zaszyfrowany.

Standardowy port dla SSH: ***TCP 22***.

Domyślnym algorytmem szyfrowania komunikacji jest **algorytm RSA**, istnieje możliwość szyfrowania za pomocą słabszego **algorytmu DSA**. 

>RSA - jeden z pierwszych i obecnie najpopularniejszy asymetryczny algorytm kryptograficzny z kluczem publicznym. 

RSA umożliwia utworzene dwóch powiązanych kluczy: ***prywatnego*** oraz ***publicznego***, a następnie wykorzystuje je w celu ochrony treści przekazywanych wiadomości. Klucz publiczny jest **powrzechnie znany** i każdy może za jego pomocą zaszyfrować dowolną widaomość. Natomiast jedynie posiadacz klucza prywatnego może odszyfrować otrzymane wiadomości. Analogicznie, posiadacz klucza prywatnego może używać go do szyfrowania danych, pozwalając w ten sam sposób każdemu posiadaczowi odpowiadającego mu klucza publicznego odszyfrować je.

Podsumowując: informacje zaszyfrowaną kluczem prywatnym można rozszyfrować tylko za pomocą klucza publicznego i na odwrót.

## Zadania
### 1. Autentykacja za pomocą kluczy asymetrycznych
- [ ] Wygenerowanie pary kluczy RSA `ssh-keygen`
- [ ] Znalezienie i przeglądnięcie wygenerowanych kluczy
- [ ] Skopiowanie wygenerowanego klucza publicznego na konto hejnold@student.agh.edu.pl `ssh-copy-id`
- [ ] Zalogowanie się na konto studenta i wykonanie polecenia `ssh hejnold@student.agh.edu.pl `
- [ ] Znalezienie na serwerze student lokalizacji klucza publicznego
- [ ] Zalogowanie się zdalnie za studenta za pomocą kluczy RSA 

### 2. Praca z plikami i katalogami
- [x] Założenie katalogu o nazwie tmp  
> `mkdir [nazwa_katalogu] ` - tworzy katalog o podanej nazwie

- [x] Utworzenie pliku tekstowego
> Plik tekstowy można utworzyć na kilka sposobów
>  1. `nano` - prosty edytor tekstu
>  2. `cat > [nazwa pliku]`, po wpisaniu komendy możemy wpisać tekst który chcemy aby znalazł się w pliku. Aby zakończyć wprowadzanie tekstu do pliku przenosimy się Enterem do nowej lini i wciskamy Ctr + D.
> 3. `echo [tekst] > [nazwa_pliku].txt` - przekierowanie wyjścia za pomocą komendy echo
> 4. `vi [nazwa_pliku] - rozbudowany edytor tekstu

- [x] Zmienienie dla pliku tekstowego praw dostępu tak aby tylko właściciel pliku miał prawo do wyświetlania i edytowania go `chmod 600`
> `chmod [opcje] [nazwa_pliku]` - komenda w systemach uniksowych do zmiany praw dostępu do pliku lub katalogu
> 
> W postaci symbolicznej dla tej komendy musimy określić:
>  - grupy dla których chcemy przyznać/odjąć uprawnienia
>    - u - właściciel pliku
>    - g - grupa
>    - o - inni
>    - a - wszyscy
>  - czy chcemy dodać dodać czy odjąć uprawnienia
>     - **-** jeśli chcemy odjąć uprawnienia
>     - **+** jeśli chcemy dodać uprawnienia
>     - **=** jeśli chcemy przypisać takie jakie podamy
>  - jakie uprawnienia chcemy dodać/odjąć
>    | Cyfra | Prawa | Litera | Binarnie |
>    | --- | --- | --- | --- |
>    | 0 | Brak praw | - - - | 000 |
>    | 1 | Wykonywanie | - - x | 001 |
>    | 2 | Zapis | - w - | 010 |
>    | 3 | Zapis i wykonanie | - w x | 011 |
>    | 4 | Odczyt | r - - | 100 |
>    | 5 | Odczyt i wykonanie | r - x | 101 |
>    | 6 | Odczyt i zapis | r w - | 110 |
>    | 7 | Odczyt, zapis i wykonanie | r w x | 111 |
>
> Aby sprawdzić jakie uprawnienia mają pliki w danej lokalizacji używamy komendy `ls -l`


### 3. Procesy
- [x] Wyświetlenie procesów `ps`. `top`, `pstree`
> Proces - wykonujący się program
> `ps` - wyświetla procesy w terminalu z ich numerami PID (identyfikator procesu), TTY (nazwa terminala), TIME (czas wykorzystywany przez proces) i  CMD (nazwa programu).
> `pstree` - procesy w postaci drzewa procesów
> `top` - wyświetla wszystkie procesy, oraz ich stan, daje najwięcej informacji
- [x] Przetestowanie jakie procesy mogą być wyświetlane w zależności od wybranych opcji

### 4. Liczenie lini w pliku
  - [x] Zliczenie programowo ile jest osób na serwerze
> Na początku użyjemy komemdy `wc > serwer.txt` która pokazuje ile jest zalogowanych osób na serwerze i przekierujemy jej wyjście z terminala do pliku. Następnie komenda `wc -l serwer.txt` policzy ile linijek jest w pliku. Ilość linijek jest równoznaczna z tym ile osób jest zalogowanych w danej chwilii na serwerze.

### 5. Hasło
- [x] Zmiana hasła dostępu konta `passwd [nazwa_konta]`

### 6. Szukanie plików
- [x] Sprawdzenie różnych opcji wyszukiwania plików w systemie
- [x] Wyszukanie pliku passwd `find / -name '*passwd*' print`
> `find` pozwala nam wyszukać pliki lub katalogi, 
>
> `/` w katalogu głównym,
>
> `name '*passwd*'` po nazwie w tym wypadku fraza *passwd* może znajdować się w dowolnym miejscu nazwy,
>
> `print`  i wyniki mają zostać wyprintowane w terminalu. 

### 7. Katalogi charakterystyczne dla systemu linux
- [ ] Sprawdzenie charakterystycznych katalogów w systemie linux
- [ ] Sprawdzenie aktualnej lokalizacji
 
 ### 8. Przekierowania wejścia i wyjścia
 - [ ] Korzystając z przekierowań utworzyć plik 
 
 ### 9. Usuwanie katalogów
 - [ ] Testowanie usuwania katalogów z użyciem komendy `rm`
 
 ### 10. Publikowanie i edytcja strony HTML
 


    

