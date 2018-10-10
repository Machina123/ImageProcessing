# Konfiguracja środowiska
Poniżej przedstawiony został proces konfiguracji środowiska identycznego do tego używanego na zajęciach.

---

## Krok 0: przydatne linki
* [Składnia Markdown do opisywania zeszytów w Jupyter](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [Składnia zapisu LaTeX do wzorów matematycznych](https://wch.github.io/latexsheet/latexsheet-a4.pdf)

---

## Krok 1: instalacja Anaconda3

### Linki do pobrania instalatora

* Wersja dla Windows (x64) - https://repo.anaconda.com/archive/Anaconda3-5.3.0-Windows-x86_64.exe
* Wersja dla macOS - https://repo.anaconda.com/archive/Anaconda3-5.3.0-MacOSX-x86_64.pkg
* Wersja dla Linux (x86_64) - https://repo.anaconda.com/archive/Anaconda3-5.3.0-Linux-x86_64.sh

Po pobraniu pliku instalatora, postępujemy zgodnie z instrukcją na ekranie. Może to potrwać od kilku do kilkunastu minut (w zależności od szybkości dysku).

### Uwagi

* **(Windows only)** W końcowym kroku instalacji można zaznaczyć opcję:
    ```     
    Add Anaconda to my PATH environment variable
    ```
    Co prawda twórcy Anacondy tego nie rekomendują, ale znacznie ułatwi to pracę, polecenia Anacondy będą wtedy dostępne w całym systemie.

* Instalację VS Code można pominąć.

---

## Krok 2: konfiguracja środowiska

### Czy Anaconda się zadomowiła?
Można to łatwo sprawdzić, wpisując w konsoli `conda --version`. Jeżeli naszym oczom ukaże się, na przykład:
```
conda 4.5.11
```
to znak, że wszystko jest dobrze zainstalowane.

### Tworzenie środowiska
W konsoli wykonujemy polecenie `conda create -n py36 python=3.6`. Ale co to właściwie znaczy? 

* `conda create` - polecenie Anacondy tworzące nowe środowisko
* `-n py36` - przełącznik `-n` odpowiada za ustawienie nazwy środowiska, używam takiej samej nazwy jaka jest ustawiona w sali komputerowej, czyli `py36`
* `python=3.6` wymusza użycie Pythona w wersji 3.6 - z tej korzystamy na zajęciach

Naszym oczom może się ukazać coś takiego:
```
Solving environment: done

## Package Plan ##

  environment location: C:\Users\Machina\Anaconda3\envs\py36

  added / updated specs:
    - python=3.6


The following packages will be downloaded:

    [REDACTED]

The following NEW packages will be INSTALLED:

    [REDACTED]

Proceed ([y]/n)?
```
W tym miejscu wpisujemy `y` i potwierdzamy klawiszem Enter. Gdy proces się zakończy, możemy sprawdzić, czy wszystko zostało poprawnie utworzone, wpisując komendę `conda env list`. Naszym oczom ukaże się spis skonfigurowanych środowisk, na przykład:
```
# conda environments:
#
base                  *  C:\Users\Machina\Anaconda3
py36                     C:\Users\Machina\Anaconda3\envs\py36
```

Jeżeli widzimy nasze środowisko na liście, oznacza to, że zostało ono poprawnie założone. Gwiazdka przy nazwie oznacza aktualnie 

### Instalacja wymaganych paczek
Na początku aktywujmy nasze nowo założone środowisko komendą (w zależności od systemu):

* **Windows:** `activate py36`
* **Linux:** `source activate py36`
* **macOS:** `conda activate py36`

gdzie `py36` to nazwa naszego środowiska podana podczas jego tworzenia.

Po tej operacji prompt w naszej konsoli zmieni się na, przykładowo (w systemie Windows):
```
(py36) C:\Users\Machina\Documents\GitHub\ImageProcessing>
```

Instalację wszystkich paczek można załatwić jedną komendą:
```
conda install numpy matplotlib scikit-image py-opencv
```
Po wprowadzeniu i zatwierdzeniu tego polecenia, po chwili na ekranie może pojawić się:
```
Solving environment: done

## Package Plan ##

  environment location: C:\Users\Machina\Anaconda3\envs\py36

  added / updated specs:
    - matplotlib
    - numpy
    - py-opencv
    - scikit-image


The following packages will be downloaded:

    [REDACTED]

The following NEW packages will be INSTALLED:

    [REDACTED]

Proceed ([y]/n)?
```
Oczywiście, potwierdzamy, wpisując `y` i zatwierdzamy klawiszem Enter.

---

## Krok 3: uruchomienie środowiska

### Aktywacja środowiska w Anaconda

Jeżeli nie aktywowaliśmy naszego środowiska, robimy to następującą komendą (w zależności od systemu operacyjnego)
* **Windows:** `activate py36`
* **Linux:** `source activate py36`
* **macOS:** `conda activate py36`

gdzie `py36` to nazwa naszego środowiska podana podczas jego tworzenia.

Po tej operacji prompt w naszej konsoli zmieni się na, przykładowo (w systemie Windows):
```
(py36) C:\Users\Machina\Documents\GitHub\ImageProcessing>
```

### Uruchomienie zeszytu Jupyter

Jupyter jest domyślnie instalowany razem z Anacondą. Aby włączyć nasz zeszyt wystarczy _(w odpowiednim katalogu)_ wywołać polecenie 
```
jupyter notebook
```
Naszym oczom powinna ukazać się przeglądarka internetowa z otwartym Jupyterem.

### Zakończenie pracy

Przeglądarkę z Jupyterem wystarczy zwyczajnie zamknąć, a w konsoli z Anacondą naciskamy kombinację klawiszy `Ctrl+C`, także na komputerach z jabłuszkiem. Poprawne zakończenie pracy objawi się poprzez następującą informację na ekranie:
```
[...]
[I 19:48:52.797 NotebookApp] Interrupted...
[...]
```
oraz powrotem prompta.

### Dezaktywacja środowiska w Anaconda

Aby powrócić do stanu sprzed aktywacji środowiska, wykorzystamy polecenie 
* **Windows:** `deactivate`
* **Linux:** `source deactivate`
* **macOS:** `conda deactivate`

Nie podajemy nazwy środowiska.

Jeżeli prompt powróci do _normalności_, na przykład:
```
C:\Users\Machina\Documents\GitHub\ImageProcessing>
```
oznacza to, że środowisko zostało wyłączone.

---

_Poradnik oraz linki są aktualne na dzień 10 października 2018._