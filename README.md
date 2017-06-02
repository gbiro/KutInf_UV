# Oktatási anyagok

## KutInf UV

Ezt a cikket dolgozzuk fel: [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4804329/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4804329/)

A fordítás ideális esetben pl így néz(het) ki:

```bash
cmake ../ -DKVAL=<val> -DPDFMAP=<filename.pdf>
(make plot)
make doc
```

ahol `-D<var>=<val>` kapcsolóval a cmake-nek adunk át változót.

> Motiváció: hogyan változik a fázistér K függvényében?
>
> Érdemes a (0,10] tartományt vizsgálni.

Példák:

![K=0.2](./KutInf_UV/examples/map02.png)
![K=2](./KutInf_UV/examples/map2.png)
![K=5](./KutInf_UV/examples/map5.png)
![K=10](./KutInf_UV/examples/map10.png)

---

### Feladat

A **standard map**-ot az alábbi egyenletpár definiálja:

$ p_{i+1} = p_i - K sin(x_i) $

$ x_{i+1} = x_i + p_{i+1} $

ahol *K* az egyetlen bemenő paraméter, $ p $ és $ x $ értelmezési tartománya pedig $ [0,2\pi] $.

#### Írjunk egy C/C++ programot, ami ezt implementálja, és vizsgáljunk meg néhány *K* értéket!

> Tippek:  
> * a teljes fázistér kiszámításához egy adott kezdeti $ K $ érték mellett $ dx = 0.1 $ lépésközökkel, $ N = 500 $ lépést számoljunk. Minden egyes iterációt írjunk ki egy fájlba, ami majd a `gnuplot` bemenete lesz.
> * a kódot bontsuk legalább header-source párokba, de még jobb, ha a szükséges függvényekből könyvtárat készítünk, amit a main programhoz hozzálinkelünk.
> * cmake-hez "hasznos" parancsok (a teljesség igénye nélkül):
>   * `add_executable`
>   * `add_library`
>   * `target_link_libraries`
>   * `target_include_directories`
>   * `add_latex_document`
>   * `set` illetve `configure_file`
>   * `find_package`
>   * `add_custom_command`, `add_custom_target`
> * ügyeljünk arra, hogy a cmake ne abszolút, hanem relatív útvonalakat kapjon.

#### Az elkészült feladatot, feladatrészeket töltsük fel a `github` repositoryba.