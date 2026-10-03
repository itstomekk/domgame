
# DOMGAME

**Domy, po których można chodzić.** Wybierz chatę i wejdź do środka - w przeglądarce, bez instalowania czegokolwiek.

### → [itstomekk.github.io/domgame](https://itstomekk.github.io/domgame/)

[![RENIKDOM - salon](docs/img/hero.jpg)](https://itstomekk.github.io/domgame/renik/)

---

## Domy

| Dom | Co to jest | Wejście |
|---|---|---|
| **RENIKDOM** | Mieszkanie Michała, Zielone Alejki, Marki. Ok. 75 m² + antresola, sufit jednospadowy do 5 m. Projekt wnętrza: mgr inż. arch. Katarzyna Radziwonka | [**Wejdź →**](https://itstomekk.github.io/domgame/renik/) |
| *następny dom* | w budowie | - |

Każdy dom to osobny katalog: `index.html` (lobby) + katalog domu (`renik/`) z własnymi teksturami, modelami, zdjęciami i rzutami. Silnik jest jeden, wystrój jest osobny.

## Co jest w środku

- **Spacer w pierwszej osobie** po całym mieszkaniu, z kolizjami: ściany, meble, drzwi, antresola.
- **Makieta** - całe mieszkanie widziane z góry, jak dom dla lalek (przekrój przez ściany).
- **Pory dnia** - zachód, noc, dzień. Włącznik światła w przedpokoju (albo klawisz `E` obok niego).
- **Zdjęcia 360°** - dla każdego pomieszczenia panorama do rozglądania się w środku.
- **Widok realistyczny** - przełącznik między modelem 3D a zdjęciem tego samego kadru.
- **Rzuty architekta** - 9 arkuszy w oryginale: układ ścian, aranżacja, gniazda, sufity, posadzki, wykończenia, rozwinięcia kuchni i łazienki, zmiany deweloperskie.
- **30 misji** w trzech grupach (pokoje, przełączniki, odkrycia), z zapisem postępu w przeglądarce. Na końcu finał.
- **Akcje przy sprzętach** - klawisz `E` przy sedesie (spuść wodę), łóżku (pościel), popielniczce i biurku (posprzątaj fajki), prysznicu (odkręć), na balkonie sypialni (posłuchaj gołębia).
- **Okolica: wł./wył.** - odgłosy miasta i podwórka za oknem, do wyłączenia jednym kliknięciem.
- **Antresola i drabinka** - wejście po drabince klawiszem `E`.
- **Skakanie po meblach** - spacja. Można wskoczyć na sofę, stół, parapet.
- **Kot** - chodzi po mieszkaniu. Spacja obok kota kopie kota.
- **Muzyka** - pięć trybów: wył., dworska, disco polo, french touch i RAVE, który sam się włącza przy konsoli DJ.
- **14 kolorów ścian** do przeklikiwania.
- **Jakość: pełna / niska** - dla słabszych komputerów.

## Galeria

|||
|---|---|
| ![Makieta](docs/img/makieta.jpg) **Makieta** - całe mieszkanie z góry | ![Kuchnia](docs/img/kuchnia.jpg) **Kuchnia** - zielone fronty, marmur, stół dla sześciu |
| ![Salon](docs/img/salon.jpg) **Salon** - sofa, dywan, witryna z lego | ![Sypialnia](docs/img/sypialnia.jpg) **Sypialnia** - zielona ściana za łóżkiem |
| ![Gabinet](docs/img/gabinet.jpg) **Gabinet** - biurko z siedmioma monitorami | ![Antresola](docs/img/antresola.jpg) **Antresola** - nad przedpokojem, widok na salon |
| ![Oto Król](docs/img/oto-krol.jpg) **Ściana Króla** - projekcja na ekranie | ![DJ](docs/img/dj.jpg) **Ściana DJ-a** - mural i konsola |

Widok realistyczny, obok modelu 3D tego samego pomieszczenia:

|||
|---|---|
| ![Model 3D](docs/img/salon.jpg) **Model 3D** | ![Widok realistyczny](docs/img/widok-realistyczny.jpg) **Widok realistyczny** |

Interface i tryby:

|||
|---|---|
| ![Lobby](docs/img/lobby.jpg) **Lobby** - wybór domu | ![Intro](docs/img/intro.jpg) **Intro** - animacja powitalna z dźwiękiem |
| ![Misje](docs/img/misje.jpg) **Misje** - 30 zadań w trzech grupach | ![Rzuty](docs/img/rzuty.jpg) **Rzuty** - arkusze architekta w oryginale |
| ![Noc](docs/img/noc.jpg) **Noc** - Warszawa za oknem | ![Zdjęcie 360°](docs/img/zdjecie-360.jpg) **Zdjęcie 360°** - panorama pomieszczenia |
| ![Przedpokój](docs/img/przedpokoj.jpg) **Przedpokój** - drzwi wejściowe, włącznik światła | ![Łazienka](docs/img/lazienka.jpg) **Łazienka** - prysznic, umywalka, lustro |

## Sterowanie

| Wejście | Akcja |
|---|---|
| mysz (przeciągnij) | rozglądanie się |
| `W` `A` `S` `D` albo strzałki | chodzenie, strzałki w lewo/prawo obracają |
| spacja | skok (na meble też) |
| `E` | drabinka na antresolę, włącznik światła, akcje przy sprzętach (spłuczka, łóżko, fajki, prysznic, gołąb) |
| kółko myszy | kąt widzenia (w makiecie: przybliżenie) |
| przyciski na dole | pokoje, makieta, zdjęcie 360°, widok realistyczny, rzuty, kolor ścian, jakość, okolica, muzyka |
| mapa w prawym górnym rogu | kliknięcie przenosi w to miejsce |

## Jak to jest zrobione

- **three.js r128** z CDN, `GLTFLoader` i `Reflector`. Bez frameworka, bez budowania, bez `npm`.
- Jeden `index.html` na dom - cały kod sceny, UI, misji i dźwięku (WebAudio) siedzi w nim.
- Geometria z rzutów architekta: arkusze 1:50 rozrysowane przy 110 dpi, **87.2 px = 1 m**. Sufit jednospadowy: 2.40 m + 0.37 m na metr.
- Meble: **Poly Haven (CC0)**. Pliki `renik/mdl/*.wasm` to modele GLB pod zmienioną nazwą - tak je zapisał pipeline, przeglądarka czyta je normalnie.
- Tekstury i murale w `renik/tex/`, zdjęcia w `renik/photos/`, rysunki architekta w `renik/plans/`.
- Hosting: **GitHub Pages**, gałąź `main`, katalog główny. `.nojekyll` wyłącza przetwarzanie przez Jekyll.

Screenshoty w tym README to zrzuty z tej wersji, zrobione headless Chromium (SwiftShader) na stronie serwowanej lokalnie.

## Uruchom u siebie

```
git clone https://github.com/itstomekk/domgame
cd domgame
python -m http.server 8000
```

Potem [http://localhost:8000](http://localhost:8000). Otwieranie `index.html` prosto z dysku nie zadziała - modele i tekstury ładują się przez `fetch`.

## Aktualizacja strony

Źródło treści siedzi u Michała w `walkthrough/domgame-site/`. Kopia robocza, z której idzie publikacja, jest w `C:\Users\Lenovo\Hermes\projects\domgame`. Po każdej zmianie:

```
cp -a "<źródło>/domgame-site/." "C:/Users/Lenovo/Hermes/projects/domgame/"
cd /c/Users/Lenovo/Hermes/projects/domgame
git add -A && git commit -m "domgame: update" && git push
```

Pages przebuduje się samo w 1-3 minuty. Status: `gh api repos/itstomekk/domgame/pages/builds/latest --jq .status`.

## Kredyty

- kod i strona: **TomekK** ([x.com/itstomekk](https://x.com/itstomekk))
- projekt wnętrza: **mgr inż. arch. Katarzyna Radziwonka**
- modele mebli: **Poly Haven** (CC0)
- rzuty i zdjęcia: **Michał Renik**

---

### English

DOMGAME is a browser-based 3D walkthrough of real flats, built from the architect's drawings. No build step, no plugins - plain three.js r128 and GitHub Pages. Currently one house: **RENIKDOM** (Michał's flat in Marki, Poland), with first-person movement, a dollhouse view, 360° photos, day/night lighting, 25 in-browser missions and the architect's original plan sheets. Play it at [itstomekk.github.io/domgame](https://itstomekk.github.io/domgame/).
