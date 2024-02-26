# Konsolen (Console)

## Skriva text

### Console.WriteLine()

Skriver ut något till konsollen.

```csharp
Console.WriteLine("Hello!");
```

### Console.ReadLine()

Läser in en string från användaren och väntar på Enter-tryckning. Returnerar stringen så att den kan lagras i en variabel eller användas i koden.

```csharp
string answer = Console.ReadLine();
```

### Console.OutputEncoding

Ändrar vilken teckenkodning som ska användas när saker skrivs ut till konsolen.

```csharp
Console.OutputEncoding = System.Text.Encoding.UTF8;
```

Med UTF-8 som teckenkodning kan man använda fler tecken – till exempel emojis som 🤖.

```csharp
Console.WriteLine("🤖");
```

### Console.Clear()

Rensar skärmen.

```csharp
Console.Clear();
```

## Färg

### Console.ForegroundColor

Variabel vars värde avgör färgen på texten i konsollfönstret.

```csharp
Console.ForegroundColor = ConsoleColor.Cyan;
```

{% hint style="warning" %}
**OBSERVERA:** detta gäller enbart text som skrivs _efter_ det att färgen ändrats. Text som redan skrivits ut förändras inte.
{% endhint %}

### Console.BackgroundColor

Variabel vars värde avgör färgen på texten i konsollfönstret.

```csharp
Console.BackgroundColor = ConsoleColor.Magenta;
```

{% hint style="warning" %}
**OBSERVERA:** detta gäller enbart text som skrivs efter det att färgen ändrats. Text som redan skrivits ut förändras inte.
{% endhint %}

### ANSI-färger

ANSI är en gammal textstandard, med koder som fortfarande kan användas för att formatera text i konsollen. Man börjar varje kommando med `\x1b[`, följt av en siffra och sedan `m`. [En komplett lista finns här](https://gist.github.com/raghav4/48716264a0f426cf95e4342c21ada8e7).

I exemplet nedan används alltså `\x1b[34m` för att aktivera blå färg, och sedan används `\x1b[0m` för att återgå till normal färg.

```csharp
Console.WriteLine("\x1b[34mBlå\x1b[0m färg");
```

## Fönstret

### Console.Title

Ändrar konsollfönstrets namn.

```csharp
Console.Title = "Mitt fina fönster";
```

## Console.Beep()

Gör ett ljud!

```csharp
Console.Beep(294,1000) // 1 sekunds (1000 millisekunders) beep i D.
```

## Pekaren

### Console.SetCursorPosition()

Bestäm pekarens position i x- och y-led. Tar emot två int-värden.

```csharp
Console.SetCursorPosition(20, 10); // Plancera pekaren på column 20, rad 10
```

{% hint style="warning" %}
**OBSERVERA:** y-axeln är **omvänd**! Med andra ord, den första raden är 0, den andra är 1, den tredje är 2… Och "origo" ligger uppe i vänstra hörnet.
{% endhint %}

### Console.GetCursorPosition()

Läs av pekarens position i x- och y-led. Returnerar en [tuple ](datatyper/tuples.md)där det första värdet är x, det andra y.

```csharp
(int x, int y) = Console.GetCursorPosition();
```

### Console.CursorLeft

Pekarens position i x-led, räknat från fönstrets vänstra kant (den första "kolumnen" är 0)

```csharp
Console.CursorLeft = 20; // Placera pekaren i kolumn 20
Console.CursorLeft -= 5; // Flytta pekaren fem steg åt vänster
```

### Console.CursorTop

Pekarens position i y-led, räknat från fönstrets överdel.

```csharp
Console.CursorTop = 10; // Placera pekaren på rad 10
Console.CursorTop-- // Flytta pekaren 1 rad uppåt
```

