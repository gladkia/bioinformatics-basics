# Instrukcja: Podstawy Bioinformatyki (Quarto + WebR)

Ten dokument opisuje, jak skonfigurować środowisko lokalne, zarządzać plikami kursu oraz publikować zmiany na GitHub Pages.

---

## 🛠️ Wymagania wstępne
1. Zainstalowane środowisko **RStudio** (najlepiej najnowsza wersja, która ma wbudowane wsparcie dla Quarto).
2. Zainstalowany system kontroli wersji **Git**.
3. Konto na GitHubie (Twój login: `gladkia`).

## 🚀 Krok 1: Instalacja Quarto
Jeśli jeszcze nie masz Quarto w swoim systemie:
1. Wejdź na stronę: [https://quarto.org/docs/get-started/](https://quarto.org/docs/get-started/)
2. Pobierz i zainstaluj instalator odpowiedni dla Twojego systemu operacyjnego (Windows/Mac/Linux).
3. Uruchom ponownie RStudio.

---

## 🏗️ Krok 2: Tworzenie projektu i repozytorium
1. Utwórz nowe, puste repozytorium na GitHubie (np. `pwbioinfo_2026`).
2. Sklonuj to repozytorium na swój komputer (np. przez RStudio: *File -> New Project -> Version Control -> Git*).
3. Będąc w tym nowym projekcie w RStudio, utwórz strukturę strony Quarto. Wpisz w zakładce **Terminal** (na dole w RStudio):
   ```bash
   quarto create-project --type website
   ```

---

## 🧩 Krok 3: Instalacja rozszerzenia WebR (Interaktywny kod R)
Aby interaktywne bloki kodu (WebR) działały w naszych laboratoriach, musimy dodać odpowiednie rozszerzenie do projektu Quarto.
Wpisz w **Terminalu** (będąc w folderze projektu):
```bash
quarto add coatless/quarto-webr
```
*(Zatwierdź wpisując "Y", gdy instalator zapyta o zgodę).*

Jeśli używasz pakietu `webexercises` do quizów, upewnij się, że masz go zainstalowanego w R:
```R
install.packages("webexercises")
```

---

## 📝 Krok 4: Codzienna praca (Dodawanie laboratoriów)
1. Twórz nowe pliki z rozszerzeniem `.qmd` (np. `laboratorium_1.qmd`, `laboratorium_2.qmd`).
2. Aby podejrzeć, jak wygląda strona **zanim** wrzucisz ją do sieci, użyj przycisku **Render** (ikona niebieskiej strzałki) u góry edytora w RStudio. Otworzy się lokalny podgląd strony.
3. Pliki i nawigację na stronie konfigurujesz w głównym pliku `_quarto.yml`.

---

## 🌐 Krok 5: Publikacja w sieci (GitHub Pages)
Kiedy jesteś zadowolony z wprowadzonych zmian i chcesz opublikować je dla studentów, użyj magicznej komendy w **Terminalu**:
```bash
quarto publish gh-pages
```
**Co robi ta komenda?**
* Kompiluje wszystkie Twoje pliki `.qmd` do czystego HTML.
* Automatycznie wrzuca (pushuje) te wygenerowane pliki na specjalną gałąź `gh-pages` na Twoim GitHubie.
* Twoja strona zaktualizuje się w ciągu 1-2 minut pod adresem: `https://gladkia.github.io/NAZWA_REPOZYTORIUM/`
