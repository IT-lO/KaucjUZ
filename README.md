# Scenariusze przypadków użycia - Automat do butelek

## UC1: Wprowadzenie butelki

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Wprowadzenie butelki do automatu |
| **Aktor** | Użytkownik |
| **Opis** | Użytkownik wkłada butelkę do automatu w celu jej recyklingu i otrzymania zwrotu pieniędzy lub darmowej utylizacji |
| **Warunki wstępne** | - Automat jest włączony i sprawny<br>- Automat ma miejsce w kontenerze<br>- Użytkownik posiada butelkę do zwrotu |
| **Główny scenariusz** | 1. Użytkownik umieszcza butelkę w otworze przyjmującym<br>2. System zczytuje kod kreskowy butelki<br>3. System określa materiał butelki (plastik/szkło/aluminium)<br>4. System określa pojemność butelki<br>5. System określa poziom zgniecenia butelki<br>6. System akceptuje butelkę<br>7. System sortuje butelkę po materiale<br>8. System zgniata butelkę (jeśli plastikowa)<br>9. System przemieszcza butelkę do odpowiedniego kontenera<br>10. System aktualizuje wysokość uznania na wyświetlaczu<br>11. System aktualizuje liczbę przyjętych butelek<br>12. System wyświetla timer przed ponownym wrzuceniem |
| **Alternatywne scenariusze** | **A1: Butelka bez kodu kreskowego**<br>- 2a. System nie może odczytać kodu kreskowego<br>- 2b. System odrzuca butelkę<br>- 2c. System wyświetla komunikat o błędzie<br><br>**A2: Butelka zbyt zgnieciona**<br>- 5a. System stwierdza zbyt duży poziom zgniecenia<br>- 5b. System oferuje darmową utylizację<br>- 5c. Użytkownik potwierdza lub odrzuca<br>- 5d. System przyjmuje bez zwrotu lub odrzuca butelkę<br><br>**A3: Butelka niekwalifikująca się**<br>- 5a. System stwierdza, że butelka nie spełnia kryteriów<br>- 5b. System odrzuca butelkę<br>- 5c. System wyświetla przyczynę odrzucenia<br><br>**A4: Kontener pełny**<br>- 9a. System wykrywa brak miejsca w kontenerze<br>- 9b. System przerywa przyjmowanie butelek<br>- 9c. System wyświetla komunikat "Automat pełny"<br>- 9d. System wysyła powiadomienie do serwisanta |
| **Warunki końcowe** | - Butelka została przyjęta i umieszczona w odpowiednim kontenerze LUB została odrzucona<br>- Wysokość uznania została zaktualizowana (jeśli przyjęto)<br>- Liczba butelek została zaktualizowana (jeśli przyjęto)<br>- System gotowy do przyjęcia kolejnej butelki |

---

## UC6: Wypłata środków

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Wypłata środków za butelki |
| **Aktor** | Użytkownik |
| **Opis** | Użytkownik kończy wkładanie butelek i wybiera sposób wypłaty zgromadzonych środków |
| **Warunki wstępne** | - Użytkownik wrzucił przynajmniej jedną butelkę<br>- Wysokość uznania jest większa od zera<br>- Automat jest sprawny |
| **Główny scenariusz** | 1. Użytkownik wybiera "Zakończ transakcję" na wyświetlaczu<br>2. System wyświetla wysokość zgromadzonych środków<br>3. System wyświetla dostępne metody wypłaty<br>4. Użytkownik wybiera metodę wypłaty (np. karta sklepu)<br>5. System przetwarza wypłatę<br>6. System potwierdza wypłatę<br>7. System wyświetla podsumowanie transakcji<br>8. System wysyła powiadomienie o transakcji do systemu sklepu<br>9. System resetuje licznik i wraca do stanu początkowego |
| **Alternatywne scenariusze** | **A1: Wypłata na kartę sklepu**<br>- 4a. Użytkownik wybiera "Karta sklepu"<br>- 4b. Użytkownik skanuje kartę sklepu<br>- 4c. System dodaje środki do karty<br><br>**A2: Wypłata w monetach**<br>- 4a. Użytkownik wybiera "Monety"<br>- 4b. System wydaje monety<br>- 4c. System wyświetla "Odbierz monety"<br><br>**A3: Wypłata przez aplikację**<br>- 4a. Użytkownik wybiera "Aplikacja sklepu"<br>- 4b. Użytkownik skanuje kod QR aplikacją<br>- 4c. System przesyła środki do aplikacji<br><br>**A4: Wypłata bonem ze zniżką**<br>- 4a. Użytkownik wybiera "Bon ze zniżką"<br>- 4b. System drukuje bon z kodem kreskowym<br>- 4c. System wyświetla "Odbierz bon"<br><br>**A5: Wypłata na kartę płatniczą**<br>- 4a. Użytkownik wybiera "Karta"<br>- 4b. Użytkownik zbliża kartę do terminala<br>- 4c. System przetwarza zwrot na kartę<br><br>**A6: Brak pieniędzy w automacie**<br>- 5a. System wykrywa brak monet<br>- 5b. System ukrywa opcję "Monety"<br>- 5c. System oferuje alternatywne metody<br><br>**A7: Brak papieru do bonów**<br>- 5a. System wykrywa brak papieru<br>- 5b. System ukrywa opcję "Bon ze zniżką"<br>- 5c. System oferuje alternatywne metody<br><br>**A8: Anulowanie transakcji**<br>- 4a. Użytkownik wybiera "Anuluj"<br>- 4b. System anuluje transakcję<br>- 4c. System wraca do przyjmowania butelek |
| **Warunki końcowe** | - Środki zostały wypłacone wybraną metodą<br>- Powiadomienie o transakcji zostało wysłane<br>- System został zresetowany do stanu początkowego<br>- Wyświetlacz pokazuje ekran powitalny |

---

## UC10: Maintenance automatu

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Konserwacja i serwis automatu |
| **Aktor** | Serwisant |
| **Opis** | Serwisant wykonuje czynności konserwacyjne automatu w celu utrzymania jego sprawności |
| **Warunki wstępne** | - Serwisant ma dostęp do automatu<br>- Serwisant posiada uprawnienia i klucze<br>- System wysłał powiadomienie o konieczności serwisu LUB jest zaplanowana konserwacja |
| **Główny scenariusz** | 1. Serwisant loguje się do trybu serwisowego<br>2. System wyświetla status automatu<br>3. Serwisant sprawdza poziom napełnienia kontenerów<br>4. Serwisant opróżnia kontenery z butelkami<br>5. Serwisant sprawdza stan rolki papieru<br>6. Serwisant wymienia rolkę papieru (jeśli potrzeba)<br>7. Serwisant sprawdza stan pieniędzy<br>8. Serwisant uzupełnia monety (jeśli potrzeba)<br>9. Serwisant sprawdza stan techniczny elementów<br>10. Serwisant zatwierdza zakończenie konserwacji<br>11. System wysyła powiadomienie o zakończeniu serwisu<br>12. System wraca do trybu normalnego |
| **Alternatywne scenariusze** | **A1: Poważna awaria**<br>- 9a. Serwisant wykrywa poważną usterkę<br>- 9b. Serwisant przełącza automat w tryb "Out of commission"<br>- 9c. System wyświetla "Automat nieczynny"<br>- 9d. System blokuje przyjmowanie butelek<br>- 9e. System wysyła powiadomienie o awarii<br><br>**A2: Kontenery prawie pełne**<br>- 3a. System wykrywa napełnienie powyżej 80%<br>- 3b. System wysyła powiadomienie o zbliżającym się przepełnieniu<br><br>**A3: Papier kończy się**<br>- 5a. System wykrywa, że papier kończy się<br>- 5b. System wysyła powiadomienie o konieczności wymiany<br><br>**A4: Pieniądze kończą się**<br>- 7a. System wykrywa, że monet jest mniej niż 20%<br>- 7b. System wysyła powiadomienie o konieczności uzupełnienia<br><br>**A5: Konserwacja prewencyjna**<br>- 1a. Serwisant rozpoczyna zaplanowaną konserwację<br>- 1b. System nie wysyłał wcześniej powiadomień<br>- 1c. Serwisant wykonuje standardowe czynności kontrolne |
| **Warunki końcowe** | - Kontenery zostały opróżnione<br>- Papier został uzupełniony (jeśli potrzeba)<br>- Monety zostały uzupełnione (jeśli potrzeba)<br>- System jest w trybie normalnym LUB w trybie "Out of commission"<br>- Powiadomienie o stanie po serwisie zostało wysłane |

---

## UC11: Wysyłanie powiadomień

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Wysyłanie powiadomień do systemu sklepu |
| **Aktor** | System sklepu/Aplikacja |
| **Opis** | Automat automatycznie wysyła powiadomienia o stanie technicznym i transakcjach do centralnego systemu |
| **Warunki wstępne** | - Automat ma połączenie z systemem sklepu<br>- Wystąpiło zdarzenie wymagające powiadomienia |
| **Główny scenariusz** | 1. System wykrywa zdarzenie wymagające powiadomienia<br>2. System przygotowuje dane powiadomienia<br>3. System wysyła powiadomienie POST do systemu sklepu<br>4. System otrzymuje potwierdzenie odbioru<br>5. System loguje wysłane powiadomienie |
| **Alternatywne scenariusze** | **A1: Powiadomienie o stanie technicznym - papier**<br>- 1a. System wykrywa, że papier kończy się (<20%)<br>- 1b. System wysyła powiadomienie "LOW_PAPER"<br><br>**A2: Powiadomienie o stanie technicznym - kontener**<br>- 1a. System wykrywa, że miejsce w kontenerze się kończy (>80%)<br>- 1b. System wysyła powiadomienie "CONTAINER_FULL"<br><br>**A3: Powiadomienie o stanie technicznym - pieniądze**<br>- 1a. System wykrywa, że pieniądze się kończą (<20%)<br>- 1b. System wysyła powiadomienie "LOW_COINS"<br><br>**A4: Powiadomienie o transakcji**<br>- 1a. Użytkownik zakończył transakcję<br>- 1b. System wysyła powiadomienie "TRANSACTION_COMPLETE" z danymi transakcji<br><br>**A5: Brak połączenia**<br>- 3a. System nie może połączyć się z serwerem<br>- 3b. System zapisuje powiadomienie w kolejce<br>- 3c. System próbuje wysłać ponownie co 5 minut<br><br>**A6: Krytyczna awaria**<br>- 1a. System wykrywa krytyczną awarię<br>- 1b. System wysyła powiadomienie "CRITICAL_ERROR" z najwyższym priorytetem |
| **Warunki końcowe** | - Powiadomienie zostało wysłane i potwierdzone LUB zapisane w kolejce<br>- Zdarzenie zostało zalogowane w systemie<br>- System sklepu otrzymał informację o stanie automatu |

---

## UC12: Obsługa wyświetlacza/interfejsu

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Interakcja użytkownika z wyświetlaczem automatu |
| **Aktor** | Użytkownik |
| **Opis** | Użytkownik nawiguje po interfejsie automatu, wybiera opcje i otrzymuje informacje zwrotne |
| **Warunki wstępne** | - Automat jest włączony<br>- Wyświetlacz działa poprawnie |
| **Główny scenariusz** | 1. System wyświetla ekran powitalny<br>2. Użytkownik wybiera język z dostępnych opcji<br>3. System zmienia język interfejsu<br>4. System wyświetla instrukcję wkładania butelek<br>5. System wyświetla aktualną wysokość uznania (0,00 zł)<br>6. System wyświetla liczbę przyjętych butelek (0 szt.)<br>7. Użytkownik wkłada butelki (UC1)<br>8. System aktualizuje wysokość uznania po każdej butelce<br>9. System aktualizuje liczbę butelek<br>10. System wyświetla timer przed ponownym wrzuceniem (3 sek.)<br>11. Po upływie timera system sygnalizuje gotowość<br>12. Użytkownik wybiera "Zakończ transakcję"<br>13. System wyświetla ekran wyboru metody wypłaty<br>14. Użytkownik wybiera metodę wypłaty<br>15. System przetwarza wypłatę (UC6)<br>16. System wyświetla podsumowanie transakcji<br>17. System wyświetla podziękowanie<br>18. System wraca do ekranu powitalnego |
| **Alternatywne scenariusze** | **A1: Zmiana języka w trakcie**<br>- 7a. Użytkownik wybiera zmianę języka w menu<br>- 7b. System wyświetla dostępne języki<br>- 7c. System zmienia język bez przerywania transakcji<br><br>**A2: Timeout bezczynności**<br>- 7a. Użytkownik nie wkłada butelki przez 60 sekund<br>- 7b. System wyświetla komunikat "Czy chcesz kontynuować?"<br>- 7c. Jeśli brak reakcji przez 30 sek., system przechodzi do wypłaty<br><br>**A3: Anulowanie przed wypłatą**<br>- 12a. Użytkownik wybiera "Anuluj" lub "Wrzuć więcej butelek"<br>- 12b. System wraca do ekranu przyjmowania butelek<br><br>**A4: Błąd przyjęcia butelki**<br>- 7a. System odrzuca butelkę<br>- 7b. System wyświetla komunikat o przyczynie odrzucenia<br>- 7c. System pokazuje instrukcję poprawnego wkładania<br>- 7d. System wraca do przyjmowania po 5 sekundach<br><br>**A5: Automat pełny**<br>- 1a. System wykrywa pełny kontener<br>- 1b. System wyświetla "Automat tymczasowo nieczynny"<br>- 1c. System blokuje możliwość rozpoczęcia transakcji<br><br>**A6: Tryb serwisowy**<br>- 1a. Serwisant aktywuje tryb serwisowy<br>- 1b. System wyświetla interfejs serwisowy<br>- 1c. System blokuje dostęp dla zwykłych użytkowników |
| **Warunki końcowe** | - Użytkownik zakończył interakcję z automatem<br>- System wrócił do ekranu powitalnego<br>- Wszystkie dane transakcji zostały przetworzone<br>- Interfejs jest gotowy dla kolejnego użytkownika |

---

## UC9: Przechowywanie butelek

| Element | Opis |
|---------|------|
| **Przypadek użycia** | Przetwarzanie i przechowywanie przyjętych butelek |
| **Aktor** | System (proces automatyczny) |
| **Opis** | Automat automatycznie sortuje, przetwarza i przechowuje przyjęte butelki w odpowiednich kontenerach |
| **Warunki wstępne** | - Butelka została przyjęta i zweryfikowana<br>- Materiał butelki został określony<br>- W kontenerach jest miejsce |
| **Główny scenariusz** | 1. System identyfikuje materiał butelki (plastik/szkło/aluminium)<br>2. System kieruje butelkę na odpowiedni tor sortujący<br>3. Jeśli butelka plastikowa: system aktywuje mechanizm zgniatający<br>4. System zgniata butelkę do 1/3 objętości<br>5. System przemieszcza butelkę do odpowiedniego kontenera<br>6. System inkrementuje licznik butelek w kontenerze<br>7. System sprawdza poziom napełnienia kontenera<br>8. Jeśli kontener >80%: system wysyła powiadomienie<br>9. System potwierdza umieszczenie butelki |
| **Alternatywne scenariusze** | **A1: Butelka szklana**<br>- 3a. System wykrywa materiał: szkło<br>- 3b. System pomija zgniatanie<br>- 3c. System ostrożnie przemieszcza do kontenera szkła<br><br>**A2: Butelka aluminiowa**<br>- 3a. System wykrywa materiał: aluminium<br>- 3b. System pomija zgniatanie (lub lekko zgniata)<br>- 3c. System przemieszcza do kontenera aluminium<br><br>**A3: Kontener prawie pełny**<br>- 7a. System wykrywa napełnienie >80%<br>- 7b. System wysyła powiadomienie "CONTAINER_ALMOST_FULL"<br>- 7c. System kontynuuje przyjmowanie do 95%<br><br>**A4: Kontener pełny**<br>- 7a. System wykrywa napełnienie >95%<br>- 7b. System wysyła powiadomienie "CONTAINER_FULL"<br>- 7c. System blokuje przyjmowanie kolejnych butelek tego typu<br>- 7d. System wyświetla komunikat użytkownikowi<br><br>**A5: Błąd mechanizmu zgniatającego**<br>- 4a. System wykrywa usterkę mechanizmu<br>- 4b. System pomija zgniatanie<br>- 4c. System umieszcza butelkę niezgniecioną<br>- 4d. System wysyła powiadomienie o usterce<br><br>**A6: Zablokowanie toru**<br>- 5a. System wykrywa blokadę na torze transportowym<br>- 5b. System próbuje usunąć blokadę (odwrócenie silnika)<br>- 5c. Jeśli niepowodzenie: system przechodzi w tryb awaryjny<br>- 5d. System wysyła powiadomienie "TRANSPORT_BLOCKED" |
| **Warunki końcowe** | - Butelka została umieszczona w odpowiednim kontenerze<br>- Liczniki kontenerów zostały zaktualizowane<br>- System monitoruje poziom napełnienia<br>- Powiadomienia zostały wysłane (jeśli potrzeba) |
