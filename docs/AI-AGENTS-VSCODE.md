# Použití AI Agentů v VS Code / Using AI Agents in VS Code

Tento projekt nyní obsahuje konfiguraci pro GitHub Copilot a další AI nástroje ve VS Code.

---

This project now includes configuration for GitHub Copilot and other AI tools in VS Code.

## Co bylo přidáno / What Was Added

### 1. GitHub Copilot Instructions (`.github/copilot-instructions.md`)
Tento soubor obsahuje vlastní instrukce pro GitHub Copilot, které mu pomohou lépe porozumět struktuře projektu, konvencím kódu a nejlepším praktikám specifickým pro Nightscout.

---

This file contains custom instructions for GitHub Copilot to help it better understand the project structure, code conventions, and best practices specific to Nightscout.

### 2. VS Code Settings (`.vscode/settings.json`)
Konfigurace VS Code optimalizovaná pro tento projekt:
- Odsazení 2 mezerami
- Single quotes pro JavaScript
- ESLint integrace
- GitHub Copilot enabled
- Mocha test runner konfigurace

---

VS Code configuration optimized for this project:
- 2-space indentation
- Single quotes for JavaScript
- ESLint integration
- GitHub Copilot enabled
- Mocha test runner configuration

### 3. Recommended Extensions (`.vscode/extensions.json`)
Seznam doporučených rozšíření pro VS Code, která usnadní vývoj.

---

List of recommended VS Code extensions to facilitate development.

### 4. Debug Configurations (`.vscode/launch.json`)
Předpřipravené ladící konfigurace pro:
- Spuštění aplikace v dev režimu
- Spuštění aplikace v produkčním režimu
- Spuštění testů
- Spuštění aktuálního testovacího souboru

---

Pre-configured debug configurations for:
- Running the app in dev mode
- Running the app in production mode
- Running tests
- Running the current test file

## Jak to nainstalovat / How to Install

### 1. Instalace GitHub Copilot v VS Code

1. Otevřete VS Code
2. Přejděte do Extensions (Ctrl+Shift+X nebo Cmd+Shift+X na Mac)
3. Vyhledejte "GitHub Copilot"
4. Nainstalujte následující rozšíření:
   - **GitHub Copilot** - hlavní rozšíření pro AI dokončování kódu
   - **GitHub Copilot Chat** - chatovací rozhraní pro konverzaci s AI

---

1. Open VS Code
2. Go to Extensions (Ctrl+Shift+X or Cmd+Shift+X on Mac)
3. Search for "GitHub Copilot"
4. Install the following extensions:
   - **GitHub Copilot** - main extension for AI code completion
   - **GitHub Copilot Chat** - chat interface for conversing with AI

### 2. Přihlášení k GitHub Copilot / Sign in to GitHub Copilot

1. Po instalaci klikněte na ikonu GitHub Copilot v dolní liště VS Code
2. Přihlaste se pomocí GitHub účtu
3. Ujistěte se, že máte aktivní GitHub Copilot předplatné

---

1. After installation, click on the GitHub Copilot icon in the VS Code status bar
2. Sign in with your GitHub account
3. Make sure you have an active GitHub Copilot subscription

### 3. Instalace dalších doporučených rozšíření / Install Other Recommended Extensions

Když poprvé otevřete projekt ve VS Code, měla by se vám zobrazit notifikace s nabídkou instalace doporučených rozšíření. Klikněte na "Install All" pro instalaci všech najednou.

Nebo můžete nainstalovat jednotlivá rozšíření ručně:
- ESLint
- npm IntelliSense
- MongoDB for VS Code
- Mocha Test Adapter

---

When you first open the project in VS Code, you should see a notification offering to install recommended extensions. Click "Install All" to install them all at once.

Or you can install individual extensions manually:
- ESLint
- npm IntelliSense
- MongoDB for VS Code
- Mocha Test Adapter

## Jak používat GitHub Copilot / How to Use GitHub Copilot

### Automatické dokončování kódu / Automatic Code Completion

Copilot automaticky navrhuje kód při psaní:
1. Začněte psát funkci nebo komentář
2. Copilot zobrazí šedý text s návrhem
3. Stiskněte `Tab` pro přijetí návrhu
4. Stiskněte `Alt+]` (Windows/Linux) nebo `Option+]` (Mac) pro další návrhy

---

Copilot automatically suggests code as you type:
1. Start typing a function or comment
2. Copilot will show gray text with a suggestion
3. Press `Tab` to accept the suggestion
4. Press `Alt+]` (Windows/Linux) or `Option+]` (Mac) for alternative suggestions

### GitHub Copilot Chat

Otevřete Copilot Chat:
- Stiskněte `Ctrl+Shift+I` (Windows/Linux) nebo `Cmd+Shift+I` (Mac)
- Nebo klikněte na ikonu chatu v postranním panelu

Můžete se ptát například:
- "Jak vytvořit nový plugin pro Nightscout?"
- "Explain this function" (pro vysvětlení vybrané funkce)
- "Fix this code" (pro opravu vybraného kódu)
- "Write tests for this function" (pro vytvoření testů)

---

Open Copilot Chat:
- Press `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Shift+I` (Mac)
- Or click on the chat icon in the sidebar

You can ask questions like:
- "How do I create a new plugin for Nightscout?"
- "Explain this function" (to explain selected function)
- "Fix this code" (to fix selected code)
- "Write tests for this function" (to create tests)

### Copilot rozumí kontextu projektu / Copilot Understands Project Context

Díky souboru `.github/copilot-instructions.md` Copilot automaticky zná:
- Strukturu projektu Nightscout
- Konvence kódování (2 mezery, single quotes, comma-first style)
- Plugin architekturu
- Testovací vzory
- API dokumentaci
- Bezpečnostní opatření

---

Thanks to the `.github/copilot-instructions.md` file, Copilot automatically knows:
- Nightscout project structure
- Coding conventions (2 spaces, single quotes, comma-first style)
- Plugin architecture
- Testing patterns
- API documentation
- Security considerations

## Příklady použití / Usage Examples

### 1. Vytvoření nového pluginu / Creating a New Plugin

Napište komentář:
```javascript
// Create a new plugin that monitors battery level and sends alerts
```

Copilot navrhne strukturu pluginu podle konvencí projektu.

---

Write a comment:
```javascript
// Create a new plugin that monitors battery level and sends alerts
```

Copilot will suggest plugin structure following project conventions.

### 2. Psaní testů / Writing Tests

Vyberte funkci a zeptejte se v Copilot Chat:
```
Write mocha tests for this function using should.js assertions
```

---

Select a function and ask in Copilot Chat:
```
Write mocha tests for this function using should.js assertions
```

### 3. Refaktoring / Refactoring

Vyberte kód a zeptejte se:
```
Refactor this code to follow comma-first style
```

---

Select code and ask:
```
Refactor this code to follow comma-first style
```

### 4. Vysvětlení složitého kódu / Explaining Complex Code

Vyberte složitý kód a použijte příkaz:
```
/explain
```

---

Select complex code and use command:
```
/explain
```

## Nastavení úrovně asistence / Adjusting Assistance Level

V `settings.json` můžete upravit, jak agresivní má být Copilot:

```json
{
  "github.copilot.enable": {
    "*": true,
    "javascript": true
  }
}
```

Pro vypnutí v určitých souborech:
```json
{
  "github.copilot.enable": {
    "*": true,
    "plaintext": false
  }
}
```

---

In `settings.json` you can adjust how aggressive Copilot should be:

```json
{
  "github.copilot.enable": {
    "*": true,
    "javascript": true
  }
}
```

To disable in certain files:
```json
{
  "github.copilot.enable": {
    "*": true,
    "plaintext": false
  }
}
```

## Časté problémy / Troubleshooting

### Copilot nefunguje / Copilot Not Working

1. Zkontrolujte, že jste přihlášeni (ikona v dolní liště)
2. Zkontrolujte, že máte aktivní předplatné
3. Restartujte VS Code
4. Zkontrolujte output panel: View > Output > GitHub Copilot

---

1. Check that you're signed in (icon in status bar)
2. Check that you have an active subscription
3. Restart VS Code
4. Check output panel: View > Output > GitHub Copilot

### Copilot nerespektuje konvence projektu / Copilot Not Respecting Project Conventions

1. Ujistěte se, že soubor `.github/copilot-instructions.md` existuje
2. Zkuste se zeptat explicitně: "Follow the project's comma-first style"
3. Copilot potřebuje několik příkladů, aby se naučil vzory

---

1. Make sure `.github/copilot-instructions.md` file exists
2. Try asking explicitly: "Follow the project's comma-first style"
3. Copilot needs a few examples to learn patterns

## Ověření instalace / Verifying Installation

Po instalaci můžete ověřit, že vše funguje správně:

### Kontrola souborů / File Check
Ujistěte se, že existují následující soubory:
```
✓ .github/copilot-instructions.md
✓ .vscode/settings.json
✓ .vscode/extensions.json
✓ .vscode/launch.json
```

### Kontrola Copilot / Copilot Check
1. Otevřete jakýkoliv `.js` soubor v projektu
2. Začněte psát komentář `// Create a function that`
3. Copilot by měl nabídnout dokončení kódu
4. Pokud vidíte šedý text s návrhem, Copilot funguje! ✓

### Kontrola nastavení / Settings Check
1. Otevřete VS Code nastavení (Ctrl+, nebo Cmd+,)
2. Vyhledejte "tab size"
3. Mělo by být nastaveno na 2 (z projektu)
4. Vyhledejte "quote style"
5. Mělo by být nastaveno na "single"

---

After installation, you can verify everything works correctly:

### File Check
Make sure the following files exist:
```
✓ .github/copilot-instructions.md
✓ .vscode/settings.json
✓ .vscode/extensions.json
✓ .vscode/launch.json
```

### Copilot Check
1. Open any `.js` file in the project
2. Start typing a comment `// Create a function that`
3. Copilot should offer code completion
4. If you see gray text with suggestions, Copilot is working! ✓

### Settings Check
1. Open VS Code settings (Ctrl+, or Cmd+,)
2. Search for "tab size"
3. Should be set to 2 (from project)
4. Search for "quote style"
5. Should be set to "single"

## Další zdroje / Additional Resources

- [Příklady použití Copilot / Copilot Usage Examples](./COPILOT-EXAMPLES.md) ⭐ **Začněte zde!** / **Start here!**
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [VS Code GitHub Copilot Extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [Nightscout Contributing Guide](../CONTRIBUTING.md)
- [Nightscout README](../README.md)

## Podpora / Support

Pokud máte problémy s konfigurací, otevřete issue v tomto repozitáři.

---

If you have issues with the configuration, open an issue in this repository.
