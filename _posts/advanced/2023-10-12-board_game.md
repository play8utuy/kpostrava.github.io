---
layout: post
title:  "Board game"
---
# Board game

Nejprve se [připojte do Lorem Ipsum týmu](https://replit.com/teams/join/xvtsjzaadrqmanaknpncvlanyelasxgw-lorem-ipsum-team) na Repl.it, kde by jste měli nalézt HTML5 verzi programu, který se nazývá "BoardGame (1)". 

## Popis programu
Základem celé aplikace je dvourozměrné pole `game_board` (10x10). K jednomu prvku pole přistoupíme s pomocí dvou hranatých závorek. Tzn. například:
```JavaScript
game_board[1][0] = 10
```
uloží na první řádek a nultý sloupec hodnotu 10. Jednotlivé políčka v `game_board` jsou nastavená na hodnotu nula nebo jedna. Hodnota jedna má vyjadřovat, že na dané pozici nachází překážka.

Dále se v programu nachází proměnné `x` a `y`, které uchovávají pozici hráče. Hráč je ovládán šipkami a posun v poli je implementován ve funkci `moveCircle`. 

## Úkoly

U této verze zkuste následující úkoly:
- Ošetřete v metodě `moveCircle` pohyb hráče tak, aby nemohl vstoupit na pole s překážkou (tzn. `game_board` je na dané pozici nastaven na jedna)
- Změňte obrázek překážky z modrého čtverce na nějaký obrázek (např. stěna)
- Změňte obrázek hráče z červeného kruhu na nějaký obrázek (např. auto, osoba zvrchu)
- Přidejte do `game_board` novou hodnotu 2, která bude reprezentovat nějakou odměnu, kterou chceme sebrat. Upravte `createBoard()` funkci, aby se odměny zobrazovaly v HTML.
- Napište do `moveCircle` logiku, která bude kontrolovat, zda-li hráč nevstoupil na pole s odměnou. Pokud vstoupí na pole s odměnou provede následující:
  1. Zvýší skóre hráče.
  2. Odstraní odměnu z `game_board`. Tzn. nastaví dané pole na 0 a v HTML odebere obrázek odměny.


# NPC
Nyní zkusíme do našeho programu přidat NPC (non-playable character), který bude hráče pronásledovat. K tomu potřebujeme několik změn v našem programu:
1. Proměnné, které budou udávat pozici NPC v programu.
2. Funkci, která se bude spouštět v pravidelných intervalech a která bude posunovat pozici NPC.
3. Funkci, která bude schopna v našem `game_board` nalézt nejkratší cestu od hráče k NPC.

## Spouštění v pravidelných intervalech

Vytvořte si funkci `posunNPC`, kde bude docházet k posunu NPC a také se bude kontrolovat, zda-li NPC není na stejném poli s hráčem. Tato funkce se bude v JavaScriptu volat spomocí funkce `setInterval`. Takže to bude vypadat nějak takto:
```JavaScript
function posunNPC() { 
  // dopiště vlastní logiku
  console.log("Function executed every second."); 
} 
setInterval(myFunction, 1000); // spouštěno každou sekundu
```

## Hledání nejkratší cesty
Pro hledání nejkratší cesty využijeme algoritmus breath first search (BFS). Názorné vysvětlení algoritmu je možné vidět třeba [zde](https://www.youtube.com/watch?v=T_m27bhVQQQ&t=131s).