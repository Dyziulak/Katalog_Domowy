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
