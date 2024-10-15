# Tworzenie Tabel i Bloków Div za Pomocą Pętli w PHP

## Wprowadzenie

Cześć! Dzisiaj nauczymy się, jak w języku PHP tworzyć tabele i bloki `div` za pomocą pętli. Pętle pozwalają nam powtarzać ten sam kod wiele razy, co jest bardzo przydatne przy tworzeniu powtarzających się elementów na stronie.

---

## Pętle w PHP

Pętle to sposób na powtarzanie kodu. W PHP najczęściej używamy pętli:

- **for** – gdy wiemy, ile razy pętla ma się wykonać.
- **while** – gdy chcemy powtarzać kod, dopóki jakiś warunek jest spełniony.

---

## Tworzenie Tabeli za Pomocą Pętli

### Cel

Chcemy stworzyć tabelę z nagłówkiem i kilkoma wierszami. Użyjemy pętli tylko do generowania wierszy, a nagłówek dodamy osobno.

### Krok po kroku

1. **Rozpocznij tabelę** – otwórz znacznik `<table>`.
2. **Dodaj wiersz nagłówkowy** – użyj znaczników `<th>`.
3. **Użyj pętli do generowania wierszy** – wygeneruj zawartość tabeli.
4. **Zamknij tabelę** – zamknij znacznik `</table>`.

### Kod

Oto kod, który to robi:

```php
<?php
echo "<table border='1'>";

// 1. Tworzymy wiersz nagłówkowy
echo "<tr>";
echo "<th>Kolumna 1</th>";
echo "<th>Kolumna 2</th>";
echo "<th>Kolumna 3</th>";
echo "</tr>";

// 2. Generujemy wiersze za pomocą pętli
for ($wiersz = 1; $wiersz <= 5; $wiersz++) {
    echo "<tr>";
    echo "<td>Wiersz $wiersz, Kolumna 1</td>";
    echo "<td>Wiersz $wiersz, Kolumna 2</td>";
    echo "<td>Wiersz $wiersz, Kolumna 3</td>";
    echo "</tr>";
}

echo "</table>";
?>
```

### Wyjaśnienie

- **`echo "<table border='1'>";`** – rozpoczynamy tabelę z obramowaniem.
- **Wiersz nagłówkowy**:
  - Używamy znaczników `<th>` dla nagłówków kolumn.
  - Tworzymy wiersz z trzema nagłówkami: "Kolumna 1", "Kolumna 2", "Kolumna 3".
- **Pętla `for`**:
  - **`for ($wiersz = 1; $wiersz <= 5; $wiersz++)`** – pętla wykona się 5 razy.
  - W każdej iteracji:
    - Otwieramy nowy wiersz `<tr>`.
    - Dodajemy trzy komórki `<td>` z tekstem zawierającym numer wiersza i kolumny.
    - Zamykamy wiersz `</tr>`.
- **`echo "</table>";`** – zamykamy tabelę.

### Wynik

Po uruchomieniu tego kodu zobaczysz tabelę z nagłówkiem i 5 wierszami:

| Kolumna 1            | Kolumna 2            | Kolumna 3            |
|----------------------|----------------------|----------------------|
| Wiersz 1, Kolumna 1  | Wiersz 1, Kolumna 2  | Wiersz 1, Kolumna 3  |
| Wiersz 2, Kolumna 1  | Wiersz 2, Kolumna 2  | Wiersz 2, Kolumna 3  |
| Wiersz 3, Kolumna 1  | Wiersz 3, Kolumna 2  | Wiersz 3, Kolumna 3  |
| Wiersz 4, Kolumna 1  | Wiersz 4, Kolumna 2  | Wiersz 4, Kolumna 3  |
| Wiersz 5, Kolumna 1  | Wiersz 5, Kolumna 2  | Wiersz 5, Kolumna 3  |

---

## Tworzenie Bloków Div za Pomocą Pętli

### Cel

Chcemy stworzyć kilka bloków `div`, które będą wyświetlane obok siebie. Każdy blok będzie miał inny kolor i będzie zawierał tekst.

### Krok po kroku

1. **Użyj pętli `for`** – określ, ile bloków chcesz stworzyć.
2. **Wygeneruj bloki `div`** – w każdej iteracji pętli dodaj nowy blok.
3. **Dodaj style CSS** – aby bloki były widoczne i kolorowe.

### Kod

Oto kod, który to robi:

```php
<?php
for ($i = 1; $i <= 5; $i++) {
    // Generujemy losowy kolor w formacie szesnastkowym
    $kolor = '#' . dechex(rand(0x100000, 0xFFFFFF));

    echo "<div style='
        width: 100px;
        height: 100px;
        background-color: $kolor;
        margin: 10px;
        display: inline-block;
        text-align: center;
        line-height: 100px;
        color: #fff;
        '>
        Blok $i
    </div>";
}
?>
```

### Wyjaśnienie

- **Pętla `for`**:
  - **`for ($i = 1; $i <= 5; $i++)`** – pętla wykona się 5 razy.
- **Generowanie losowego koloru**:
  - **`$kolor = '#' . dechex(rand(0x100000, 0xFFFFFF));`** – tworzymy losowy kolor.
- **Tworzenie bloku `div`**:
  - Ustawiamy styl bloku:
    - **`width: 100px;`** – szerokość 100 pikseli.
    - **`height: 100px;`** – wysokość 100 pikseli.
    - **`background-color: $kolor;`** – tło w losowym kolorze.
    - **Inne style** – margines, wyświetlanie obok siebie, wyśrodkowanie tekstu.
  - **`Blok $i`** – tekst wewnątrz bloku, gdzie `$i` to numer bloku.

### Wynik

Po uruchomieniu kodu zobaczysz 5 kolorowych kwadratów z napisem "Blok 1", "Blok 2", ..., "Blok 5".

---

## Zadania do Samodzielnego Wykonania

### Zadanie 1

**Stwórz tabelę o 10 wierszach i 4 kolumnach.** W każdej komórce umieść tekst: "Komórka X-Y", gdzie X to numer wiersza, a Y to numer kolumny.

**Wskazówki**:

- Użyj zagnieżdżonych pętli `for`.
- Najpierw utwórz wiersz nagłówkowy z 4 kolumnami.
- W pętli zewnętrznej generuj wiersze.
- W pętli wewnętrznej generuj komórki w wierszu.

**Przykład rozpoczęcia**:

```php
<?php
echo "<table border='1'>";

// Wiersz nagłówkowy
echo "<tr>";
for ($kolumna = 1; $kolumna <= 4; $kolumna++) {
    echo "<th>Kolumna $kolumna</th>";
}
echo "</tr>";

// Wiersze tabeli
for ($wiersz = 1; $wiersz <= 10; $wiersz++) {
    echo "<tr>";
    for ($kolumna = 1; $kolumna <= 4; $kolumna++) {
        echo "<td>Komórka $wiersz-$kolumna</td>";
    }
    echo "</tr>";
}

echo "</table>";
?>
```

### Zadanie 2

**Wygeneruj 7 bloków `div`, które będą miały rosnącą szerokość.** Pierwszy blok ma mieć 50 pikseli szerokości, każdy kolejny o 50 pikseli więcej (czyli 50px, 100px, 150px, ...). Każdy blok powinien mieć inny kolor tła i wyświetlać napis "Blok numer Z", gdzie Z to numer bloku.

**Wskazówki**:

- Użyj pętli `for` od 1 do 7.
- Oblicz szerokość jako `$szerokosc = $i * 50;`.
- Generuj losowy kolor tła dla każdego bloku.
- Ustaw style CSS tak, aby bloki były widoczne.

**Przykład rozpoczęcia**:

```php
<?php
for ($i = 1; $i <= 7; $i++) {
    $szerokosc = $i * 50; // Szerokość rośnie o 50px
    $kolor = '#' . dechex(rand(0x100000, 0xFFFFFF));

    echo "<div style='
        width: {$szerokosc}px;
        height: 50px;
        background-color: $kolor;
        margin: 5px;
        text-align: center;
        line-height: 50px;
        color: #fff;
        '>
        Blok numer $i
    </div>";
}
?>
```

---

## Podsumowanie

Gratulacje! Nauczyłeś się, jak za pomocą pętli w PHP tworzyć tabele i bloki `div`. Pętle pozwalają na efektywne generowanie powtarzających się elementów, co jest bardzo przydatne w programowaniu.

### Co dalej?

- Spróbuj zmodyfikować kody, aby lepiej je zrozumieć.
- Eksperymentuj z różnymi wartościami w pętlach.
- Dodaj dodatkowe style CSS, aby ulepszyć wygląd elementów.

---

## Pomoc

Jeśli napotkasz trudności:

- Sprawdź, czy wszystkie znaczniki HTML są poprawnie otwarte i zamknięte.
- Upewnij się, że pętle mają poprawne warunki.
- Pamiętaj o średnikach `;` i nawiasach `{}` w kodzie PHP.

---

## Słowniczek

- **PHP** – język programowania używany do tworzenia dynamicznych stron internetowych.
- **Pętla** – konstrukcja, która pozwala na wielokrotne wykonywanie tego samego kodu.
- **`for`** – rodzaj pętli, która wykonuje się określoną liczbę razy.
- **`echo`** – funkcja w PHP, która wyświetla tekst na stronie.
- **HTML** – język znaczników używany do tworzenia struktury stron internetowych.
- **CSS** – język używany do stylizacji elementów HTML.

---

## Życzę powodzenia!

Nie bój się eksperymentować i zadawać pytań. Im więcej ćwiczysz, tym lepiej zrozumiesz, jak działa programowanie w PHP.
