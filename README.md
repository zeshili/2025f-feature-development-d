# 🌦️ Weather Desktop App (Python + Tkinter)

A modern, lightweight desktop weather application built using **Python Tkinter**.  
It retrieves real-time weather data from **OpenWeatherMap API** and displays it through a clean, responsive graphical interface.

---

## 🚀 Features

- 🔍 Search weather by **city name**
- 🌡️ Displays temperature, feels-like, humidity, pressure, and visibility
- 🌬️ Shows wind speed and direction
- 🌅 Displays **sunrise** and **sunset** times
- ⏰ Shows **local time** for the searched city (via timezone lookup)
- 🖼️ Smooth interface with icons and image-based visual feedback
- 💡 Simple configuration using `config.ini`

---

## 🛠️ Tech Stack

- **Python 3.8+**
- **Tkinter** — GUI framework
- **Pillow** — image handling
- **Requests** — for API calls
- **pytz** — timezone support
- **timezonefinder** — determine timezone from latitude/longitude
- **OpenWeatherMap API** — weather data provider

---

## 📁 Project Structure

```
Weather-Desktop-App/
├── app.py                     # Main application file
├── config.ini                 # Stores your OpenWeatherMap API key
├── Images/                    # UI and button assets
├── Icons/                     # Weather condition icons
├── requirements.txt           # Python dependencies
└── README.md
```

---

## ⚙️ Installation

1. **Clone or unzip** the project:
   ```bash
   git clone <your-repo-url>
   cd Weather-Desktop-App
   ```

2. **Create and activate a virtual environment** (optional but recommended):
   ```bash
   # macOS / Linux
   python3 -m venv .venv
   source .venv/bin/activate

   # Windows (PowerShell)
   py -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
   or manually:
   ```bash
   pip install pillow requests pytz timezonefinder
   ```

4. **Add your API key to `config.ini`:**
   ```ini
   [Openweather]
   api=YOUR_OPENWEATHERMAP_API_KEY
   ```
   > ⚠️ Don’t commit your API key if the project is public.

---

## ▶️ Usage

Run the app:

```bash
# macOS / Linux
python3 app.py

# Windows
py app.py
```

Then:
1. Type a **city name** in the entry field.
2. Click **Search**.
3. The app will fetch and display real-time weather data with icons.
4. Use **Reset** to clear and **Exit** to quit.

---

## 📦 Build an Executable (Optional)

You can turn the app into a standalone executable using **PyInstaller**:

```bash
pip install pyinstaller
pyinstaller --noconsole --onefile --name WeatherApp app.py
```

Include images and icons with the `--add-data` option:

- **Windows (PowerShell):**
  ```bash
  pyinstaller --noconsole --onefile --name WeatherApp `
    --add-data "Images;Images" `
    --add-data "Icons;Icons" `
    app.py
  ```

- **macOS / Linux:**
  ```bash
  pyinstaller --noconsole --onefile --name WeatherApp     --add-data "Images:Images"     --add-data "Icons:Icons"     app.py
  ```

---

## 🧩 Troubleshooting

| Issue | Cause | Fix |
|-------|--------|-----|
| `ModuleNotFoundError` | Missing dependencies | Run `pip install -r requirements.txt` |
| `No GUI appears` | Missing Tkinter (Linux) | Run `sudo apt-get install python3-tk` |
| API returns 401/403 | Invalid API key | Recheck your key in `config.ini` |
| Icons not visible | Incorrect asset path | Ensure folders `Images/` and `Icons/` exist in root |

---

## 🧾 Example `requirements.txt`

```
pillow
requests
pytz
timezonefinder
```

---

## 🧠 Notes

- The GUI uses **Tkinter’s PhotoImage** to display weather icons.
- **TimezoneFinder** uses coordinates from the weather API to determine the city’s local time.
- Avoid overloading the OpenWeatherMap API with too many rapid requests — it may throttle your calls.

---

## 📜 License

This project is open-source under the **MIT License**.  
Feel free to modify and distribute with attribution.

---

## 🙌 Acknowledgments

- Weather data from [OpenWeatherMap](https://openweathermap.org/)
- Icons and images provided in `/Icons` and `/Images` directories
- Developed in Python with ❤️
