# 📊 Pawnshop Database - IME Roleplay

Comprehensive price database for the pawnshop system on IME Roleplay server. This repository stores selling price data for various items that can be sold to pawnshops, along with crafting calculations for mining materials and jewelry.

[![Last Update](https://img.shields.io/github/last-commit/ardelagi/pawndata?label=Last%20Update&color=orange)](https://github.com/ardelagi/pawndata/commits/main)
[![Contributors](https://img.shields.io/github/contributors/ardelagi/pawndata?color=blue)](https://github.com/ardelagi/pawndata/graphs/contributors)
[![License](https://img.shields.io/badge/License-Open%20Source-green)](LICENSE)

## 📋 Table of Contents

- [Item Categories](#-item-categories)
- [Data Structure](#-data-structure)
- [How to Contribute](#-how-to-contribute)
- [Data Update Format](#-data-update-format)
- [Contribution Rules](#️-contribution-rules)
- [Integration](#-integration)

## 🏷️ Item Categories

This database includes 6 main categories with detailed pricing:

### 1. **PERTANIAN** 🌾 (Farming)
Farm produce including vegetables, fruits, and food crops.
- **Total Items:** 17
- **Price Range:** $3 - $5
- **Examples:** Carrot, Potato, Tomato, Watermelon

### 2. **RONGSOKAN** ♻️ (Scrap)
Recyclable used goods and materials.
- **Total Items:** 4
- **Price Range:** $2 - $150
- **Examples:** Metal Scrap, Broken Phone, Empty Bottle

### 3. **TAMBANG** ⛏️ (Mining)
Raw mining materials and processed ores.
- **Total Items:** 12
- **Price Range:** $7 - $78
- **Examples:** Copper, Iron, Gold Ingot, Diamond, Ruby
- **Special:** Includes crafting requirements in `mining.json`

### 4. **PERHIASAN** 💎 (Jewelry)
Luxury accessories crafted from mining materials.
- **Total Items:** 22
- **Price Range:** $129 - $678
- **Examples:** Ruby Ring, Emerald Necklace, Diamond Earring
- **Special:** Complete crafting recipes in `mining.json`

### 5. **ALKOHOL** 🍷 (Alcohol)
Alcoholic beverages and mixers.
- **Total Items:** 13
- **Price Range:** $28 - $45
- **Examples:** Red Wine, Vodka, Whiskey, Sake

### 6. **HUNTING** 🦌 (Hunting)
Items obtained from hunting wild animals.
- **Total Items:** 14
- **Price Range:** $7 - $28
- **Examples:** Animal Skins (Deer, Boar, Coyote), Raw Meat

## 📁 Data Structure

### Main Files

```
pawndata/
├── data.txt           # Complete list of all items and prices
├── mining.json        # Crafting details for jewelry and mining materials
└── README.md          # This documentation
```

### Format: `data.txt`

Simple category-based format for pawnshop prices:

```
[CATEGORY_NAME]
Item Name = $Price
```

**Example:**
```
[PERTANIAN]
Carrot = $5
Potato = $3

[TAMBANG]
Gold Ingot = $58
Diamond = $31
```

### Format: `mining.json`

JSON structure for crafting calculations and requirements:

```json
{
  "tambang": {
    "item_name": {
      "require": {
        "material_name": quantity
      },
      "price": sell_price
    }
  },
  "perhiasan": {
    "item_name": {
      "require": {
        "material_name": quantity
      },
      "price": sell_price
    }
  }
}
```

**Example:**
```json
{
  "tambang": {
    "gold_ingot": {
      "require": {
        "gold_ore": 2
      },
      "price": 58
    }
  },
  "perhiasan": {
    "ruby_ring": {
      "require": {
        "gold_ring": 1,
        "ruby": 4
      },
      "price": 351
    }
  }
}
```

## 🤝 How to Contribute

### Quick Start Guide

1. **Fork the Repository**
   ```
   Click the "Fork" button at the top right of this page
   ```

2. **Clone to Local**
   ```bash
   git clone https://github.com/YOUR_USERNAME/pawndata.git
   cd pawndata
   ```

3. **Create a New Branch**
   ```bash
   git checkout -b update-prices-DD-MM-YY
   ```

4. **Edit Data Files**
   - Open `data.txt` for pawnshop prices
   - Open `mining.json` for crafting items
   - Ensure format consistency

5. **Commit Your Changes**
   ```bash
   git add .
   git commit -m "Update: [Category] - Date"
   ```

6. **Push to GitHub**
   ```bash
   git push origin update-prices-DD-MM-YY
   ```

7. **Create Pull Request**
   - Open the repository on GitHub
   - Click "New Pull Request"
   - Fill in the description clearly

## 📝 Data Update Format

### Price Update Template

**For data.txt:**
```
[CATEGORY]
Item Name = $New_Price  # (previously: $Old_Price)
```

**For mining.json:**
```json
"item_name": {
  "require": {
    "material": quantity
  },
  "price": new_price  // was: old_price
}
```

### Adding New Items

**For data.txt:**
```
[CATEGORY]
New Item Name = $Price
```

**For mining.json:**
```json
"new_item": {
  "require": {
    "material_1": quantity,
    "material_2": quantity
  },
  "price": sell_price
}
```

### Pull Request Description Example

```markdown
## Price Update -  23-12-2025

### Changes:
- [PERTANIAN] Potato: $3 → $4
- [TAMBANG] Diamond: $31 → $35
- [PERHIASAN] Ruby Ring: $351 → $360

### New Items:
- [PERTANIAN] Pumpkin = $5
- [HUNTING] Bear Skin (Low) = $25

### Mining.json Updates:
- Updated ruby_ring price: 351 → 360
- Updated emerald_ring requirements
```

## ⚠️ Contribution Rules

### ✅ DO (Best Practices)

- ✅ Verify data accuracy before submitting
- ✅ Follow existing format conventions
- ✅ Include information sources
- ✅ Update both files if item involves crafting
- ✅ Use descriptive branch names
- ✅ Write clear commit messages
- ✅ Test JSON validity before committing
- ✅ Check for typos in item names

### ❌ DON'T (Avoid These)

- ❌ Change file structure format
- ❌ Add unverified data
- ❌ Delete items without confirmation
- ❌ Commit directly to main branch
- ❌ Use estimated/guessed prices
- ❌ Break JSON syntax
- ❌ Mix category formats

## 🔍 Data Verification

Before submitting updates, ensure:

- ✅ Prices cross-checked with in-game pawnshop
- ✅ Consistent formatting (capitalization, punctuation)
- ✅ No typos in item names
- ✅ Crafting profit calculations make sense
- ✅ JSON is valid (use [JSONLint](https://jsonlint.com/))
- ✅ File encoding is UTF-8
- ✅ No duplicate entries

## 📊 Profit Analysis Template

For crafting items, you can add profit analysis:

```
Ruby Ring
━━━━━━━━━━━━━━━━━━━━━━━━━
Materials:
  • Gold Ring: $0 (crafted from Gold Ingot $58)
  • Ruby x4: $39 × 4 = $156
  
Total Cost: $214
Sell Price: $351
Net Profit: $137 (64% margin)
```

## 🔗 Integration

This database is used by:

- **IME Pawnshop Web App**: [pawnshop.ardelagi.web.id](https://pawnshop.ardelagi.web.id)
  - Real-time price tracking
  - Crafting calculator
  - Price trend analysis


## 📞 Contact & Support

- **Discord Server:** IME Roleplay
- **Issues:** Report bugs or data discrepancies via [GitHub Issues](https://github.com/ardelagi/pawndata/issues)
- **Discussions:** Use [Discussions](https://github.com/ardelagi/pawndata/discussions) tab for general discussions
- **Web App:** [pawnshop.ardelagi.web.id](https://pawnshop.ardelagi.web.id)

## 🎯 Roadmap

- [ ] Add historical price tracking
- [ ] Implement automated price validation
- [ ] Create API documentation
- [ ] Add price prediction based on trends
- [ ] Include seasonal price variations
- [ ] Add more crafting categories


## 📈 Statistics

- **Total Items:** 82+ items across 6 categories
- **Crafting Items:** 33 items with recipes
- **Update Frequency:** As needed by community
- **Active Contributors:** Community-driven

---


**Last Updated:** December 23, 2025  
**Maintained by:** IME Roleplay  
**Powered by:** [IME Government - Department of Treasury](https://github.com/ardelagi)

Made with ❤️ by IME Roleplay Community

