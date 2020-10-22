# Bilder och texturer

## Bilder och texturer

I Raylib skiljer man på _bilder_ och _texturer_.

### Image

En Image är en bild som är sparad i datorns arbetsminne, och kan manipuleras på olika sätt.

```csharp
// Skapar en svart bild som är 200x200 pixlar.
Image emptyImage = Raylib.GenImageColor(200, 200, Color.BLACK);

// Skapar en röd bild som är 200x200 pixlar.
Image emptyImage = Raylib.GenImageColor(200, 200, Color.RED);

// Läser in bilden hero.png och bygger en ny Image baserat på den.
// OBS! bilden måste ligga i samma mapp som exe-filen (eller projektet)!
Image filebasedImage = Raylib.LoadImage(@"hero.png");
```

### ImageDrawPixel

Ändrar färg på en pixel i en Image.

```csharp
// Ändrar pixeln som är 20 pixlar från vänsterkanten och 15 från 
// toppen av bilden till att bli blå
Raylib.ImageDrawPixel(ref targetImage, 20, 15, Color.BLUE);
```

### ImageFlipHorizontal

Flippar en Image horisontellt \(spegelvänder\).

```csharp
Raylib.ImageFlipHorizontal(ref targetImage);
```

### ImageFlipVertical

Flippar en Image vertikalt.

```csharp
Raylib.ImageFlipVertical(ref targetImage);
```

### ImageResize/ImageResizeNN

Ändrar storlek på en bild. NN-versionen ger ett skarpt resultat vilket fungerar bra för pixelart som skalas med jämna multiplikationer.

```csharp
//Ändrar storleken på bilden "someImage" till 400x400 pixlar
Raylib.ImageResize(ref someImage, 400, 400);

//Ändrar storleken på bilden "pixelartImage" till dubbla dess nuvarande storlek
RayLib.ImageResizeNN(ref pixelartImage, pixelartImage * 2, pixelartImage * 2);
```

### Texture

En Texture är en bild som är sparad i grafikkortets minne, och är redo att ritas ut på skärmen. Man kan skapa en Texture utifrån en Image eller läsa in en bildfil från hårddisken direkt. Om man ska använda samma Image i flera olika Textures så kan det vara bra att skapa en Image först, så slipper man läsa in den från hårddisken flera gånger.

```csharp
// Skapar en ny texture baserat på en Image som redan lästs in.
Texture2D heroTexture = Raylib.LoadTextureFromImage(originalImage);

// Läser in en bildfil och skapar en texture direkt från den.
Texture2D goombaTexture = Raylib.LoadTexture(@"goomba.png");
```

Images kan manipuleras mer. Textures kan ritas ut till skärmen.

### DrawTexture

```csharp
// Ritar texturen heroTexture till fönstret, på x-position 40 och 
// y-position 300, utan infärgning (WHITE färgar inte)
Raylib.DrawTexture(heroTexture, 40, 300, Color.WHITE)
```
