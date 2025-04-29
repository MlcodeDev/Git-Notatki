# L1
## Akt 1 - Podstawowe pojęcia
`Git` - System kontroli wersji
`Bash` - Jeden z języków konsoli

## Akt 2 - Bash 
## Podstawowe komendy
`cd` - (Change Directory) - Zmień folder. 
- Polecenie `cd` użyte bez ścieżki przekieruje nas do domyślnego folderu 
`ls` - (List) - Wypisz pliki / foldery znajdujące się w ścieżce.
`pwd` - (Print working Directory) - Wypisz obecną ścieżkę w której się znajdujemy.
`touch` - Stwórz nowy plik.
`mkdir`  - (Remove directory) Stwórz nowy folder.
`rm` -(Remove) Usuń 
`rmdir` - (Remove directory) Usuń folder 
- Działa tylko na pustych folderach, foldery z zawartością muszą być usunięte komendą `rm -r` bądź `rm --recursive`
## Foldery
Każdy folder posiada dwie ukryte *pseudo ścieżki* `.` i `..`
`.` - Oznacza obecny folder.
`..` - Oznacza folder o poziom wyżej.
Pseudo ścieżki mogą zostać wypisane komendą `ls -h`, bądź `ls --hidden`

## Akt 3 - Git
`git init` - Inicjalizacja repozytorium git  - Dodaje system git do naszego projektu tworząc ukrytą ścieżkę `.git`. Od tego momentu, folder z git nazywa się repozytorium.
`git add` - Dodaje pliki / foldery do systemu git
- Można dodać całą zawartość folderu z użyciem komendy `git add .`
`git commit` - Zapisuje zmiany w git
* Jeżeli chcemy dodać wiadomość do naszego commit-a używamy argumentu `-m` . Przykładowo `git commit -m "First commmit"`
`git log` - Wypisz logi commit-ów
`git status` - Wypisz zmiany.

# L2

## Branch
`branch` - Gałąź w systemie git. Umożliwia pracę nad różnymi wersjami projektu jednocześnie.

### Podstawowe komendy:
`git branch` - Wypisz wszystkie istniejące gałęzie  
`git branch <nazwa>` - Utwórz nową gałąź o podanej nazwie  
`git checkout <nazwa>` - Przełącz się na inną gałąź  
`git checkout -b <nazwa>` - Utwórz nową gałąź i od razu się na nią przełącz  
`git branch -d <nazwa>` - Usuń gałąź (tylko jeżeli została zmergowana)  
`git branch -D <nazwa>` - Wymuś usunięcie gałęzi  

### Gałąź główna
Domyślną gałęzią jest zazwyczaj `main` (lub `master` w starszych projektach)  
Praca na osobnych gałęziach pozwala eksperymentować bez ryzyka uszkodzenia głównej wersji projektu.

---

## Git Merge

`merge` - Łączy zmiany z jednej gałęzi do drugiej (np. z gałęzi roboczej do `main`)

### Podstawowe komendy:
`git merge <nazwa-gałęzi>` - Połącz wskazaną gałąź z obecną  

### Przykład:
```bash
git checkout main
git merge feature-branch
```

---

## Akt 6 Git Rebase

`rebase` - Przenosi zmiany z jednej gałęzi i "nakłada" je na inną, tworząc czystszą historię commitów.

### Podstawowe komendy:
`git rebase <nazwa-gałęzi>` - Przenieś obecną gałąź "na bazę" wskazanej gałęzi  
`git rebase -i <commit>` - Interaktywny rebase – pozwala na edycję, łączenie lub usuwanie commitów  

### Przykład:
```bash
git checkout feature-branch
git rebase main
```

📌 Rebase przepisuje historię commitów 