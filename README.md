# Gra w Bingo - Aplikacja Klient-Serwer 🎲

## 📜 Opis projektu
Gra w Bingo to aplikacja klient-serwer umożliwiająca wielu użytkownikom udział w grze w czasie rzeczywistym.  
Serwer losuje liczby w ustalonych odstępach czasu i informuje o tym wszystkich podłączonych klientów.  
Każdy klient posiada swoją losowo wygenerowaną kartę Bingo i może zgłaszać "BINGO!", jeśli uzna, że jego karta spełnia warunki wygranej.

### Funkcje aplikacji:
- **Serwer**: 
  - Losuje liczby co 5 sekund.
  - Wysyła wylosowane liczby do klientów.
  - Obsługuje zgłoszenia "BINGO!" i weryfikuje wygraną.
- **Klient**: 
  - Wyświetla swoją kartę Bingo.
  - Odbiera wylosowane liczby od serwera.
  - Pozwala zgłosić "BINGO!" i informuje o wyniku.

Aplikacja wykorzystuje:
- **Programowanie wielowątkowe**: Każdy klient jest obsługiwany w osobnym wątku.
- **Komunikację sieciową**: Gniazda (sockets) umożliwiają przesyłanie danych między serwerem a klientami.
- **Obsługę błędów**: Reaguje na sytuacje takie jak utrata połączenia czy nieprawidłowe zgłoszenie "BINGO!".

---

## ⚙️ Wymagania
- **Java Development Kit (JDK)** 8 lub nowszy
- Sieć lokalna (LAN)

---

## 🚀 Instrukcja uruchomienia

### 1️⃣ Uruchomienie serwera
1. Otwórz terminal lub konsolę.
2. Przejdź do katalogu, w którym znajduje się plik `BingoServer.java`.
3. Skompiluj kod serwera:
   ```bash
   javac BingoServer.java

4. Uruchom serwer
   ```bash
   java BingoServer

5. Serwer rozpocznie nasłuchiwanie na porcie `12345`.

### 2️⃣ Uruchomienie klienta
1. Otwórz nowy terminal lub konsolę.
2. Przejdź do katalogu, w którym znajduje się plik `BingoClient.java`.
3. Skompiluj kod klienta
   ```bash
   javac BingoClient.java

4. Uruchom klienta:
   ```bash
   java BingoClient

5. Klient połączy się z serwerem, a następnie wyświetli swoją kartę Bingo.

## 🖥️ Przykłady interakcji

### Serwer:

| Czynność                      | Komunikat w terminalu                     |
|-------------------------------|-------------------------------------------|
| Uruchomienie serwera          | `Uruchamianie serwera do gry w bingo...`  |
| Losowanie liczb               | `Wylosowana liczba: 12`                   |
|                               | `Wylosowana liczba: 90`                   |
|                               | `Wylosowana liczba: 47`                   |
| Zgłoszenie BINGO              | `Gracz /192.168.1.5 zdobył BINGO!`        |

### Klient:

| Czynność                      | Komunikat w terminalu                                 |
|-------------------------------|-------------------------------------------------------|
| Połączenie z serwerem         | `Połączono z serwerem do gry w bingo...`              |
| Wyświetlanie karty            | `Twoja karta bingo: [6, 7, 34, 47, 90]`               |
| Odbieranie numerów            | `Wylosowana liczba: 90`                               |
|                               | `Wylosowana liczba: 47`                               |
|                               | `Wylosowana liczba: 12`                               |
| Zgłoszenie BINGO              | `BINGO`                                               |
|                               | Odpowiedź serwera: `Gracz /192.168.1.5 zdobył BINGO!` |


## ❌ Obsługa błędów
- **Serwer wyłączony**: Jeśli serwer zostanie zatrzymany, klienci otrzymają komunikat o rozłączeniu.
- **Niepoprawne zgłoszenie BINGO**: Jeśli karta klienta jest niepoprawna, serwer informuje o błędzie.
- **Utrata połączenia**: W przypadku rozłączenia serwera lub klienta aplikacja kończy działanie i wyświetla odpowiedni komunikat.

  
## 📊 Przykładowy przebieg gry

### Serwer:
   ```bash
   Uruchamianie serwera do gry w bingo...
   Serwer jest obsługiwany na porcie 12345
   Wylosowana liczba: 90
   Wylosowana liczba: 47
   Wylosowana liczba: 12
   Gracz /192.168.1.5 zdobył BINGO!
   ```

### Klient:
   ```bash
   Połączono z serwerem do gry w bingo.
   Witamy w grze w bingo! Twoja gra się rozpoczeła.
   Twoja karta bingo: [6, 7, 34, 47, 90]
   Wylosowana liczba: 90
   Wylosowana liczba: 47
   Wylosowana liczba: 12
   BINGO
   Gracz /192.168.1.5 zdobył BINGO!
   ```

ℹ️ Uwagi
- **Komunikacja w LAN**: Aplikacja działa w sieci lokalnej. Upewnij się, że firewall nie blokuje portu `12345`.
- **Jedna wygrana**: Serwer nie obsługuje kolejnych zgłoszeń "BINGO!" po ogłoszeniu zwycięzcy.
