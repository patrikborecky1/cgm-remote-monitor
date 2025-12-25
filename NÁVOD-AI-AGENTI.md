# Jak používat AI agenty ve VS Code - Rychlý průvodce

## ✅ Co bylo přidáno

Do projektu Nightscout byly přidány konfigurační soubory pro GitHub Copilot a VS Code, které vám pomohou rychleji psát kód s využitím umělé inteligence.

### Přidané soubory:

1. **`.github/copilot-instructions.md`**
   - Vlastní instrukce pro GitHub Copilot
   - Copilot bude rozumět struktuře projektu Nightscout
   - Automaticky použije správné konvence kódování (comma-first style, 2 mezery, atd.)

2. **`.vscode/settings.json`**
   - Nastavení editoru optimalizované pro Nightscout
   - ESLint integrace
   - Aktivace GitHub Copilot

3. **`.vscode/extensions.json`**
   - Seznam doporučených rozšíření
   - VS Code vám nabídne jejich automatickou instalaci

4. **`.vscode/launch.json`**
   - Přednastavené ladící konfigurace
   - Spouštění dev/prod režimu
   - Spouštění testů

5. **Dokumentace:**
   - `docs/AI-AGENTS-VSCODE.md` - Kompletní průvodce (česky i anglicky)
   - `docs/COPILOT-EXAMPLES.md` - Praktické příklady použití

## 🚀 Jak to zprovoznit (3 kroky)

### Krok 1: Nainstalujte GitHub Copilot ve VS Code

1. Otevřete VS Code
2. Přejděte do Extensions (zkratka: `Ctrl+Shift+X`)
3. Vyhledejte a nainstalujte:
   - **GitHub Copilot**
   - **GitHub Copilot Chat**

### Krok 2: Přihlaste se k GitHub Copilot

1. Po instalaci klikněte na ikonu GitHub Copilot v dolní liště
2. Přihlaste se pomocí GitHub účtu
3. Ujistěte se, že máte aktivní předplatné GitHub Copilot
   - Studenti a open-source contributors: https://education.github.com/
   - Ostatní: https://github.com/features/copilot

### Krok 3: Otevřete projekt ve VS Code

1. Otevřete tento projekt (`cgm-remote-monitor`) ve VS Code
2. VS Code vám nabídne instalaci doporučených rozšíření - klikněte "Install All"
3. Hotovo! 🎉

## 💡 Jak to používat

### Automatické dokončování kódu

Začněte psát a Copilot automaticky navrhne pokračování:

```javascript
// Napište komentář:
// Function to convert mmol/L to mg/dL

// Copilot navrhne:
function mmolToMgdl (mmol) {
  return Math.round(mmol * 18.0182);
}
```

**Klávesové zkratky:**
- `Tab` - přijmout návrh
- `Esc` - odmítnout návrh
- `Alt+]` - další návrh
- `Alt+[` - předchozí návrh

### Chat s AI asistentem

Otevřete Copilot Chat (`Ctrl+Shift+I`) a ptejte se:

- "Jak vytvořit nový plugin pro Nightscout?"
- "Vysvětli tuto funkci" (označte funkci)
- "Napiš testy pro tuto funkci"
- "Oprav tento kód"
- "Refaktoruj podle comma-first style"

### Příklady dotazů v češtině

Copilot rozumí i češtině! Můžete se ptát česky:

```
Vytvořit funkci pro validaci glukózy v rozsahu 40-400 mg/dL
```

```
Jak funguje plugin systém v Nightscout?
```

```
Napiš mocha test pro tuto funkci
```

## 📚 Detailní dokumentace

Pro více informací a praktických příkladů viz:

1. **[docs/AI-AGENTS-VSCODE.md](docs/AI-AGENTS-VSCODE.md)** 
   - Kompletní instalační průvodce
   - Řešení problémů
   - Nastavení VS Code

2. **[docs/COPILOT-EXAMPLES.md](docs/COPILOT-EXAMPLES.md)** ⭐
   - Konkrétní příklady kódu
   - Ukázky vytváření pluginů
   - Příklady testů
   - Tipy pro nejlepší výsledky

## 🎯 Co Copilot umí s touto konfigurací

✅ Zná strukturu projektu Nightscout
✅ Používá správný styl kódu (comma-first, 2 mezery)
✅ Chápe plugin architekturu
✅ Umí vytvářet testy s Mocha a Should.js
✅ Rozumí API endpoints a Express.js
✅ Respektuje bezpečnostní požadavky
✅ Zná MongoDB strukturu (SGV, treatments, devicestatus)

## ❓ Nejčastější otázky

**Q: Musím za GitHub Copilot platit?**
A: Copilot je placený, ale je zdarma pro:
- Studenty (GitHub Education)
- Open-source maintainere
- Můžete si to vyzkoušet zdarma 30 dní

**Q: Funguje to i bez internetu?**
A: Ne, Copilot potřebuje připojení k internetu.

**Q: Copilot nenavrhuje kód?**
A: Zkontrolujte:
1. Jste přihlášeni (ikona v dolní liště)
2. Máte aktivní předplatné
3. Restartujte VS Code

**Q: Copilot nepoužívá správný styl kódu?**
A: 
1. Zkontrolujte, že existuje `.github/copilot-instructions.md`
2. Explicitně se zeptejte: "Follow comma-first style"
3. Po pár příkladech se Copilot přizpůsobí

**Q: Mohu používat Copilot i pro jiné projekty?**
A: Ano! Copilot funguje globálně ve VS Code pro všechny projekty.

## 🔒 Bezpečnost a soukromí

- Copilot posílá části vašeho kódu do cloudu
- Neposílejte do Copilot citlivá data (hesla, API klíče)
- Pro více info: https://docs.github.com/en/copilot/overview-of-github-copilot/about-github-copilot-individual

## 🆘 Potřebujete pomoc?

1. Přečtěte si [docs/AI-AGENTS-VSCODE.md](docs/AI-AGENTS-VSCODE.md)
2. Podívejte se na [příklady použití](docs/COPILOT-EXAMPLES.md)
3. Otevřete issue v tomto repozitáři

## 🎉 Shrnutí

Nyní máte k dispozici AI asistenta, který:
- ⚡ Urychlí psaní kódu
- 🎯 Automaticky použije správné konvence
- 🧪 Pomůže s psaním testů
- 📖 Vysvětlí složitý kód
- 🔧 Pomůže s refactoringem

**Vyzkoušejte to hned!** Otevřete jakýkoliv `.js` soubor a začněte psát komentář...
