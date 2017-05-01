
Project Pokemon RawDB
=== 

URL: http://projectpokemon.org/rawdb

Author: Alpha of projectpokemon.org

---

RawDB is a flexible binary reader and parser built primary for Pokémon and other NDS/3DS games. The goal of this is to make development of those games easier and more robust.

History
------
The origin of this project was from a need to use the same components for reading and writing in PPRE as the existing components in AlphaDB. Originally, AlphaDB was going to be used, except that it suffered from shaky data structures that required a lot of rewriting.

The first version of RawDB was just a quick rewrite of AlphaDB. It did not serve very well as an interface for writing data however. More write-able structures were added manually later.

RawDB:Atomic was a version built around the idea that this could become a very powerful binary parser that could accurately reconstruct the odd looking nitro data structures. After a few months of development, this was found to be horrendously slow at parsing despite the stronger read/write structures.

RawDB is again being re-written with the idea that incremental parsing and writing can be done well as long as data is carefully handled and exposed.

Supported Games
---

* diamond
* platinum
* heartgold
* black
* black2

Usage
---
To make use of RawDB, add it to your Python 2 path, or put it in your current working directory. Then it and its components can be imported directly.

To get the most usage out of this, you may wish to use a graphical user interface such as PPRE.

Instructions:

1. Create the directory "local/data/<game>/fs/", where <game> is the lowercase name of a game listed above in Supported Games for every game to use.
2. Copy the nitrofs file system of the desired ROM into the corresponding directory. This means everything inside the "data" directory created by ndstool.
3. Launch `gen.py`:

```
Usage: %s [Options] [Game1 [Game2 [...]]]
If game is left blank, all games will be processed.

Options:
--gen-index         Generate index files.
--ext <extension>   Use <extension> for newly created files.
--help              Show this help, then exit.
```