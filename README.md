<div align="center"><h1> 🐍 Wprowadzenie do języka Python 🐍 </h1></div>

> Python - jest to język programowania wysokiego poziomu, do ogólnego przeznaczenia. Ideą języka jest czytelność i klarowność kodu źródłowego (co jak się może okazać nie aż tak dobre jak założenia przedstawiają). Python otacza się następującymi paradygmatami programowania: obiektowy, imperatywny oraz funkcyjny. 

Zaletą języka dla początkujących programistów jest ``dynamiczny system typów`` oraz ``zarządzanie pamięcią``, czyli nie trzeba się martwić czy zmienna ``a`` przypisana do cyfry posiada typ ``str`` (ciągu znaków) czy ``int`` (liczba całkowita), a także czy mamy konkretnie miejsce w pamięci dla tej zmiennej. 

>``Psst.`` paradygmat programowania oznacza tyle, że jest to jakiś wzorzec według którego orientowany jest w tym przypadku język programowania.

>``Psst 2.`` a paradygmat obiektowy oznacza tyle, że działania głównie są opierane na jakimś obiekcie z zdefiniowaną abstrakcyjną strukturą zwaną także klasą (trochę się zagłębiam, ale to oznacza tyle, że obiekt to może być plastikowy sześcian, który można było wydrukować za pomocą jakiegoś schematu w drukarce 3D który nazwalibyśmy klasą).

To, co w Pythonie jest jednym z najbardziej charakterystycznych wyróżników jest to, że sposób formatowania składni ma znaczenie. To znaczy fakt czy blok instrukcji jest wcięty ``(za pomocą spacji lub tabulatora)`` może oznaczać, czy jest on, czy nie, częścią innego bloku.

Oprócz tego język Python nie ma żadnego znaku końca linii poza znakiem nowej linii. To znaczy – ``nie ma średników ani kropek``.

> <div align="right"><sub>1.1 Listing - Przykładowa składnia języka Python</sub></div>
```python
def silnia(n):
    print("n = ", n)
    if n > 1:
        return n * silnia(n - 1)
    else:
        return 1
```


  ## 🔖 Syntaktyka języka Python
  
  Zmienne będą miały typ wydedukowany (``inferowany``), typ nie jest dla danej zmiennej stały, można potem go zmienić (czyli w Pythonie jest typowanie dynamiczne), ale Python nie pozwoli np. na bezpośrednie dodanie do siebie liczby i litery (czyli jest ``typowanie silne``), w odróżnieniu na przykład od języka JavaScript, który konwertuje typy „w locie”. 
  
  > <div align="right"><sub>1.2 Listing - Przykłady dynamicznego typowania</sub></div>
  ```python
  x = 1     # x będzie typu int
  y = 1.1   # y będzie typu float
  z = "ala" # z będzie typu string
  ą = False # ą będzie typu bool
  
  a = x + y # operacja zadziała, bo automatycznie liczby zostaną dodane
  b = y + z # operacja nie zadziała, bo dodajemy różne typy do siebie
  0 < x < 5 # operacja zwróci True
  ```

  >Do zapewnienia rozgałęzień w programie używamy typowej instrukcji ``if`` lub ``switch`` (dostępnej od wersji 3.10). Można używać samego if, jak i ``if/else``, jak i ``if/elif/else`` do zapewnienia różnych wersji odpowiedzi, jednak każde z nich wymaga stworzenia całego bloku.

  Operator sprawdzania równości to ``==``, a nierówności to ``!=``, operatory logiczne ``or``, ``and`` oraz ``not`` są zapisywane dokładnie takimi słowami, ale jedną z ciekawych cech jest możliwość porównywania kilku elementów naraz w jednym wyrażeniu, bez konieczności wykorzystania operatora ``and``. Jest to ostatni przykład przedstawiony na listingu 1.2.


  ### 🌟 Zadania do wykonania

  1. Zapisz dowolną zmienną typu ``float`` i dodaj do niej dowolną zmienną typu ``int``, wyświetl wynik.

  2. Przypisz do zmiennej ``imie`` swoje własne imię, a następnie przyrównaj tą zmienną z ciągiem znaków ``"zadanie 2"``.

  3. Wybierz trzy dowolne liczby, przypisz je do zmiennych i ułóż warunek ``True`` korzystając ze znaków ``<``, ``>``, ``=`` pomiędzy tymi zmiennymi.


---

  ## 💱 Konwersje typów
  
  Konwersja między typami zmiennych może zachodzić poprzez wbudowane funkcje takie jak ``str()``, ``int()``, ``bool()`` i inne, odpowiednie dla wszystkich wymienionych typów. 
  Wyniki jednak mogą nieco odbiegać od oczekiwań, zwłaszcza w przypadku konwersji na wartość logiczną.


  > <div align="right"><sub>1.3 Listing - Przykładowe wymuszenie zmiany typu</sub></div>
  ```python
  print(type(str(1.1)))       # <class 'str'>
  print(type(str(2)))         # <class 'str'>
  print(type(int("2")))       # <class 'int'>
  print(type(float("2.1")))   # <class 'float'>


  print(bool(1))      # True
  print(bool(1.1))    # True
  print(bool(0))      # False
  print(bool(-1))     # True
  ```


  ### 🌟 Zadania do wykonania

  1. Napisz funkcję podnoszącą wprowadzony argument do x<sup>3</sup>.
  
  2. Przerób funkcję z poprzedniego punktu tak, aby przyjmowała argument od użytkownika i operowała na typie ``float``.


---

  ## 📦 Funkcje i parametry oraz parametry nazwane

  Funkcja ``print()`` pozwala na wyświetlanie tekstu na ekranie. Funkcja ta jednak może przyjmować wiele parametrów, w tym część określonych jako parametry nazwane, tj. takie, w których wymagane jest określenie nazwy parametru przy jego wywołaniu.

  > <div align="right"><sub>1.4 Listing - Zastosowanie rozwiniętej funkcjonalności funkcji print()</sub></div>
  ```python
  print("TEB Edukacja", end=" ") # wyświetla tekst ale na zakończenie
  print("TEB Edukacja", end=" ") # nie znak nowej linii, ale spacja
  ```

  Parametry nazwane można stosować do wszystkich parametrów, można również mieszać te konwencje. Nie jest jednak możliwe użycie parametru nazwanego, a po nim parametrów pozycyjnych

  > <div align="right"><sub>1.5 Listing - Przykład zastosowania parametrów nazwanych</sub></div>
  ```python
  def dodawanie(a, b):
    return a + b

  print(dodawanie(1, 2))
  print(dodawanie(1, b=2))
  print(dodawanie(a=1, b=2))
  print(dodawanie(b=2, a=1))
  print(dodawanie(b=2, 1)) # SyntaxError: positional argument follows keyword argument
  ```


  Python dysponuje również bliźniaczą funkcją w stosunku do ``print()``, funkcją ``input()``,
  która pozwala pobrać od użytkownika tekst z konsoli, opcjonalnie podając komunikat prośby.
  
  Funkcja ta przyjmuje zawartość wprowadzoną od użytkownika i automatycznie konwertuje ją na typ ``string``.

  > <div align="right"><sub>1.6 Listing - Przykładowe zastosowanie funkcji input()</sub></div>
  ```python
  wprowadzony_tekst = input("Podaj tekst: ")
  ```


  ### 🌟 Zadania do wykonania

  1. Napisz funkcję podnoszącą wprowadzony argument do x<sup>3</sup>.
  
  2. Przerób funkcję z poprzedniego punktu tak, aby przyjmowała argument od użytkownika i operowała na typie ``float``.


---

  ## ➰ Generatory i pętle

  Funkcja ``range()`` zwraca generator – specjalny obiekt, po którym można iterować, którego zawartością są elementy od ``0`` do podanej wartości. Można go skonwertować na listę za pomocą funkcji ``list()``.
  
  Generator liczb ``range()`` przyjmuje 3 argumenty. Domyślny ``skok_iteracji`` to ``1``, a ``początek_iteracji`` to ``0``.
  ```
  range(początek_iteracji, koniec_iteracji - 1, skok_iteracji)
  ```
  Jednak wykorzystywany może być z ilością argumentów do 1 do 3.

  W jakim celu stosować funkcję ``range()``? W odróżnieniu od wielu innych języków programowania, Python nie dysponuje pętlą ``for``, która uruchamia się określoną liczbę razy. Można jednak wykorzystać pętlę ``for-in``, służącą do przechodzenia po wszystkich elementach listy, w połączeniu z funkcją ``range()``, do stworzenia pętli iterującej w określonych granicach.
  
  > <div align="right"><sub>1.7 Listing - Zastosowanie funkcji range() z użyciem argumentów</sub></div>
  ```python
  list(range(3)) # generuje listę [0, 1, 2]
  list(range(3,9)) # generuje listę [3, 4, 5, 6, 7, 8]
  list(range(3,12,3)) # generuje liste [3, 6, 9]
  ```
  
  W pętlach występuje również podstawowa pętla ``while``, możemy wykorzystywać w trakcie jej działania takie polecenia jak ``continue`` oraz ``break``. Alternatywą dla ``continue`` jest ``pass``

  Przy wykorzystywaniu pętli ``while`` ważny jest odpowiedni warunek kończący pętle, w przeciwnym wypadku będzie się wykonywać w nieskończoność.

  > <div align="right"><sub>1.8 Listing - Pętla while z zastosowaniem continue oraz break</sub></div>
  ```python
  x = 0
  while x < 10:
    x += 1
    if x == 5:
        continue
    else if x == 8:
        break
  print(x)
  ```
  > W momencie iteracji zmiennej ``x``, gdy wynosi ona 5 warunek jest spełniony, lecz w bloku występuje polecenie ``continue`` do "kontynuacji" działania pętli, więc wykonuje się dalej, aż do momentu gdy ``x`` ma wartość 9, wykonuje się wtedy polecenie ``break`` i pętla zostaje przerwana.


  > <div align="right"><sub>1.9 Listing - Wypisanie mnożenia w zakresie 10 z użyciem pętli</sub></div>
  ```python
  for x in range(10):
      print(x, '** 2 =', x*x)
  ```

  Dodatkowo, pętla for-in może być również wykorzystana do iterowana po dowolnej liście:

  > <div align="right"><sub>1.10 Listing - Wypisanie elementów listy za pomocą pętli</sub></div>
  ```python
  for i in [1, 3, 3, 7]:
      print(i)
  ```

  Jak również po łańcuchu znaków, znak po znaku:
  > <div align="right"><sub>1.11 Listing - Wypisanie znak po znaku ciągu znaków za pomocą pętli</sub></div>
  ```python
  for i in "TEB Edukacja":
      print(i)
  ```


  ### 🌟 Zadania do wykonania

  1. Za pomocą pętli ``while`` zapisz poniższą pętle.
     ```python
     some_list = [5, 2, 62, 3, 12, 3, 7, 22, 753]
     for i in some_list:
        if i < 21:
            some_list.append(i//2)
            continue
        elif 0 in some_list:
            break
        print(some_list)
     ```

  2. Napisz program, który zlicza liczby parzyste i nieparzyste w podanej niżej krotce.
     ```python
     some_tuple = (6,2,5,1,87,13,63,33,1956,88,0)
     ```

  3. Napisz program, który iteruje od ``1`` do ``100``, przy liczbach wielokrotności 3 wypisuje ``Fizz`` zamiast numeru, a dla liczb podzielnych przez 5 - ``Buzz``. Natomiast dla liczb podzielnych przez 3 oraz 5 wypisuje ``FizzBuzz``. 


---

  ## 📔 Słowniki

  Słownik to jedna z podstawowych struktur danych w Pythonie, odpowiadająca tablicy asocjacyjnej w PHP. Pozwala na tworzenie struktur w postaci ``Klucz-Wartość``, w których zarówno klucze, jak i wartości, nie muszą być takich samych typów w całym słowniku.
  
  Słowniki definiuje się z wykorzystaniem operatora ``{ }``, a odwołać się do określonego klucza można za pomocą prostego operatora indeksowania ``[ ]``.

  > <div align="right"><sub>1.12 Listing - Odwołanie do wartości słownika za pomocą klucza</sub></div>
  ```python
  słownik = { "klucz": "wartość", "TEB": "Edukacja", "jakaś_liczba": 2137 }
  print(słownik["klucz"])
  print(słownik["jakaś_liczba"])
  ```

  > Można również modyfikować wartości pod określonym kluczem oraz dodawać nowe.

  > <div align="right"><sub>1.13 Listing - Modyfikacja wartości po kluczu oraz dodanie nowych pozycji w słowniku</sub></div>
  ```python
  słownik["jakaś_liczba"] = 2115
  słownik["nowy_klucz"] = "eo eo eo"
  ```

  Jeśli kluczami są łańcuchy znaków, wielkość liter ma oczywiście znaczenie, ponieważ aby operator indeksowania dopasował poszukiwany klucz do klucza w słowniku, oba obiekty muszą być dokładnie równoważne. 
  
  W języku Python większość typów złożonych, do których należą słowniki, są w gruncie rzeczy obiektami. Stąd też możliwe jest wykonywanie operacji na obiekcie słownika z wykorzystaniem operatora kwalifikowanego ``.``.

  > <div align="right"><sub>1.14 Listing - Zastosowanie metody clear() w słowniku</sub></div>
  ```python
  słownik = {"klucz": "wartość", "TEB": "Edukacja", "jakaś_liczba": 2137}
  słownik.clear()
  print(słownik) # {}
  ```

  > <div align="right"><sub>1.15 Tabela - Dostępne metody na słownikach</sub></div>
  <div align="center">
    <table>
    <tr align="center">
    <th style="text-align:center">Metoda</th>
    <th style="text-align:center">Wyjaśnienie</th>
    <th style="text-align:center">Przykład</th>
    </tr>
    <tr align="center">
    <td>clear()</td>
    <td>Czyści cały słownik.</td>
    <td>słownik.clear()</td>
    </tr>
    <tr align="center">
    <td>copy()</td>
    <td>Kopiuje słownik do zmiennej.</td>
    <td>x = słownik.copy()</td>
    </tr>
    <tr align="center">
    <td>pop()</td>
    <td>Usuwa pozycję ze słownika o konkretnym kluczu.</td>
    <td>słownik.pop("klucz")</td>
    </tr>
    <tr align="center">
    <td>del</td>
    <td>Nie do końca metoda, ale przy wykorzystaniu usuwa cały słownik, lub pozycję w słowniku niczym pop().</td>
    <td>del słownik[“klucz”] 
    lub
    <br>del słownik</td>
    </tr>
    <tr align="center">
    <td>keys()</td>
    <td>Zwraca wszystkie klucze w słowniku.</td>
    <td>print(słownik.keys())</td>
    </tr>
    <tr align="center">
    <td>values()</td>
    <td>Zwraca wszystkie wartości w słowniku.</td>
    <td>print(słownik.values())</td>
    </tr>
    <tr align="center">
    <td>items()</td>
    <td>Zwraca wszystkie pozycje w słowniku.</td>
    <td>print(słownik.items())</td>
    </tr>
    </table>
  </div>


  ### 🌟 Zadania do wykonania

  1. Stwórz słownik wybranego samochodu za pomocą funkcji, którą nazwiesz ``utworz_samochod``, słownik powinien mieć conajmniej ``5`` kluczy, których wartości zostaną pobrane od użytkownika. Funkcja powinna zwracać słownik.

  2. Utwórz drugą funkcję ``wybierz_nowszy``, która jako parametry przyjmie dwa słowniki (tj. auta) i porówna ich roczniki, zwróci najnowszy z nich.
  
  3. Utwórz funkcję która sprawdza czy podana nazwa klucza (jako argument) występuje w danym słowniku słowniku, funkcja powinna zwrócić wartość typu ``bool``.


---

  ## ✉️ Listy

  Listy definiowane są za pomocą nawiasów kwadratowych ``[ ]``. Są to uporządkowane struktury danych elementów, można odwoływać się do nich za pomocą indeksów. Listy nie muszą być ``homogeniczne``, tj. mogą zawierać elementy różnych typów i nie jest to żaden problem. Listy indeksowane są od ``0``.

  > <div align="right"><sub>1.16 Listing - Przykładowa syntaktyka listy</sub></div>
  ```python
  la = [] # lista pusta
  li = ["a", "b", "Joseph Conrad", 3]
  print(li[3]) # wyświetli 3
  print(li[-3]) # wyświetli b
  ```


  Jedną z ciekawych cech języka Python jest operator ``:`` wewnątrz operatora indeksowania ``[ ]``, który posłuży do tworzenia wycinków list, czyli pozwala na tzw. slicing. Slicing można używać z wykorzystaniem następującej składni:


  ```
  Zmienna = Lista[ start : koniec : krok ]
  ```

  Zmienna będzie nową listą utworzoną na podstawie istniejącej listy Lista począwszy od indeksu start, do indeksu koniec -1, co krok.

  > <div align="right"><sub>1.17 Listing - Zastosowanie “cięcia” na liście</sub></div>
  ```python
  li = ["a", "b", "Joseph Conrad", 18]
  print(li[0:2]) # indeksy 0 i 1 -- ['a', 'b']
  print(li[1:2]) # indeksy 1 i 1 -- ['b']
  print(li[:3]) # indeksy od początku do 2 -- ['a', 'b', 'Joseph Conrad']
  print(li[1:]) # indeksy od 1 do końca -- ['b', 'Joseph Conrad', 18]
  print(li[0:3:2]) # indeksy 0, 2 -- ['a', 'Joseph Conrad']
  ```

  jak wspomniano wcześniej, struktury danych w Pythonie są obiektami, stąd też lista dysponuje szeregiem metod.

  > <div align="right"><sub>1.18 Tabela - Dostępne metody na listach</sub></div>
  <div align="center">
    <table>
    <tr align="center">
    <th style="text-align:center">Metoda</th>
    <th style="text-align:center">Wyjaśnienie</th>
    <th style="text-align:center">Przykład</th>
    </tr>
    <tr align="center">
    <td>append()</td>
    <td>Dodaje nowy element na końcu.</td>
    <td>li.append("Taco Hemingway")</td>
    </tr>
    <tr align="center">
    <td>insert()</td>
    <td>Wstawia element we wskazanym miejscu (indeksie).</td>
    <td>li.insert(0,"Kabriolety")</td>
    </tr>
    <tr align="center">
    <td>extend()</td>
    <td>Dodaje listę do listy na samym końcu.</td>
    <td>li.extend(nowa_lista)</td>
    </tr>
    <tr align="center">
    <td>remove()</td>
    <td>Usuwa element wskazany na liście.</td>
    <td>li.remove(18)</td>
    </tr>
    <tr align="center">
    <td>index()</td>
    <td>Zwraca na którym indeksie listy występuje element podany w parametrze metody.</td>
    <td>print(li.index("Taco Hemingway"))</td>
    </tr>
    <tr align="center">
    <td>sort()</td>
    <td>Sortuje liste, posiada dwa argumenty - reverse do odwrócenia sortowania, oraz key do przypisania funkcji sortującej</td>
    <td>li.sort(reverse=True)</td>
    </tr>
    <tr align="center">
    <td>reverse()</td>
    <td>Mutuje liste i odwraca kolejność elementów.</td>
    <td>li.reverse()</td>
    </tr>
    <tr align="center">
    <td>count()</td>
    <td>Zlicza ilość wskazanego elementu w liście.</td>
    <td>li.count("a")</td>
    </tr>
    </table>
  </div>

  Używa się ich w stosunku do obiektu listy, na przykład: ``li.insert(2, "test")``, jednak mogą zwrócić oczywiście błąd, na przykład funkcja ``index()`` zwraca ``ValueError`` jeżeli obiektu nie ma w liście. 

  > Aby uchronić się przed tym i sprawdzić czy w ogóle obiekt istnieje w liście, można wykorzystać operator ``in``.

  > <div align="right"><sub>1.19 Listing - Zastosowanie metod listy index() oraz sprawdzenie istnienia elementu w liście</sub></div>
  ```python
  li = ["a", "b", "Joseph Conrad", 18]
  print(li.index("a"))      # wyświetla 0
  print(li.index(3.14))    # ValueError: 3.14 is not in list

  print("18" in li)     # wyświetla False
  print(18 in li)       # wyświetla True
  ```

  Usuwanie elementu z listy może być również realizowane przez metodę ``pop()`` która usuwa i zwraca pierwszy element listy.

  > W powiązaniu z metodą ``push()`` można traktować dowolną listę jak stos (strukturę ``LIFO``). Pobieranie aktualnej długości listy realizowane jest jednak zupełnie inaczej – Python oferuje globalną funkcję ``len()``, która zwraca długość dowolnej struktury danych, która umie „obliczyć” swoją długość (np. lista, słownik, generator, krotka, niektóre klasy).

  W podobny sposób lista również może zostać przekonwertowana na łańcuch znaków globalną funkcją ``str()``. Z kolei inne struktury danych można przekonwertować do postaci listy z wykorzystaniem funkcji ``list()``.

  Ważnym szczegółem jest fakt, że listy są zmienne (``mutowalne``), a niektóre funkcje operujące na liście bezpośrednio ją modyfikują, a nie zwracają nową, zmodyfikowaną listę – w szczególności dotyczy funkcji takich jak ``sort()`` oraz ``reverse()``.

  > <div align="right"><sub>1.20 Listing - Metody manipulacji elementami listy</sub></div>
  ```python
  lista = [2, 4, 0]
  lista.sort()

  print(lista) # [0, 2, 4]
  lista.reverse()
  print(lista) # [4, 2, 0]

  # Nieco bardziej skomplikowane sortowanie
  szkolna_17 = [
    {'Imie': 'Zbigniew Stonoga', 'Wiek': 48, 'Wyplata': 4},
    {'Imie': 'Krzysztof Mlekołak Konanowicz', 'Wiek': 60, 'Wyplata': 3200},
    {'Imie': 'Wojciech Major Suchodolski', 'Wiek': 49, 'Wyplata': 30000},
  ]

  szkolna_17.sort(reverse = True, key = lambda x: x['Wiek'])
  print(szkolna_17) 
  ```

  Aby posortować listę w taki sposób, aby została zwrócona nowa, posortowana lista, bez modyfikacji oryginału, należy wykorzystać funkcję ``sorted()``.
  Do funkcji ``sorted()`` można również przekazywać własną funkcję wybierającą klucz sortowania, co będzie istotne w niektórych przypadkach.

  > <div align="right"><sub>1.21 Listing - Przypisanie posortowanej listy do nowej zmiennej</sub></div>
  ```python
  lista = [7, 1, 2, 3]
  lista_posortowana = sorted(lista)
  print(lista) # [7, 1, 2, 3]
  print(lista_posortowana) # [1, 2, 3, 7]
  ```


  ### 🌟 Zadania do wykonania

  1. Utwórz funkcję, która znajdzie i zwróci najmniejszą liczbę w podanej liście.

  2. Utwórz funkcję, która przyjmuje dwie listy zawierające tylko liczby i zwróci listę, która będzie posiadać liczby unikatowe z tych dwóch list.


---

  ## 📑 Krotki

  Krotki są niezmiennymi (``niemutowalnymi``) strukturami danych i mogą zawierać wiele elementów, różnych typów. Podstawową operacją na krotce będzie oczywiście jej dekonstrukcja na wiele zmiennych. W typowych językach funkcyjnych można to wykonywać wewnątrz mechanizmu ``pattern matching`` (regexp), w Pythonie dostępna jest również wersja imperatywna.

  > <div align="right"><sub>1.22 Listing - Przykładowa syntaktyka krotki</sub></div>
  ```python
  k = (1, 2)
  l = (1, "a")
  m = (1, 2, False)

  a, b = (1, "Daenerys")
  print(a) # wyświetla 1
  print(b) # wyświetla Daenerys
  ```

  Krotki przede wszystkim mogą być wykorzystywane do tworzenia funkcji, które zwracają obiekty opakowane w nie, przez co pojedyncza funkcja zwraca nie jedną, ale wiele wartości za pośrednictwem jednego ``return``.

  > <div align="right"><sub>1.23 Listing - Zastosowanie krotki w funkcji</sub></div>
  ```python
  def jakas_funkcja():
      return (2, 3)
  
  x, y = jakas_funkcja() # funkcja efektywnie zwróciła x oraz y
  print(x,y) # 2 3
  ```


  ### 🌟 Zadania do wykonania

  1. Wykorzystaj podaną krotkę do następującego zadania.

     ```python
     some_tuple = (1,5,6,9,"2115","Juan Pablo")
     ```
     - Utwórz funkcję, która sprawdzi wszystkie elementy w krotce i zmieni te ciągi znaków, które posiadają liczbę na typ ``int`` oraz wyeliminuje ciągi znaków, które żadnych liczb nie posiadają.
     
     <br>
     <details>
     <summary>
       ℹ️ Wskazówka
     </summary>

      > Dla sprawdzenia ciągu znaków czy jest liczbą wykorzystuje się metodę ``isdigit()``.

      > Pamiętaj, że krotki są ``niemutowalne`` 😩.

     </details>

     
  2. Wykorzystaj podaną krotkę do następującego zadania.
     ```python
     some_tuple = (1,2,3,4,3,2,1)
     ```
     - Utwórz funkcję, dzięki której znajdziesz wszystkie powtarzające się cyfry oraz zapiszesz do słownika ile razy się powtarzają. Następnie usuniesz duplikaty tych cyfr i zwrócisz krotkę oraz słownik.
     
     <br>
     <details>
     <summary>
       ℹ️ Wskazówka
     </summary>

      > W Pythonie występują jeszcze ``zbiory`` (set), których jedną z cech jest to, że nie zawierają duplikatów, więc często są do tego pośredniego zadania wykorzystywane ;-).

      > ``return`` ma możliwość zwracania więcej niż jednej rzeczy, wystarczy oddzielić po słowie kluczowym te elementy przecinkiem.
        ```python
        return x,y
        ```
     </details>
     
---

  ## ⛓️ Ciągi znaków czyli stringi

  Ciągi znaków w Pythonie opatrywane są apostrofami lub cudzysłowami, i nie ma znaczenia który znak zostanie wykorzystany - nie powoduje to zmian w analizie ciągów, nie rozróżnia pojedynczych znaków – w Pythonie wszystko jest typu ``str``, w odróżnieniu od innych języków programowania rozróżniających znaki typu ``char`` od ciągów, czyli typu ``string``.

  Możliwe jest użycie potrójnych apostrofów lub cudzysłowów, aby utworzyć wielolinijkowe ciągi znaków.

  > <div align="right"><sub>1.24 Listing - Przykładowa syntaktyka wielolinijkowego ciągu znaków</sub></div>
  ```python
  wielolinijkowy_tekst = """bardzo dlugi
  string z wielooma
  liniami"""
  ```

  > Ciekawostką języka Python jest nieobecność wielolinijkowych komentarzy w kodzie – do dokumentacji funkcji czy metod stosuje się wielolinijkowe ciągi znaków, które nie są przypisywane do żadnej zmiennej, co automatycznie powoduje, że interpreter je będzie ignorował.

  > <div align="right"><sub>1.25 Listing - Wykorzystanie sposobu na opisywanie funkcji</sub></div>
  ```python
  def eoeo():
    """
    Ta funkcja robi "eoeo"
    """
    for _ in range(100):
        print("eo\teo\n")

  eoeo()
  ```

  W ciągach znaków występują również sekwencje ucieczki sygnalizujące interpreterowi konkretne działanie, takie jak ``\t`` (tabulacja) czy ``\n`` (przejście do nowej linii).

  Występuje również pojęcie ``interpolacji`` ciągów znakowych, czyli automatycznego wstawiania wartości zmiennych do środka ciągu.

  > <div align="right"><sub>1.26 Listing - Zastosowanie formatowania ciągu znaku za pomocą interpolacji</sub></div>
  ```python
  imie = "Cezary"
  stopien = "Posterunkowy"
  wiek = 60
  print(f"W 13 Posterunku, {imie} Pazura miał stopień {stopien}, a aktualnie ma lat {wiek}")
  ```

  > Jest to bardzo popularny mechanizm stosowany również w języku C# za pomocą operatora ``$`` czy w języku JavaScript poprzez tworzenie łańcuchów z wykorzystaniem znaków `` ` ``.

  Poprzez słowo kluczowe ``import`` można dołączyć do programu dodatkowe moduły, będące luźnym odpowiednikiem bibliotek. Na przykład bibliotekę ``string``, która dostarczy kilka istotnych stałych zawierających różnego typu znaki ``alfanumeryczne``.

  > <div align="right"><sub>1.27 Listing - Przykładowy import modułu string i prezentacja stałych</sub></div>
  ```python
  import string
  
  print(string.ascii_letters)   # abcdefghijklmno...IJKLMNOPQRSTUVWXYZ
  print(string.ascii_lowercase) # abcdefghijklmnopqrstuvwxyz
  print(string.ascii_uppercase) # ABCDEFGHIJKLMNOPQRSTUVWXYZ
  print(string.digits)          # 0123456789
  print(string.punctuation)     # '!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~'
  print(string.printable)       # digits + ascii_letters + punctuation + whitespace
  print(string.whitespace)      # space + tab + linefeed + return + ...
  ```

  > W taki sposób moduł ułatwia znacznie pracę z ciągami znaków w potrzebie np. sprawdzenia siły hasła (czy zawiera małe, duże znaki, znaki specjalne, cyfry).

  Poza modułem ``string``, występuje jeszcze bardzo fundamentalny moduł ``random``. 

  > <div align="right"><sub>1.28 Listing - Import całego modułu random</sub></div>
  ```python
  import random
  
  random.randint(0, 100)        # liczba losowa z zakresu 0-100
  random.choice([2, 0, 1, 1, 230.5])   # losowy element kolekcji
  ```

  Czasami jednak chcielibyśmy zaimportować funkcje bezpośrednio do globalnej przestrzeni nazw, aby uruchamiać je jak dowolne inne globalne lub lokalne funkcje – do tego wykorzystać można składnię ``from ... import ....``

  > <div align="right"><sub>1.29 Listing - Zaimportowanie pojedynczej funkcji z modułu</sub></div>
  ```python
  from random import randint

  def czy_parzysta(x):
    if x // 2:
        return True
    else:
        return False

  losowa_liczba = randint(1,69) # Przypisanie losowej liczby z zakresu 1 - 69
  print(czy_parzysta(losowa_liczba))
  ```
  
  > Możliwe też jest zaimportowanie wszystkich funkcji z modułu, za pomocą składni ``from ... import *``, należy jednak pamiętać, że mogą wystąpić konflikty nazw. Co można rozwiązać przypisując zastępczą nazwę dla konkretnego modułu słowem kluczowym ``as``. Na przykład: ``from ... import * as nowa_nazwa_modulu``.


  ### 🌟 Zadania do wykonania

  1. Napisz funkcje, która wygeneruje losowy numer rejestracyjny samochodu w powiecie. Lublin (LU XXXXX), gdzie X jest wielką literą lub cyfrą.

  2. Napisz funkcję, która zaszyfruje tekst złożony tylko z wielkich liter z wykorzystaniem ``szyfru Cezara``.
     
     <br>
     <details>
     <summary>
       ℹ️ Wskazówka
     </summary>

      > ``Szyfr Cezara`` – rodzaj szyfru, w którym każda litera tekstu niezaszyfrowanego (``jawnego``) zastępowana jest inną, oddaloną od niej o stałą liczbę pozycji w alfabecie literą, przy czym kierunek zamiany musiał być zachowany. Pierwotnie Szyfr Cezara polega na przesunięciu liter tekstu o trzy (klucz przesunięcia zawsze wynosił 3). W szyfrze tym korzysta się wyłącznie z podstawowego alfabetu (od a do z). Nie rozróżnia się tutaj dużych i małych liter, oraz znaków specjalnych.

     </details>


---

  ## 🔪 Operacje na ciągach znaków

  Ciągi znaków jak i listy są traktowane bardzo podobnie - a w związku z tym, można wykorzystać operator ``[ ]`` oraz mechanizm ``slicing`` do zdefiniowania nowego tekstu z już istniejącego.

  > <div align="right"><sub>1.30 Listing - Zastosowanie slicingu na ciągu znaków</sub></div>
  ```python
  abecadło = "abcdefghijklmnoprstuwyz"
  print(abecadło[1:6:2]) # bdf
  ```

  Ważnym szczegółem jednak będzie to, że nie istnieje, jak wspomniano wcześniej, typ danych obejmujący pojedynczy znak – stąd operacja sprawdzenia typu z wykorzystaniem operatora ``type()`` - wyświetli oczywiście ``<class 'str'>``. Drugim ważnym szczegółem jest próba modyfikacji zawartości ciągu znaków.
  Nie powiedzie się ona, wraz z komunikatem błędu.

  > <div align="right"><sub>1.31 Listing - Wykorzystanie operatorów zasięgowych do utworzenia ciągu</sub></div>
  ```python
  abecadło = "abcdefghijklmnoprstuwyz"
  x = abecadło[1]
  print(type(x))    # <class 'str'>

  abecadło[1] = "6" # TypeError: 'str' object does not support item assignment.
  ```

  Oznacza to, że ciąg znaków, w odróżnieniu od listy, jest strukturą niezmienną (``niemutowalną``). Aby móc zmienić pojedynczy znak w ciągu, najlepsze będzie wykorzystanie mechanizmu tworzenia ciągów poprzez operatory zasięgowe.

  > <div align="right"><sub>1.32 Listing - Wykorzystanie operatorów zasięgowych do utworzenia ciągu</sub></div>
  ```python
  abecadło = "abcdefghijklmnoprstuwyz"
  nowe_abecadło = abecadło[:1] + "ą" + abecadło[1:]
  print(nowe_abecadło) # aąbcdefghijklmnoprstuwyz
  ```

  Na ciągach znaków można wykonywać metody modyfikujące wielkość liter, odpowiadają za to metody ``lower()`` i ``upper()``. Są to tylko przykładowe metody.

  > <div align="right"><sub>1.33 Tabela - Dostępne przykładowe metody na stringach</sub></div>
  <div align="center">
    <table>
    <tr align="center">
    <th style="text-align:center">Metoda</th>
    <th style="text-align:center">Wyjaśnienie</th>
    <th style="text-align:center">Przykład</th>
    </tr>
    <tr align="center">
    <td>lower()</td>
    <td>Zamienia litery w ciągu na małe.</td>
    <td>print("ABCDE".lower())</td>
    </tr>
    <tr align="center">
    <td>upper()</td>
    <td>Zamienia litery w ciągu na duże</td>
    <td>print("abcde".upper())</td>
    </tr>
    <tr align="center">
    <td>replace()</td>
    <td>Zamienia jeden podciąg znaków na inny.</td>
    <td>print(tekst.replace("abc","cba"))</td>
    </tr>
    <tr align="center">
    <td>strip()</td>
    <td>Usuwa białe znaki z początku i końca.</td>
    <td>
    tekst = "     banan     "<br>
    x = txt.strip()<br>
    print("ze wszystkich owoców", x, "jest moim ulubionym") 
    </td>
    </tr>
    <tr align="center">
    <td>isdigit()</td>
    <td>Zwraca True jeśli wszystkie znaki są cyframi.</td>
    <td>print(tekst.isdigit())</td>
    </tr>
    <tr align="center">
    <td>islower()</td>
    <td>Sprawdza czy znaki w ciągu są małymi literami</td>
    <td>tekst.islower()</td>
    </tr>
    <tr align="center">
    <td>isnumeric()</td>
    <td>Sprawdza czy ciąg znaków jest numeryczny. Zwraca True albo False</td>
    <td>tekst.isnumeric()</td>
    </tr>
    <tr align="center">
    <td>zfill()</td>
    <td>Wypełnia ciąg znaków zerami od lewej strony.</td>
    <td>tekst.zfill(100)</td>
    </tr>
    <tr align="center">
    <td>startswith()</td>
    <td>Sprawdza czy ciąg znaków zaczyna się określonym tekstem.</td>
    <td>tekst.startswith("abcd")</td>
    </tr>
    <tr align="center">
    <td>endswith()</td>
    <td>Sprawdza czy ciąg znaków kończy się określonym tekstem.</td>
    <td>tekst.endswith("abcd")</td>
    </tr>
    <tr align="center">
    <td>find()</td>
    <td>Szuka w ciągu znaków pozycję tekstu, jeśli nie znajdzie to zwraca -1.</td>
    <td>tekst.find("abc")</td>
    </tr>
    </table>
  </div>


  ### 🌟 Zadania do wykonania

  1. Napisz funkcję, która odwróci podany przez użytkownika tekst i wykorzystaj ją do sprawdzenia czy tekst podany od użytkownika jest ``palindromem``.
     
     <br>
     <details>
     <summary>
       ℹ️ Wskazówka
     </summary>


      > ``Palindrom`` – wyrażenie brzmiące tak samo czytane od lewej do prawej i od prawej do lewej. Przykładem palindromu jest: Kamil Ślimak. 

     </details>

  2. Napisz program, który iterując znak po znaku wyświetli każdą cyfrę liczby w postaci słownej, np. 110 wyświetli jako „jeden jeden zero”.

  3. Napisz program, który zamieni liczbę w postaci rzymskiej na system arabski.


---
