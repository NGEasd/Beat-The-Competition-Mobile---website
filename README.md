# Közzététel és bekötés

1. Másold a négy HTML-fájlt és a `.nojekyll` fájlt a meglévő GitHub Pages oldalad publikált könyvtárába. A meglévő adattörlési `index.html` fájlodat ne írd felül. Ezek statikus oldalak, nincs szükség szerverre, külső betűkészletre vagy analitikára.
2. Nyisd meg a közzétett `terms-en.html`, `privacy-en.html`, `terms-hu.html`, `privacy-hu.html` oldalakat. Ellenőrizd a dátumokat és a szöveget. A dátumot tényleges kiadáskor szükség esetén mindkét nyelven frissítsd.
3. A játék `godot/legal/links.cfg` fájljában a `terms_url` és `privacy_url` helyére másold a teljes HTTPS-címeket. Az `example.invalid` helyőrzőkkel a játék nem mutat webes gombot; a teljes szöveg offline akkor is olvasható.
4. A változásokhoz új kliensbuild szükséges. Backend-deploy vagy adatbázis-migráció ehhez nem kell.

## Dokumentumfrissítés

A forrásszövegek a `docs/TERMS-OF-USE-HU-DRAFT.md`, `docs/TERMS-OF-USE-EN.md`, `docs/PRIVACY-POLICY-HU-DRAFT.md`, `docs/PRIVACY-POLICY-EN.md` fájlok. A HU fájlnevek kompatibilitásból maradtak meg.

Módosítás után futtasd: `python scripts/build-legal-pages.py`. Ez frissíti az itteni HTML-oldalakat és a játék négy offline szövegét. A build nem fordít: mindkét nyelv tartalmát szerkeszteni kell.

Ha új elfogadás szükséges, változtasd meg a `LegalVersion` értékét a `godot/scripts/Main.Legal.cs` fájlban is. A verzió és UTC-időpont helyileg kerül mentésre; nem fiókhoz kötött, szerveroldali bizonyíték. Új telepítés/adattörlés után újra kérjük.

## Éles kiadás

- A meghirdetett bétaadat-visszaállítást külön kell végrehajtani. Ez a módosítás nem töröl adatbázist.
- Utána `beta=false` a `links.cfg` fájlban; az elfogadási verzió automatikusan különbözik a bétától, ezért új elfogadás szükséges.
- Frissítsd a dátumokat, verziót és a már lezárult bétára vonatkozó szöveget mindkét nyelven; generáld újra és publikáld a lapokat.
- A szolgáltatási és dokumentum-URL-eket ellenőrizd az éles kiadásnál.

## Korlátok

Az életkori/szülői nyilatkozat nem személyazonosság-ellenőrzés és nem igazolja önmagában a szülő tényleges elfogadását. Az adatvédelmi tájékoztató megismerése nem GDPR-hozzájárulás. A dokumentumok technikai bekötése nem helyettesít jogi felülvizsgálatot.
