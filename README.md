# 🌤️ ATMOS — Weather Dashboard

A retro-futuristic weather dashboard delivering real-time conditions, 24-hour hourly forecasts, and 7-day outlooks for any city on Earth. Powered entirely by the free Open-Meteo API — no API key, no sign-up, no cost.

![ATMOS Preview](preview-weather.png)

---

## 🔗 Live Demo

**[lizard-creator.github.io/weather-dashboard](https://lizard-creator.github.io/weather-dashboard)**

---

## ✨ Features

- **Live weather data** — current conditions updated every 15 minutes by Open-Meteo
- **City search** — geocodes any city worldwide via Open-Meteo Geocoding API
- **Geolocation** — one-click locate button uses browser GPS for instant local weather
- **Current conditions** — temperature, feels like, humidity, wind speed & direction, pressure, visibility, sunrise, sunset
- **UV index bar** — animated color-coded strip from Low to Extreme
- **24-hour hourly forecast** — scrollable strip, auto-snaps to current hour
- **7-day forecast** — high/low temps, weather icons, rain probability per day
- **Animated wind compass** — SVG needle rotates to true wind direction
- **Dew point & cloud cover** — with plain-English comfort labels
- **Dynamic sky canvas** — HTML5 Canvas background shifts between clear blue, stormy grey, and night themes
- **Live scrolling ticker** — current stats broadcast in a news-style ticker bar
- **Live clock** — updates every second in the masthead
- **Zero dependencies** — no frameworks, no npm, no build tools
- **No API key required** — Open-Meteo is free and open source

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Markup | HTML5 (semantic) |
| Styling | CSS3 (Grid, custom properties, keyframe animations) |
| Scripting | Vanilla JavaScript (async/await, Fetch API) |
| Weather API | [Open-Meteo](https://open-meteo.com) (free, no key) |
| Geocoding | [Open-Meteo Geocoding API](https://geocoding-api.open-meteo.com) |
| Canvas | HTML5 Canvas API (dynamic sky background) |
| Fonts | Google Fonts (Bebas Neue + Space Mono + Crimson Pro) |
| Hosting | GitHub Pages |

---

## 📁 Project Structure

```
weather-dashboard/
├── weather-dashboard.html  # Single-file app — all HTML, CSS, JS
├── README.md               # You are here
└── preview.png             # (optional) screenshot for README
```

---

## 🚀 Getting Started

### View locally

```bash
# Clone the repo
git clone https://github.com/Lizard-Creator/weather-dashboard.git

# Open in browser — no build step needed
open weather-dashboard.html
```

> **Note:** The Geolocation "Locate Me" button requires the page to be served over HTTPS or localhost. It won't work when opened as a local `file://` URL in some browsers.

### Deploy to GitHub Pages

```bash
git add .
git commit -m "Add weather dashboard"
git push origin main
# Enable Pages in Settings → Pages → main / root
```

---

## 🌐 API Reference

### Weather data — Open-Meteo

```
GET https://api.open-meteo.com/v1/forecast
  ?latitude=40.71
  &longitude=-74.00
  &current=temperature_2m,relative_humidity_2m,...
  &hourly=temperature_2m,weather_code,...
  &daily=temperature_2m_max,temperature_2m_min,...
  &timezone=auto
```

No authentication required. Rate limit: 10,000 requests/day on the free tier.

### Geocoding — Open-Meteo

```
GET https://geocoding-api.open-meteo.com/v1/search
  ?name=New+York
  &count=1
  &language=en
```

Returns latitude, longitude, country code, and city name.

---

## 🌦️ WMO Weather Code Reference

The app interprets WMO 4677 weather codes returned by the API:

| Code | Condition |
|------|-----------|
| 0 | Clear Sky |
| 1–3 | Mainly Clear → Overcast |
| 45, 48 | Fog |
| 51–55 | Drizzle |
| 61–65 | Rain |
| 71–77 | Snow |
| 80–82 | Rain Showers |
| 95–99 | Thunderstorm |

---

## 🔮 Planned Improvements

- [ ] Temperature unit toggle (°C / °F)
- [ ] Recent cities history (localStorage)
- [ ] Wind speed unit toggle (km/h / mph / knots)
- [ ] Air quality index (AQI) panel
- [ ] Precipitation chart using Canvas

---

## 📄 License

MIT — free to use, modify, and distribute.

---

*Built by [Lizard-Creator](https://github.com/Lizard-Creator) · Data by [Open-Meteo](https://open-meteo.com)*
