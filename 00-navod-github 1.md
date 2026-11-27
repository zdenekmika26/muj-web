# 🚀 Návod: GitHub krok za krokem

Tento návod tě provede vším od založení účtu až po web, který běží na internetu. Kroky 1–8 uděláš **jednou** na začátku. Pak už jen upravuješ soubory a ukládáš změny (viz [Každodenní práce](#-každodenní-práce)).

Všechno kromě jednoho kroku naklikáš ve **VS Code**. Terminál použiješ jen jednou, v kroku 3.

**Budeš potřebovat:**
- e-mail, ke kterému máš přístup
- **VS Code**
- **Git** (ve škole je nainstalovaný, doma si ho stáhneš z [git-scm.com](https://git-scm.com/))

---

## 1. Založ si účet na GitHubu

1. Jdi na [github.com/signup](https://github.com/signup).
2. Vyplň e-mail, heslo a **uživatelské jméno**.
   - Uživatelské jméno bude součástí adresy tvého webu (`jmeno.github.io`), tak ho vyber s rozmyslem.
   - Nemusí to být tvoje celé jméno. Bude veřejně vidět.
3. Potvrď e-mail kódem, který ti přijde.

> 💡 Doporučení: GitHub ti později může nabídnout **dvoufázové ověření** (při přihlášení zadáš kromě hesla i kód z mobilu). Účet je pak mnohem bezpečnější, ale pro práci na tomto projektu ho nepotřebuješ.

---

## 2. Vytvoř složku a otevři ji ve VS Code

1. V počítači vytvoř novou **prázdnou** složku a pojmenuj ji **`muj-web`**. Zapamatuj si, kde je.
   - Podle názvu složky se pak pojmenuje i repozitář na GitHubu, a ten se **musí jmenovat přesně `muj-web`**.
2. Složku chyť myší a přetáhni ji na **ikonu VS Code** na ploše. VS Code se otevře rovnou s touto složkou.
   - Jde to i jinak: ve VS Code klikni na **File → Open Folder** a složku vyber.

> ❗ Vždycky otevírej **celou složku**, ne jen jeden soubor. Jinak ti nebude fungovat Source Control.

---

## 3. Řekni Gitu, kdo jsi (jediný krok v terminálu)

Git u každé uložené verze (commitu) zapisuje, kdo ji vytvořil. **Jméno a e-mail musí být vyplněné**, jinak ti Git nedovolí udělat ani jeden commit.

1. Ve VS Code otevři terminál: nahoře **Terminal → New Terminal** (nebo **Ctrl + `**). Dole se objeví okno pro psaní příkazů.
2. Napiš tyto dva příkazy (každý potvrď Enterem), jen místo ukázky dej svoje údaje:
   ```bash
   git config --global user.name "Jan Novák"
   git config --global user.email "jan.novak@email.cz"
   ```
   Jako e-mail použij ten, kterým se přihlašuješ na GitHub.
3. Kontrola, že se to uložilo:
   ```bash
   git config --global --list
   ```
   Měl bys vidět svoje jméno a e-mail.

> 🏠 Tohle musíš udělat na **každém počítači**, kde budeš pracovat (ve škole i doma).

---

## 4. Vytvoř první stránku

1. Ve VS Code vytvoř v levém panelu nový soubor `index.html` a napiš do něj základní strukturu stránky.
2. Ulož (**Ctrl + S**).

Postupně by struktura složky měla vypadat zhruba takto:
```
muj-web/
├── index.html
├── o-nas.html
├── img/
│   └── logo.png
└── media/
    └── trailer.mp4
```

---

## 5. Zapni Git ve složce (inicializace repozitáře)

Tím řekneš Gitu, aby začal tuhle složku hlídat a pamatovat si její verze.

1. Vlevo klikni na ikonu **Source Control** (větvička) nebo stiskni **Ctrl + Shift + G**.
2. Klikni na tlačítko **Initialize Repository**.

Od teď VS Code ukazuje všechny změněné soubory v Source Control. Ze složky se stal **repozitář**.

---

## 6. Ulož první verzi (stage a commit)

Uložení verze má dva kroky: nejdřív vybereš, **které změny** chceš uložit (*stage*), a pak je uložíš jako jednu verzi (*commit*).

### Co znamenají seznamy v Source Control

- **Changes:** soubory, které jsi změnil, ale zatím nejsou vybrané k uložení.
- **Staged Changes:** soubory vybrané k uložení. Do commitu se dostane **jen to, co je tady**.

Písmeno vedle souboru říká, co se s ním stalo:

| Písmeno | Anglicky | Význam |
|---|---|---|
| **U** | Untracked | nový soubor, který Git zatím nehlídá |
| **A** | Added | nový soubor přidaný do Staged Changes |
| **M** | Modified | upravený soubor |
| **D** | Deleted | smazaný soubor |

### Postup

1. **Stage:** najeď myší na soubor v **Changes** a klikni na **+**. Soubor se přesune do **Staged Changes**.
   - Chceš vybrat všechno najednou? Klikni na **+** u nadpisu **Changes**.
   - Spletl ses? U souboru ve **Staged Changes** klikni na **−** a vrátí se zpátky.
2. Do pole **Message** nahoře napiš, co jsi udělal, třeba `Přidána úvodní stránka`.
3. Klikni na **✓ Commit**.

> 💡 Když nic nevybereš a rovnou klikneš na Commit, VS Code se zeptá, jestli má uložit všechny změny. **Yes** = uloží se všechno.

> ❗ Commit ukládá verzi **jen u tebe v počítači**. Na GitHub ji pošleš v dalším kroku.

---

## 7. Pošli repozitář na GitHub (publish)

1. V Source Control klikni na tlačítko **Publish Branch**.
2. VS Code tě požádá o přihlášení ke GitHubu. Klikni na **Allow**, v prohlížeči se přihlas a povol přístup. Pak se vrať do VS Code.
3. Nahoře se objeví nabídka. Vyber **Publish to GitHub public repository**.
   - **Musí být public (veřejný)**, jinak web na GitHub Pages zdarma nepoběží. Pozor, hned pod ním je v nabídce *private*.
   - Název repozitáře se nabídne podle složky. **Musí to být přesně `muj-web`**, případně ho přepiš.
4. Počkej, až se dole vpravo objeví hláška o úspěšném publikování. Kliknutím na **Open on GitHub** si repozitář můžeš rovnou otevřít.

Teď je tvůj projekt na GitHubu a VS Code je s ním propojený.

### Omylem jsem vybral private. Jak to opravit?

Soukromý repozitář nejde zdarma zveřejnit na GitHub Pages. Změníš ho na veřejný takto:

1. Na GitHubu otevři svůj repozitář a klikni na **Settings**.
2. Sjeď úplně dolů do červené části **Danger Zone**.
3. U **Change repository visibility** klikni na **Change visibility** → **Change to public**.
4. Potvrď všechna upozornění (GitHub tě může nechat opsat název repozitáře nebo se znovu přihlásit).

Kontrola: u názvu repozitáře nahoře je teď štítek **Public**.

### Repozitář má špatný název. Jak ho přejmenovat?

Repozitář se musí jmenovat přesně `muj-web`. Přejmenovat ho můžeš kdykoli, historie ani tagy se neztratí.

1. Na GitHubu otevři svůj repozitář a klikni na **Settings**.
2. Hned nahoře v poli **Repository name** přepiš název na `muj-web`.
3. Klikni na **Rename**.

Co se tím změní:
- **Adresa tvého webu se změní** na `https://tvoje-jmeno.github.io/muj-web/`. Stará adresa přestane fungovat, takže novou **pošli vyučujícímu**.
- Ve VS Code nemusíš nic měnit. Sync Changes i Pull fungují dál.
- Složku v počítači přejmenovávat nemusíš.

---

## 8. Zapni GitHub Pages (web na internetu)

1. Na GitHubu otevři svůj repozitář `muj-web`.
2. Klikni na **Settings** → vlevo **Pages**.
3. V části **Build and deployment** nastav:
   - **Source:** Deploy from a branch
   - **Branch:** `main` (nebo `master`, pokud se ti nabízí ten) a složka `/ (root)`
4. Klikni na **Save**.
5. Počkej 1–2 minuty a obnov stránku. Nahoře se objeví adresa tvého webu:
   ```
   https://tvoje-jmeno.github.io/muj-web/
   ```

Tuhle adresu i odkaz na repozitář **pošli vyučujícímu**.

> 💡 Po každém odeslání změn se web na internetu aktualizuje sám, jen to trvá asi minutu.

---

## 🔁 Každodenní práce

Tohle budeš dělat pořád dokola, všechno v Source Control:

1. Uprav soubory a ulož je (**Ctrl + S**).
2. **Stage:** klikni na **+** u souborů, které chceš uložit (nebo u nadpisu **Changes** pro všechny).
3. Napiš zprávu → **✓ Commit**.
4. Klikni na **Sync Changes**. Tím se verze pošle na GitHub (a zároveň se stáhne, co tam je nového).

> 💡 Commituj často a po menších kouscích. Jedna věc = jeden commit (`Přidána tabulka s menu`, `Opravena navigace`).

---

## 🏠 Práce na jiném počítači (třeba doma)

Projekt máš na GitHubu, takže si ho stáhneš kamkoli.

**Poprvé na novém počítači:**
1. Udělej [krok 3](#3-řekni-gitu-kdo-jsi-jediný-krok-v-terminálu) (jméno a e-mail).
2. Ve VS Code stiskni **Ctrl + Shift + P**, napiš `Git: Clone` a potvrď.
3. Vyber **Clone from GitHub**, přihlas se a vyber svůj repozitář `muj-web`.
4. Vyber, kam se má složka uložit, a pak klikni na **Open**.

**Pokaždé, než začneš pracovat:** v Source Control klikni na **⋯** → **Pull**. Stáhneš si tím, co jsi udělal na jiném počítači. Jinak budeš pracovat se starou verzí a při odesílání ti Git ohlásí chybu.

---

## 🏷️ Označení verze tagem (konec milníku)

Na konci milníku označíš poslední commit štítkem (`v1`, `v2`…). Nevzniká tím nový commit, jen se na ten existující „nalepí“ jméno.

1. Ujisti se, že máš vše commitnuté a odeslané (**Sync Changes**).
2. Stiskni **Ctrl + Shift + P**, napiš `Git: Create Tag` a potvrď.
3. Napiš `v1` a potvrď. Popis (message) můžeš nechat prázdný.
4. Znovu **Ctrl + Shift + P**, napiš `Git: Push Tags` a potvrď.

Kontrola: na GitHubu v repozitáři klikni na **Tags**. Měl bys tam vidět `v1`.

---

## 🆘 Něco nefunguje

| Problém | Řešení |
|---|---|
| Commit hlásí *Please tell me who you are* nebo *Make sure you configure your user.name and user.email* | Neudělal jsi [krok 3](#3-řekni-gitu-kdo-jsi-jediný-krok-v-terminálu) na tomto počítači. |
| V Source Control není tlačítko **Initialize Repository** ani seznam souborů | Nemáš otevřenou složku. Přetáhni ji na ikonu VS Code nebo ji otevři přes **File → Open Folder**. |
| Commit nejde, píše *There are no changes to commit* | Uložil jsi soubor (**Ctrl + S**)? Neuložený soubor má v záložce tečku místo křížku. |
| Soubor jsem změnil, ale v commitu na GitHubu chybí | Nebyl ve **Staged Changes**. Přidej ho přes **+** a udělej nový commit. |
| Není vidět tlačítko **Publish Branch** | Nejdřív musíš mít aspoň jeden commit (krok 6). |
| Při odesílání chyba *rejected* / *fetch first* | Klikni na **⋯** → **Pull** a pak znovu **Sync Changes**. |
| V **Settings → Pages** nejde vybrat větev nebo GitHub chce placený účet | Repozitář je **private**. Změň ho na public (viz [krok 7](#omylem-jsem-vybral-private-jak-to-opravit)). |
| Web hlásí **404** | Hlavní stránka se musí jmenovat přesně `index.html`. Po zapnutí Pages počkej pár minut. |
| Obrázek se zobrazí u mě, ale na webu ne | Zkontroluj velká a malá písmena v názvu (`Logo.PNG` ≠ `logo.png`) a že je obrázek commitnutý a odeslaný. |
| Změny nejsou na webu vidět | Dal jsi **Sync Changes**? Pak počkej minutu a obnov stránku (**Ctrl + F5**). |
| Zapomněl jsem heslo | Na přihlašovací stránce GitHubu klikni na **Forgot password?** |

Pokud nic z toho nepomůže, ozvi se vyučujícímu.
