# Gra w Statki - Aplikacja RMI 🚢

## 📜 Opis projektu
Gra w Statki to aplikacja oparta na technologii RMI (Remote Method Invocation), umożliwiająca dwóch graczom udział w rozgrywce w czasie rzeczywistym. 
Serwer zarządza całą logiką gry oraz spójnością danych, natomiast klienci mogą prowadzić bitwy morskie z przeciwnikiem, wykonując ruchy na zdalnej planszy.

### Funkcje aplikacji:
- **Serwer RMI:**
  - Udostępnia metody zdalne umożliwiające:
    - Rejestrację graczy.
    - Zarządzanie planszami i ich stanem.
    - Obsługę ruchów graczy i sprawdzanie trafień.
    - Zakończenie gry po zatopieniu wszystkich statków przeciwnika.
  - Obsługuje jednoczesne połączenia od wielu klientów.

- **Klient RMI:**
  - Łączy się z serwerem.
  - Pozwala na interakcję z grą poprzez:
    - Wyświetlanie planszy.
    - Wykonywanie ruchów (np. strzały).
    - Odbieranie wyników strzałów od serwera.

Aplikacja wykorzystuje:
- **Technologię RMI:** Do komunikacji między klientem a serwerem.
- **Programowanie współbieżne:** Obsługuje wielu graczy jednocześnie.
- **Obsługę wyjątków:** Reaguje na utratę połączenia, błędy serwera lub nieprawidłowe akcje klienta.

---

## ⚙️ Wymagania
- **Java Development Kit (JDK)** 8 lub nowszy.
- Sieć lokalna (LAN).

---

## 🚀 Instrukcja uruchomienia

### 1️⃣ Kompilacja plików
1. Otwórz terminal i przejdź do katalogu, w którym znajdują się pliki `.java`.
2. Skompiluj wszystkie pliki:
   ```bash
   javac *.java
   ```

### 2️⃣ Uruchomienie serwera
1. Uruchom rejestr RMI:
   ```bash
   rmiregistry
   ```
2. W osobnym terminalu uruchom serwer:
   ```bash
   java BattleshipServer
   ```
3. Serwer rozpocznie nasłuchiwanie na domyślnym porcie RMI.

### 3️⃣ Uruchomienie klientów
1. Otwórz nowy terminal dla każdego gracza.
2. Uruchom klienta:
   ```bash
   java BattleshipClient
   ```
3. Klienci połączą się z serwerem i rozpoczną grę.

---

## 🖥️ Przykłady interakcji

### Serwer:

| Czynność                 | Komunikat w terminalu                           |
|--------------------------|-----------------------------------------------|
| Uruchomienie serwera     | `Serwer gry w statki uruchomiony.`             |
| Rejestracja gracza       | `Gracz o ID 1 dołączył do gry.`               |
| Ruch gracza              | `Gracz 1 strzela w pole B3. Wynik: Pudło.`     |
| Trafienie                | `Gracz 2 strzela w pole C4. Wynik: Trafiony.` |
| Koniec gry               | `Gracz 1 wygrał. Wszystkie statki przeciwnika zatopione.` |

### Klient:

| Czynność                 | Komunikat w terminalu                                |
|--------------------------|----------------------------------------------------|
| Połączenie z serwerem    | `Połączono z serwerem gry w statki.`                |
| Wyświetlenie planszy     | `Twoja plansza: 
 ~ ~ ~ ~ ~
 ~ ~ ~ ~ ~
 ~ ~ ~ ~ ~` |
| Wykonanie ruchu          | `Podaj współrzędne (np. A1):`                       |
| Wynik strzału            | `Pudło! Czekaj na ruch przeciwnika.`                |
| Trafienie                | `Trafiony! Wykonaj kolejny ruch.`                   |

---

## ❌ Obsługa błędów
- **Utrata połączenia z serwerem:** Klienci otrzymają komunikat o błędzie i zakończą działanie.
- **Nieprawidłowe współrzędne:** Jeśli gracz poda błędne współrzędne (np. poza planszą), serwer zwróci stosowny komunikat.
- **Serwer zatrzymany:** W przypadku przerwania działania serwera, klienci otrzymają odpowiedni komunikat.

---

## 📊 Przykładowy przebieg gry

### Serwer:
```bash
Serwer gry w statki uruchomiony.
Gracz o ID 1 dołączył do gry.
Gracz o ID 2 dołączył do gry.
Gracz 1 strzela w pole B3. Wynik: Pudło.
Gracz 2 strzela w pole C4. Wynik: Trafiony.
Gracz 1 wygrał. Wszystkie statki przeciwnika zatopione.
```

### Klient:
```bash
Połączono z serwerem gry w statki.
Twoja plansza: 
~ ~ ~ ~ ~
~ ~ ~ ~ ~
~ ~ ~ ~ ~
Podaj współrzędne (np. A1): B3
Pudło! Czekaj na ruch przeciwnika.
Podaj współrzędne (np. A1): C4
Trafiony! Wykonaj kolejny ruch.
