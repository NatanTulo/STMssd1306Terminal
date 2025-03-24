# STMssd1306Terminal

Projekt demonstruje wykorzystanie wyświetlacza OLED z kontrolerem SSD1306 w aplikacji terminalowej uruchamianej na mikrokontrolerze STM32F4.

## Spis treści
- Opis projektu
- Konfiguracja sprzętowa i oprogramowania
- Struktura projektu
- Sposób kompilacji i uruchomienia
- Wykorzystane biblioteki i źródła

## Opis projektu
Głównym celem projektu jest wyświetlanie tekstu w terminalu bezpośrednio na wyświetlaczu OLED. W programie przekierowano funkcję printf do wyświetlania tekstu na ekranie OLED za pomocą biblioteki SSD1306.

## Konfiguracja sprzętowa i oprogramowania
- Mikrokontroler: STM32F4
- Interfejs komunikacyjny z OLED: I2C (SSD1306_I2C_PORT ustawiony na hi2c1, adres: 0x3C)
- Biblioteka OLED: SSD1306 (wsparcie dla I2C)
- Fonty: Kilka fontów, między innymi Font_6x8, włączonych w pliku konfiguracyjnym (ssd1306_conf.h)

## Struktura projektu
- **Src/main.c** – główny plik programu, inicjalizacja HAL, konfiguracja systemu zegara, inicjalizacja I2C oraz OLED.
- **Inc/ssd1306.h** – nagłówek biblioteki SSD1306 z definicjami funkcji do rysowania na ekranie.
- **Inc/ssd1306_fonts.h** – definicje wykorzystywanych fontów.
- **Inc/ssd1306_conf.h** – konfiguracja biblioteki, wybór mikrokontrolera (STM32F4) oraz interfejsu I2C.

## Sposób kompilacji i uruchomienia
1. Otwórz projekt w STM32CubeIDE lub innym kompatybilnym środowisku.
2. Upewnij się, że ustawienia projektu odpowiadają konfiguracji sprzętowej (I2C, zegary itp.).
3. Zbuduj projekt i wgraj firmware do mikrokontrolera.
4. Po uruchomieniu, co 2 sekundy na wyświetlaczu OLED pojawi się komunikat terminalowy z inkrementowaną wartością.

## Wykorzystane biblioteki i źródła
- Biblioteka SSD1306 autorstwa Olivier Van den Eede z refaktoryzacją oraz wsparciem SPI dodanym przez Aleksander Alekseev.
- Oryginalne fonty wykorzystane w projekcie są częścią biblioteki SSD1306 i mogą pochodzić z otwartych źródeł.

Projekt jest licencjonowany zgodnie z warunkami zawartymi w oryginalnych plikach, a wszelkie prawa autorskie należą do STMicroelectronics oraz autorów biblioteki SSD1306.