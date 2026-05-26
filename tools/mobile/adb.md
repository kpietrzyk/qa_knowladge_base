# ADB

## Kategoria

- Główna kategoria: `mobile-testing`
- Podkategoria: `debugging`
- Darmowe: `True`
- Poziom trudności: `medium`
- Wartość dla manualnego testera: `very high`
- Wartość dla automatyzacji: `high`
- Wymaga kodowania: `False`

## Do czego służy

Gdy potrzebujesz technicznych danych z urządzenia, logów, nagrania ekranu albo szybkiej instalacji aplikacji.

## Najlepsze zastosowania

- logi
- instalacja APK
- screenrecord
- zrzuty ekranu
- intencje Android

## Kiedy używać

Używaj tego narzędzia wtedy, gdy jego zastosowanie skraca drogę od obserwacji błędu do technicznego dowodu: logu, requestu, zrzutu, nagrania, testu automatycznego albo raportu.

## Pierwszy praktyczny workflow

1. Zainstaluj narzędzie.
2. Uruchom je na prostym przypadku testowym.
3. Zapisz wynik w bug report template.
4. Porównaj, czy narzędzie realnie skróciło pracę.
5. Dopiero wtedy dodaj je do stałego workflow.

## Następny krok

Naucz się komend: adb devices, adb install, adb logcat, adb shell, adb bugreport.

## ADB Cheat Sheet

```bash
# Urządzenia
adb devices                              # lista podłączonych urządzeń

# Logi
adb logcat                               # logi na żywo
adb logcat -s "TAG"                      # tylko wybrany tag
adb logcat *:E                           # tylko błędy (Error level)
adb logcat > bug_log.txt                 # zapis do pliku

# Nagrywanie ekranu
adb shell screenrecord /sdcard/bug.mp4   # nagraj (max 3 min)
adb pull /sdcard/bug.mp4 .               # pobierz na komputer

# Zrzut ekranu
adb shell screencap /sdcard/screen.png
adb pull /sdcard/screen.png .

# Aplikacje
adb install app-debug.apk                # instalacja APK
adb install -r app-debug.apk             # reinstalacja (zachowaj dane)
adb uninstall com.package.name           # odinstalowanie
adb shell am force-stop com.package.name # wymuś zamknięcie

# Informacje o urządzeniu
adb shell getprop ro.build.version.sdk   # wersja API Android
adb shell getprop ro.product.model       # model urządzenia
adb bugreport bugreport.zip              # pełny raport diagnostyczny
```

## Ryzyka i ograniczenia

- Nie traktuj narzędzia jako celu samego w sobie.
- Sprawdź licencję przed użyciem komercyjnym.
- Zapisuj konfigurację w repo, jeśli narzędzie ma być używane przez zespół.
- Dla narzędzi AI: nie wklejaj poufnego kodu ani danych, jeśli polityka firmy tego zabrania.

## Link

https://developer.android.com/tools/adb

## Prompt AI do nauki narzędzia

```text
Jesteś seniorem QA Mobile. Naucz mnie narzędzia ADB praktycznie.
Kontekst: jestem manualnym testerem aplikacji mobilnych.
Chcę wiedzieć:
1. kiedy używać,
2. jak zainstalować,
3. pierwsze 5 komend / akcji,
4. typowe błędy początkujących,
5. jak użyć tego narzędzia w realnym bug reporcie,
6. jaki jest następny krok automatyzacji.
```
