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

### Klient:

| Akcja                         | Serwer odpowiada                          | Klient wyświetla                        |
|-------------------------------|-------------------------------------------|-----------------------------------------|
| Uruchomienie serwera          | `Bingo Server is starting...`             | Nie dotyczy                             |
| Połączenie klienta            | `Client connected: /192.168.1.5`          | `Connected to Bingo server.`            |
| Losowanie liczby              | `Number drawn: 12`                        | `Number drawn: 12`                      |
| Klient zgłasza "BINGO"        | `Player /192.168.1.5 has BINGO!`          | `BINGO! Player /192.168.1.5 has BINGO!` |
| Koniec gry                    | `Player /192.168.1.5 won the game!`       | `Game over. You won!`                   |


