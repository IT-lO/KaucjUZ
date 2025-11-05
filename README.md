# KaucjUZ

## Scenariusze przypadków użycia - Automat do butelek

## UC1: Wprowadzenie butelki

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Wprowadzenie butelki do automatu |
| **Aktor** | Użytkownik |
| **Opis** | Użytkownik wkłada butelkę do automatu w celu jej recyklingu i otrzymania zwrotu pieniędzy lub darmowej utylizacji |
| **Warunki wstępne** | - Automat jest włączony i sprawny
- Automat ma miejsce w kontenerze
- Użytkownik posiada butelkę do zwrotu |
| **Główny scenariusz** | 1. Użytkownik umieszcza butelkę w otworze przyjmującym
2. System zczytuje kod kreskowy butelki
3. System określa materiał butelki (plastik/szkło/aluminium)
4. System określa pojemność butelki
5. System określa poziom zgniecenia butelki
6. System akceptuje butelkę
7. System sortuje butelkę po materiale
8. System zgniata butelkę (jeśli plastikowa)
9. System przemieszcza butelkę do odpowiedniego kontenera
10. System aktualizuje wysokość uznania na wyświetlaczu
11. System aktualizuje liczbę przyjętych butelek
12. System wyświetla timer przed ponownym wrzuceniem |
| **Alternatywne scenariusze** | **A1: Butelka bez kodu kreskowego**
- 2a. System nie może odczytać kodu kreskowego
- 2b. System odrzuca butelkę
- 2c. System wyświetla komunikat o błędzie

**A2: Butelka zbyt zgnieciona**
- 5a. System stwierdza zbyt duży poziom zgniecenia
- 5b. System oferuje darmową utylizację
- 5c. Użytkownik potwierdza lub odrzuca
- 5d. System przyjmuje bez zwrotu lub odrzuca butelkę

**A3: Butelka niekwalifikująca się**
- 5a. System stwierdza, że butelka nie spełnia kryteriów
- 5b. System odrzuca butelkę
- 5c. System wyświetla przyczynę odrzucenia

**A4: Kontener pełny**
- 9a. System wykrywa brak miejsca w kontenerze
- 9b. System przerywa przyjmowanie butelek
- 9c. System wyświetla komunikat "Automat pełny"
- 9d. System wysyła powiadomienie do serwisanta |
| **Warunki końcowe** | - Butelka została przyjęta i umieszczona w odpowiednim kontenerze LUB została odrzucona
- Wysokość uznania została zaktualizowana (jeśli przyjęto)
- Liczba butelek została zaktualizowana (jeśli przyjęto)
- System gotowy do przyjęcia kolejnej butelki |

---

## UC6: Wypłata środków

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Wypłata środków za butelki |
| **Aktor** | Użytkownik |
| **Opis** | Użytkownik kończy wkładanie butelek i wybiera sposób wypłaty zgromadzonych środków |
| **Warunki wstępne** | - Użytkownik wrzucił przynajmniej jedną butelkę
- Wysokość uznania jest większa od zera
- Automat jest sprawny |
| **Główny scenariusz** | 1. Użytkownik wybiera "Zakończ transakcję" na wyświetlaczu
2. System wyświetla wysokość zgromadzonych środków
3. System wyświetla dostępne metody wypłaty
4. Użytkownik wybiera metodę wypłaty (np. karta sklepu)
5. System przetwarza wypłatę
6. System potwierdza wypłatę
7. System wyświetla podsumowanie transakcji
8. System wysyła powiadomienie o transakcji do systemu sklepu
9. System resetuje licznik i wraca do stanu początkowego |
| **Alternatywne scenariusze** | **A1: Wypłata na kartę sklepu**
- 4a. Użytkownik wybiera "Karta sklepu"
- 4b. Użytkownik skanuje kartę sklepu
- 4c. System dodaje środki do karty

**A2: Wypłata w monetach**
- 4a. Użytkownik wybiera "Monety"
- 4b. System wydaje monety
- 4c. System wyświetla "Odbierz monety"

**A3: Wypłata przez aplikację**
- 4a. Użytkownik wybiera "Aplikacja sklepu"
- 4b. Użytkownik skanuje kod QR aplikacją
- 4c. System przesyła środki do aplikacji

**A4: Wypłata bonem ze zniżką**
- 4a. Użytkownik wybiera "Bon ze zniżką"
- 4b. System drukuje bon z kodem kreskowym
- 4c. System wyświetla "Odbierz bon"

**A5: Wypłata na kartę płatniczą**
- 4a. Użytkownik wybiera "Karta"
- 4b. Użytkownik zbliża kartę do terminala
- 4c. System przetwarza zwrot na kartę

**A6: Brak pieniędzy w automacie**
- 5a. System wykrywa brak monet
- 5b. System ukrywa opcję "Monety"
- 5c. System oferuje alternatywne metody

**A7: Brak papieru do bonów**
- 5a. System wykrywa brak papieru
- 5b. System ukrywa opcję "Bon ze zniżką"
- 5c. System oferuje alternatywne metody

**A8: Anulowanie transakcji**
- 4a. Użytkownik wybiera "Anuluj"
- 4b. System anuluje transakcję
- 4c. System wraca do przyjmowania butelek |
| **Warunki końcowe** | - Środki zostały wypłacone wybraną metodą
- Powiadomienie o transakcji zostało wysłane
- System został zresetowany do stanu początkowego
- Wyświetlacz pokazuje ekran powitalny |

---

## UC10: Maintenance automatu

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Konserwacja i serwis automatu |
| **Aktor** | Serwisant |
| **Opis** | Serwisant wykonuje czynności konserwacyjne automatu w celu utrzymania jego sprawności |
| **Warunki wstępne** | - Serwisant ma dostęp do automatu
- Serwisant posiada uprawnienia i klucze
- System wysłał powiadomienie o konieczności serwisu LUB jest zaplanowana konserwacja |
| **Główny scenariusz** | 1. Serwisant loguje się do trybu serwisowego
2. System wyświetla status automatu
3. Serwisant sprawdza poziom napełnienia kontenerów
4. Serwisant opróżnia kontenery z butelkami
5. Serwisant sprawdza stan rolki papieru
6. Serwisant wymienia rolkę papieru (jeśli potrzeba)
7. Serwisant sprawdza stan pieniędzy
8. Serwisant uzupełnia monety (jeśli potrzeba)
9. Serwisant sprawdza stan techniczny elementów
10. Serwisant zatwierdza zakończenie konserwacji
11. System wysyła powiadomienie o zakończeniu serwisu
12. System wraca do trybu normalnego |
| **Alternatywne scenariusze** | **A1: Poważna awaria**
- 9a. Serwisant wykrywa poważną usterkę
- 9b. Serwisant przełącza automat w tryb "Out of commission"
- 9c. System wyświetla "Automat nieczynny"
- 9d. System blokuje przyjmowanie butelek
- 9e. System wysyła powiadomienie o awarii

**A2: Kontenery prawie pełne**
- 3a. System wykrywa napełnienie powyżej 80%
- 3b. System wysyła powiadomienie o zbliżającym się przepełnieniu

**A3: Papier kończy się**
- 5a. System wykrywa, że papier kończy się
- 5b. System wysyła powiadomienie o konieczności wymiany

**A4: Pieniądze kończą się**
- 7a. System wykrywa, że monet jest mniej niż 20%
- 7b. System wysyła powiadomienie o konieczności uzupełnienia

**A5: Konserwacja prewencyjna**
- 1a. Serwisant rozpoczyna zaplanowaną konserwację
- 1b. System nie wysyłał wcześniej powiadomień
- 1c. Serwisant wykonuje standardowe czynności kontrolne |
| **Warunki końcowe** | - Kontenery zostały opróżnione
- Papier został uzupełniony (jeśli potrzeba)
- Monety zostały uzupełnione (jeśli potrzeba)
- System jest w trybie normalnym LUB w trybie "Out of commission"
- Powiadomienie o stanie po serwisie zostało wysłane |

---

## UC11: Wysyłanie powiadomień

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Wysyłanie powiadomień do systemu sklepu |
| **Aktor** | System sklepu/Aplikacja |
| **Opis** | Automat automatycznie wysyła powiadomienia o stanie technicznym i transakcjach do centralnego systemu |
| **Warunki wstępne** | - Automat ma połączenie z systemem sklepu
- Wystąpiło zdarzenie wymagające powiadomienia |
| **Główny scenariusz** | 1. System wykrywa zdarzenie wymagające powiadomienia
2. System przygotowuje dane powiadomienia
3. System wysyła powiadomienie POST do systemu sklepu
4. System otrzymuje potwierdzenie odbioru
5. System loguje wysłane powiadomienie |
| **Alternatywne scenariusze** | **A1: Powiadomienie o stanie technicznym - papier**
- 1a. System wykrywa, że papier kończy się (<20%)
- 1b. System wysyła powiadomienie "LOW_PAPER"

**A2: Powiadomienie o stanie technicznym - kontener**
- 1a. System wykrywa, że miejsce w kontenerze się kończy (>80%)
- 1b. System wysyła powiadomienie "CONTAINER_FULL"

**A3: Powiadomienie o stanie technicznym - pieniądze**
- 1a. System wykrywa, że pieniądze się kończą (<20%)
- 1b. System wysyła powiadomienie "LOW_COINS"

**A4: Powiadomienie o transakcji**
- 1a. Użytkownik zakończył transakcję
- 1b. System wysyła powiadomienie "TRANSACTION_COMPLETE" z danymi transakcji

**A5: Brak połączenia**
- 3a. System nie może połączyć się z serwerem
- 3b. System zapisuje powiadomienie w kolejce
- 3c. System próbuje wysłać ponownie co 5 minut

**A6: Krytyczna awaria**
- 1a. System wykrywa krytyczną awarię
- 1b. System wysyła powiadomienie "CRITICAL_ERROR" z najwyższym priorytetem |
| **Warunki końcowe** | - Powiadomienie zostało wysłane i potwierdzone LUB zapisane w kolejce
- Zdarzenie zostało zalogowane w systemie
- System sklepu otrzymał informację o stanie automatu |

---

## UC12: Obsługa wyświetlacza/interfejsu

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Interakcja użytkownika z wyświetlaczem automatu |
| **Aktor** | Użytkownik |
| **Opis** | Użytkownik nawiguje po interfejsie automatu, wybiera opcje i otrzymuje informacje zwrotne |
| **Warunki wstępne** | - Automat jest włączony
- Wyświetlacz działa poprawnie |
| **Główny scenariusz** | 1. System wyświetla ekran powitalny
2. Użytkownik wybiera język z dostępnych opcji
3. System zmienia język interfejsu
4. System wyświetla instrukcję wkładania butelek
5. System wyświetla aktualną wysokość uznania (0,00 zł)
6. System wyświetla liczbę przyjętych butelek (0 szt.)
7. Użytkownik wkłada butelki (UC1)
8. System aktualizuje wysokość uznania po każdej butelce
9. System aktualizuje liczbę butelek
10. System wyświetla timer przed ponownym wrzuceniem (3 sek.)
11. Po upływie timera system sygnalizuje gotowość
12. Użytkownik wybiera "Zakończ transakcję"
13. System wyświetla ekran wyboru metody wypłaty
14. Użytkownik wybiera metodę wypłaty
15. System przetwarza wypłatę (UC6)
16. System wyświetla podsumowanie transakcji
17. System wyświetla podziękowanie
18. System wraca do ekranu powitalnego |
| **Alternatywne scenariusze** | **A1: Zmiana języka w trakcie**
- 7a. Użytkownik wybiera zmianę języka w menu
- 7b. System wyświetla dostępne języki
- 7c. System zmienia język bez przerywania transakcji

**A2: Timeout bezczynności**
- 7a. Użytkownik nie wkłada butelki przez 60 sekund
- 7b. System wyświetla komunikat "Czy chcesz kontynuować?"
- 7c. Jeśli brak reakcji przez 30 sek., system przechodzi do wypłaty

**A3: Anulowanie przed wypłatą**
- 12a. Użytkownik wybiera "Anuluj" lub "Wrzuć więcej butelek"
- 12b. System wraca do ekranu przyjmowania butelek

**A4: Błąd przyjęcia butelki**
- 7a. System odrzuca butelkę
- 7b. System wyświetla komunikat o przyczynie odrzucenia
- 7c. System pokazuje instrukcję poprawnego wkładania
- 7d. System wraca do przyjmowania po 5 sekundach

**A5: Automat pełny**
- 1a. System wykrywa pełny kontener
- 1b. System wyświetla "Automat tymczasowo nieczynny"
- 1c. System blokuje możliwość rozpoczęcia transakcji

**A6: Tryb serwisowy**
- 1a. Serwisant aktywuje tryb serwisowy
- 1b. System wyświetla interfejs serwisowy
- 1c. System blokuje dostęp dla zwykłych użytkowników |
| **Warunki końcowe** | - Użytkownik zakończył interakcję z automatem
- System wrócił do ekranu powitalnego
- Wszystkie dane transakcji zostały przetworzone
- Interfejs jest gotowy dla kolejnego użytkownika |

---

## UC9: Przechowywanie butelek

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Przetwarzanie i przechowywanie przyjętych butelek |
| **Aktor** | System (proces automatyczny) |
| **Opis** | Automat automatycznie sortuje, przetwarza i przechowuje przyjęte butelki w odpowiednich kontenerach |
| **Warunki wstępne** | - Butelka została przyjęta i zweryfikowana
- Materiał butelki został określony
- W kontenerach jest miejsce |
| **Główny scenariusz** | 1. System identyfikuje materiał butelki (plastik/szkło/aluminium)
2. System kieruje butelkę na odpowiedni tor sortujący
3. Jeśli butelka plastikowa: system aktywuje mechanizm zgniatający
4. System zgniata butelkę do 1/3 objętości
5. System przemieszcza butelkę do odpowiedniego kontenera
6. System inkrementuje licznik butelek w kontenerze
7. System sprawdza poziom napełnienia kontenera
8. Jeśli kontener >80%: system wysyła powiadomienie
9. System potwierdza umieszczenie butelki |
| **Alternatywne scenariusze** | **A1: Butelka szklana**
- 3a. System wykrywa materiał: szkło
- 3b. System pomija zgniatanie
- 3c. System ostrożnie przemieszcza do kontenera szkła

**A2: Butelka aluminiowa**
- 3a. System wykrywa materiał: aluminium
- 3b. System pomija zgniatanie (lub lekko zgniata)
- 3c. System przemieszcza do kontenera aluminium

**A3: Kontener prawie pełny**
- 7a. System wykrywa napełnienie >80%
- 7b. System wysyła powiadomienie "CONTAINER_ALMOST_FULL"
- 7c. System kontynuuje przyjmowanie do 95%

**A4: Kontener pełny**
- 7a. System wykrywa napełnienie >95%
- 7b. System wysyła powiadomienie "CONTAINER_FULL"
- 7c. System blokuje przyjmowanie kolejnych butelek tego typu
- 7d. System wyświetla komunikat użytkownikowi

**A5: Błąd mechanizmu zgniatającego**
- 4a. System wykrywa usterkę mechanizmu
- 4b. System pomija zgniatanie
- 4c. System umieszcza butelkę niezgniecioną
- 4d. System wysyła powiadomienie o usterce

**A6: Zablokowanie toru**
- 5a. System wykrywa blokadę na torze transportowym
- 5b. System próbuje usunąć blokadę (odwrócenie silnika)
- 5c. Jeśli niepowodzenie: system przechodzi w tryb awaryjny
- 5d. System wysyła powiadomienie "TRANSPORT_BLOCKED" |
| **Warunki końcowe** | - Butelka została umieszczona w odpowiednim kontenerze
- Liczniki kontenerów zostały zaktualizowane
- System monitoruje poziom napełnienia
- Powiadomienia zostały wysłane (jeśli potrzeba) |
