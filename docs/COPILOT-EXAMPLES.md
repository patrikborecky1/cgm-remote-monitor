# Příklady použití GitHub Copilot / GitHub Copilot Usage Examples

Tento soubor obsahuje praktické příklady, jak používat GitHub Copilot s konfigurací pro Nightscout projekt.

---

This file contains practical examples of using GitHub Copilot with Nightscout project configuration.

## Příklad 1: Vytvoření nové funkce / Example 1: Creating a New Function

### Vstup / Input:
Napište komentář / Type a comment:
```javascript
// Function to convert mmol/L to mg/dL for glucose values
```

### Očekávaný výstup Copilot / Expected Copilot Output:
```javascript
// Function to convert mmol/L to mg/dL for glucose values
function mmolToMgdl (mmol) {
  return Math.round(mmol * 18.0182);
}
```

✓ Copilot rozumí, že funkce má:
- Správné pojmenování (camelCase)
- Mezeru před parametry
- Vracet zaokrouhlenou hodnotu

---

✓ Copilot understands the function should have:
- Proper naming (camelCase)
- Space before parameters
- Return rounded value

## Příklad 2: Vytvoření objektu s daty / Example 2: Creating Data Object

### Vstup / Input:
```javascript
// Create SGV data object with glucose value, timestamp and direction
var sgvData =
```

### Očekávaný výstup Copilot / Expected Copilot Output:
```javascript
// Create SGV data object with glucose value, timestamp and direction
var sgvData = {
  mgdl: 120
  , mills: Date.now()
  , direction: 'Flat'
  , type: 'sgv'
};
```

✓ Všimněte si comma-first style!
✓ Copilot automaticky použil konvence projektu

---

✓ Notice the comma-first style!
✓ Copilot automatically used project conventions

## Příklad 3: Vytvoření testu / Example 3: Creating a Test

### Vstup / Input:
V Copilot Chat napište / In Copilot Chat type:
```
Write a mocha test for a function that validates glucose values are within safe range (40-400 mg/dL)
```

### Očekávaný výstup Copilot / Expected Copilot Output:
```javascript
'use strict';

require('should');

describe('Glucose Validation', function () {
  
  function isGlucoseInSafeRange (mgdl) {
    return mgdl >= 40 && mgdl <= 400;
  }

  it('should return true for glucose value in safe range', function (done) {
    isGlucoseInSafeRange(120).should.equal(true);
    done();
  });

  it('should return false for glucose value below safe range', function (done) {
    isGlucoseInSafeRange(30).should.equal(false);
    done();
  });

  it('should return false for glucose value above safe range', function (done) {
    isGlucoseInSafeRange(450).should.equal(false);
    done();
  });

});
```

✓ Test používá should.js
✓ Struktura odpovídá existujícím testům v projektu
✓ Používá správný styl s 2 mezerami

---

✓ Test uses should.js
✓ Structure matches existing tests in project
✓ Uses correct style with 2 spaces

## Příklad 4: Plugin struktura / Example 4: Plugin Structure

### Vstup / Input:
```javascript
// Create a basic Nightscout plugin for monitoring pump battery
function init (ctx) {
```

### Očekávaný výstup Copilot / Expected Copilot Output:
```javascript
// Create a basic Nightscout plugin for monitoring pump battery
function init (ctx) {
  var pumpbattery = {
    name: 'pumpbattery'
    , label: 'Pump Battery'
    , pluginType: 'pill-status'
  };

  pumpbattery.setProperties = function setProperties (sbx) {
    sbx.offerProperty('pumpbattery', function setPumpBattery ( ) {
      var data = sbx.data.devicestatus;
      if (data && data.length > 0) {
        return data[0].pump && data[0].pump.battery;
      }
      return null;
    });
  };

  pumpbattery.updateVisualisation = function updateVisualisation (sbx) {
    var battery = sbx.properties.pumpbattery;
    if (battery) {
      var info = { label: 'Pump Battery', value: battery + '%' };
      sbx.pluginBase.updatePillText(pumpbattery, info);
    }
  };

  return pumpbattery;
}

module.exports = init;
```

✓ Copilot zná strukturu pluginů Nightscout
✓ Používá comma-first style
✓ Správně pojmenovává callback funkce
✓ Respektuje plugin API

---

✓ Copilot knows Nightscout plugin structure
✓ Uses comma-first style
✓ Properly names callback functions
✓ Respects plugin API

## Příklad 5: API endpoint / Example 5: API Endpoint

### Vstup / Input:
V Copilot Chat:
```
Create an Express.js endpoint that returns the latest glucose reading from MongoDB
```

### Očekávaný výstup / Expected Output:
```javascript
function configure (app, wares, ctx, env) {
  app.get('/api/v1/glucose/latest', ctx.authorization.isPermitted('api:glucose:read'), function getLatestGlucose (req, res) {
    ctx.entries.list({ count: 1 }, function afterList (err, records) {
      if (err) {
        res.status(500).json({ error: err.message });
        return;
      }
      
      if (records && records.length > 0) {
        var latest = {
          sgv: records[0].sgv
          , mills: records[0].mills
          , direction: records[0].direction
        };
        res.json(latest);
      } else {
        res.status(404).json({ error: 'No glucose data found' });
      }
    });
  });
}
```

✓ Používá autorizaci
✓ Správné error handling
✓ Pojmenované callback funkce
✓ Comma-first style pro objekty

---

✓ Uses authorization
✓ Proper error handling
✓ Named callback functions
✓ Comma-first style for objects

## Tipy pro nejlepší výsledky / Tips for Best Results

### 1. Buďte konkrétní / Be Specific
❌ Špatně / Bad: "create function"
✓ Dobře / Good: "create function to validate SGV glucose values using Nightscout units"

### 2. Používejte terminologii projektu / Use Project Terminology
✓ SGV (Sensor Glucose Values)
✓ treatments, devicestatus, entries
✓ ctx (context), sbx (sandbox)
✓ plugins, middleware

### 3. Požadujte testy / Request Tests
"Write this with tests" nebo "Include mocha tests"

### 4. Odkažte na styl / Reference Style
"Follow the project's comma-first style"
"Use 2-space indentation"

### 5. Ptejte se na vysvětlení / Ask for Explanations
V Copilot Chat:
- "/explain" pro vysvětlení vybraného kódu
- "Why does this use comma-first style?"
- "How does the Nightscout plugin system work?"

## Poznámky / Notes

- Copilot se učí z kontextu projektu, takže čím více souborů máte otevřených, tím lepší jsou návrhy
- Pokud návrh není dokonalý, přijměte ho a pak upravte podle potřeby
- Používejte Tab pro přijetí, Alt+] pro další návrhy

---

- Copilot learns from project context, so the more files you have open, the better the suggestions
- If a suggestion isn't perfect, accept it and then modify as needed
- Use Tab to accept, Alt+] for alternative suggestions
