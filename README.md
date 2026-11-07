# 🇲🇾 Malaysia Public Holidays Data (`my-calendar-data`)

An open-source static JSON dataset containing Malaysian national and state public holiday data. Hosted publicly via GitHub Pages for simple, unauthenticated access.

## 📁 Repository Structure

```
my-calendar-data/
├── README.md
├── state-code.json        # List of Malaysian states & ISO codes (root metadata)
└── data/
    ├── 2025.json      # Holidays for 2025
    ├── 2026.json      # Holidays for 2026
    └── 2027.json      # Holidays for 2027

```

## 🌐 Fetching Data

**Base URL:**
`https://<YOUR-ORG-NAME>.github.io/my-calendar-data/`

### JavaScript Example

```
// Fetch 2026 holidays
const res = await fetch('https://<YOUR-ORG-NAME>.github.io/my-calendar-data/data/2026.json');
const holidays = await res.json();

// Filter for Selangor (SGR) + National holidays
const selangorHolidays = holidays.filter(
  (h) => h.states.includes('ALL') || h.states.includes('SGR')
);

```

## 📄 Schemas

### `data/2026.json`

```
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

### `states.json` (Root)

```
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

## 📜 License

[MIT License](LICENSE)