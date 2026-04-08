🌐 Web Mechanism of our Project (Hydronix Dashboard)
1. 🧠 Overall Architecture
Your project is a client-side web application that runs entirely in the browser.
It follows this structure:
•	Frontend (UI Layer): 
o	HTML → structure 
o	CSS → design 
o	JavaScript → logic + interactivity 
•	External APIs: 
o	OpenWeatherMap API → weather data 
•	Browser Services: 
o	Geolocation API → user location 
o	LocalStorage → saving user state 
•	Visualization Libraries: 
o	Chart.js → graphs 
o	Leaflet.js → interactive maps 
________________________________________
2. ⚙️ How the System Works Step-by-Step
🔹 Step 1: Page Loading
When the user opens the website:
1.	HTML loads → builds the layout (sidebar, cards, map, chart) 
2.	CSS applies styling (colors, spacing, layout) 
3.	JavaScript starts running inside: 
window.onload = function() { ... }
👉 This ensures everything runs only after the page is fully loaded.
________________________________________
🔹 Step 2: Authentication Check
The system checks if the user is logged in:
localStorage.getItem("loggedIn")
•	If ❌ not logged in → redirect to login page 
•	If ✅ logged in → continue loading dashboard 
👉 This simulates a simple client-side authentication system.
________________________________________
🔹 Step 3: Fetching Weather Data (API Communication)
How it works:
The app sends an HTTP request to OpenWeatherMap:
fetch("https://api.openweathermap.org/data/2.5/forecast")
Process:
1.	Browser sends request 
2.	OpenWeatherMap server responds with JSON data 
3.	JavaScript reads and processes the response 
Data used:
•	temperature 
•	rain probability 
•	forecast list 
👉 This is a client-server architecture (REST API).
________________________________________
🔹 Step 4: Data Processing
After receiving API data:
•	Extract rainfall values 
•	Convert missing values to 0 
•	Build arrays for graph: 
rainData.push(item.rain?.["3h"] ?? 0);
👉 This ensures the system doesn’t crash if data is missing.
________________________________________
🔹 Step 5: Visualization Layer
📊 Chart.js (Graph)
•	Takes processed rain data 
•	Renders a line chart 
•	Updates dynamically when data changes 
🗺️ Leaflet Map
1.	Detects user location using: 
navigator.geolocation
2.	Loads map tiles 
3.	Adds marker at user position 
4.	Shows rainfall popup 
👉 This creates a real-time geospatial visualization system.
________________________________________
🔹 Step 6: AI Prediction Logic
The “AI” part is rule-based (not ML yet):
Process:
1.	Take last 5 rain values 
2.	Compute average: 
avg = sum / 5
3.	Classify: 
•	Low ☀️ → avg ≤ 1 
•	Moderate 🌥️ → avg 1–5 
•	High 🌧️ → avg > 5 
👉 This is a simple predictive analytics model (statistical forecasting).
________________________________________
🔹 Step 7: Language Switching System
The system uses:
localStorage
Flow:
1.	User selects language 
2.	Text content updates dynamically 
3.	Preference is saved in browser 
👉 This is a client-side internationalization (i18n) system.
________________________________________
🔹 Step 8: Toast Notification System
•	Displays welcome message 
•	Uses CSS animation 
•	Disappears after 3 seconds 
👉 This improves user experience (UX feedback loop).
________________________________________
🔹 Step 9: Map Mechanism (Tile System)
The map uses:
•	Tile-based rendering system 
•	Each zoom level loads image tiles from server 
Example:
https://tile.openstreetmap.de/{z}/{x}/{y}.png
👉 This is how modern maps (Google Maps style) work.
________________________________________
3. 🔄 Full System Flow
User opens website
        ↓
HTML/CSS loads UI
        ↓
JavaScript starts
        ↓
Check login (localStorage)
        ↓
Fetch weather API
        ↓
Process JSON data
        ↓
Render chart + map
        ↓
User interacts (language / prediction)
        ↓
UI updates dynamically
________________________________________
4. 🧩 Key Technologies Used
•	HTML → structure 
•	CSS → styling 
•	JavaScript → logic 
•	REST API → data fetching 
•	Chart.js → visualization 
•	Leaflet.js → mapping 
•	Browser APIs: 
o	Geolocation API 
o	LocalStorage API 

