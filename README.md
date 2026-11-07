# 🇲🇾 Malaysia Public Holidays Data (`malaysia-public-holidays`)

An open-source static JSON dataset containing Malaysian national and state public holiday data. Served globally via the **jsDelivr CDN** for fast, unauthenticated, zero-configuration access.

---

## 📁 Repository Structure

```text
malaysia-public-holidays/
├── README.md
├── state-code.json    # List of Malaysian states & ISO codes (root metadata)
└── data/
    ├── 2025.json      # Holidays for 2025
    ├── 2026.json      # Holidays for 2026
    └── 2027.json      # Holidays for 2027
```

---

## 🌐 Fetching Data (via jsDelivr CDN)

Using jsDelivr provides high-availability global CDN caching, automatic Brotli compression, and full CORS support without requiring GitHub Pages or API setup.

### Base CDN URL
```text
https://cdn.jsdelivr.net/gh/batudimension/malaysia-public-holidays@main/
```

### Production Endpoints

* **State Codes Metadata:**  
  `https://cdn.jsdelivr.net/gh/batudimension/malaysia-public-holidays@master/state-code.json`

* **2026 Holidays Data:**  
  `https://cdn.jsdelivr.net/gh/batudimension/malaysia-public-holidays@master/data/2026.json`

---

### Fetch Examples

#### JavaScript / Next.js
```javascript
// Fetch 2026 holidays via jsDelivr CDN
const res = await fetch(
  'https://cdn.jsdelivr.net/gh/batudimension/malaysia-public-holidays@master/data/2026.json'
);
const holidays = await res.json();

// Filter for Selangor (SGR) + National holidays
const selangorHolidays = holidays.filter(
  (h) => h.states.includes('ALL') || h.states.includes('SGR')
);

console.log(selangorHolidays);
```

#### cURL
```bash
curl -X GET "https://cdn.jsdelivr.net/gh/batudimension/malaysia-public-holidays@master/data/2026.json"
```

---

## 📄 Schemas

### 1. Yearly Holiday Schema (`data/2026.json`)

```json
[
  {
    "id": "2026-cny-d1",
    "name": {
      "en": "Chinese New Year",
      "ms": "Tahun Baru Cina"
    },
    "date": "2026-02-17",
    "day": "Tuesday",
    "type": "national",
    "states": ["ALL"]
  },
  {
    "id": "2026-selangor-day",
    "name": {
      "en": "Birthday of the Sultan of Selangor",
      "ms": "Hari Lahir Sultan Selangor"
    },
    "date": "2026-12-11",
    "day": "Friday",
    "type": "state",
    "states": ["SGR"]
  }
]
```

### 2. State Codes Schema (`state-code.json`)

```json
[
  {
    "code": "SGR",
    "name": "Selangor",
    "type": "state",
    "weekend": ["Saturday", "Sunday"]
  },
  {
    "code": "KUL",
    "name": "Kuala Lumpur",
    "type": "territory",
    "weekend": ["Saturday", "Sunday"]
  }
]
```

---

## 📜 License

[MIT License](LICENSE)