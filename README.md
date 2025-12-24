# 🌤️ Atmos - Advanced Weather Dashboard

Atmos is a modern, feature-rich weather application that provides comprehensive weather information with an intuitive and beautiful user interface. Built with pure HTML, CSS, and JavaScript, it leverages the WeatherAPI.com service to deliver accurate, real-time weather data.

![Weather Dashboard](https://img.shields.io/badge/Status-Live-brightgreen) ![License](https://img.shields.io/badge/License-MIT-blue) ![API](https://img.shields.io/badge/API-WeatherAPI.com-orange)

## ✨ Features

### 🌍 **Core Weather Information**
- **Current Conditions**: Temperature, "feels like", humidity, wind speed, pressure, and UV index
- **Detailed Forecast**: 5-day weather forecast with day/night temperatures
- **Hourly Breakdown**: 24-hour forecast with hourly temperature and conditions
- **Location-based**: Automatic detection of your current location

### 🎨 **User Experience**
- **Responsive Design**: Fully responsive layout that works on mobile, tablet, and desktop
- **Dark/Light Themes**: Toggle between dark and light modes
- **Temperature Units**: Switch between Celsius (°C) and Fahrenheit (°F)
- **Search Suggestions**: Auto-complete with city suggestions as you type
- **Recent Searches**: Quick access to previously searched locations (stored locally)

### 📱 **Interactive Elements**
- **Live Search**: Real-time search with debounced API calls
- **Smooth Animations**: Hover effects and transitions for better UX
- **Loading States**: Visual feedback during data fetching
- **Error Handling**: User-friendly error messages for failed requests

## 🚀 Quick Start

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection for API calls
- A free API key from [WeatherAPI.com](https://www.weatherapi.com/)

### Installation

1. **Clone or download the project**
   ```bash
   git clone https://github.com/yourusername/atmos-weather-app.git
   cd atmos-weather-app
   ```

2. **Get your API key**
   - Visit [WeatherAPI.com](https://www.weatherapi.com/)
   - Sign up for a free account (100,000 calls/month)
   - Copy your API key from the dashboard

3. **Configure the API key**
   - Open `index.html` in a code editor
   - Find line 407 in the `<script>` section:
   ```javascript
   const API_KEY = "9b342010d3fd4cef89073201252412";
   ```
   - Replace the existing key with your own

4. **Run the application**
   - Simply open `index.html` in your web browser
   - Or use a local server for better performance:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js with http-server
   npx http-server
   ```

## 📁 Project Structure

```
atmos-weather-app/
├── index.html          # Main application file
├── README.md           # This documentation
└── assets/            # (Optional) Directory for additional assets
    ├── icons/         # Weather icons
    └── images/        # Backgrounds and other images
```

## 🔧 API Integration

Atmos uses the [WeatherAPI.com](https://www.weatherapi.com/) service, which provides:

### **Endpoints Used**
1. **Current Weather**: `/current.json` - Real-time weather conditions
2. **Forecast**: `/forecast.json` - 5-day weather forecast
3. **Search/Auto-complete**: `/search.json` - City search suggestions

### **Rate Limits**
- Free tier: 1,000,000 calls per month
- 3-day forecast in free tier
- Historical data available in paid plans

## 🎯 Usage Guide

### **Searching for Weather**
1. Type a city name in the search box (e.g., "New York")
2. Use the auto-complete suggestions for quick selection
3. Click the search button or press Enter
4. View comprehensive weather data for your selected location

### **Using Features**
- **Toggle Units**: Click °C/°F buttons to switch temperature units
- **Change Theme**: Click the moon/sun icon to toggle dark/light mode
- **Recent Searches**: Click any city in the recent searches panel
- **Hourly Forecast**: Scroll horizontally to view 24-hour forecast

### **Geolocation**
- On first load, Atmos asks for location permission
- If granted, it automatically shows weather for your current location
- If denied, it defaults to London

## 📱 Responsive Design

Atmos adapts to different screen sizes:

- **Desktop (>1200px)**: Multi-column layout with all features visible
- **Tablet (768px-1200px)**: Adjusted grid layout
- **Mobile (<768px)**: Single-column stack for optimal viewing

## 🛠️ Technical Implementation

### **Frontend Technologies**
- **HTML5**: Semantic markup and structure
- **CSS3**: Modern features like CSS Grid, Flexbox, CSS Variables
- **JavaScript ES6+**: Async/await, Fetch API, Local Storage

### **Key JavaScript Functions**

| Function | Purpose |
|----------|---------|
| `getWeather()` | Fetches and displays weather data |
| `setUnit()` | Toggles between temperature units |
| `toggleTheme()` | Switches between dark/light modes |
| `updateForecast()` | Renders 5-day forecast |
| `updateHourlyForecast()` | Displays 24-hour forecast |
| `addToRecentSearches()` | Manages recent search history |

### **Local Storage**
- Recent searches are stored in `localStorage`
- Theme preference could be extended to persist
- No sensitive data is stored locally

## 🔍 Code Highlights

### **Debounced Search Suggestions**
```javascript
function debounce(func, wait) {
  let timeout;
  return function executedFunction(...args) {
    const later = () => {
      clearTimeout(timeout);
      func(...args);
    };
    clearTimeout(timeout);
    timeout = setTimeout(later, wait);
  };
}
```

### **CSS Custom Properties for Theming**
```css
:root {
  --bg: #0f172a;
  --card: #020617;
  --accent: #38bdf8;
  --text: #e5e7eb;
  --muted: #94a3b8;
}

body.light {
  --bg: #f8fafc;
  --card: #ffffff;
  --text: #1e293b;
  --muted: #64748b;
}
```

## 🚀 Future Enhancements

### **Planned Features**
- [ ] Weather alerts and notifications
- [ ] Interactive weather maps
- [ ] Air quality index (AQI) display
- [ ] Weather trends and comparisons
- [ ] Multiple location tracking
- [ ] Weather widget export
- [ ] Offline capability with Service Workers
- [ ] PWA (Progressive Web App) installation

### **API Extensions**
- Integrate with additional weather APIs for redundancy
- Add historical weather data
- Include marine weather and tide information
- Implement severe weather alerts

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### **Development Guidelines**
- Follow the existing code style
- Add comments for complex logic
- Test changes on multiple devices
- Update documentation as needed

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Weather Data**: Powered by [WeatherAPI.com](https://www.weatherapi.com/)
- **Icons**: Font Awesome for UI icons
- **Design Inspiration**: Modern dashboard designs and weather apps
- **Development Tools**: Built with vanilla web technologies

## 📞 Support

- **Report Issues**: [GitHub Issues](https://github.com/yourusername/atmos-weather-app/issues)
- **Feature Requests**: Open an issue with the "enhancement" label
- **Questions**: Check the FAQ or open a discussion

## 🌟 Show Your Support

If you find this project useful, please give it a star ⭐ on GitHub!

---

**Built with ❤️ by Jeremy Eclarino** | *Weather affects everyone. Stay informed.*

---

## 📋 Changelog

### v1.0.0 (Initial Release)
- ✅ Complete weather dashboard with current conditions
- ✅ 5-day forecast display
- ✅ 24-hour hourly forecast
- ✅ Dark/light theme toggle
- ✅ Temperature unit conversion
- ✅ Search suggestions
- ✅ Recent searches with local storage
- ✅ Geolocation support
- ✅ Fully responsive design

---

*Note: This is a frontend-only application. All weather data is fetched from WeatherAPI.com in real-time. The free API key is rate-limited to 1,000,000 calls per month, which is sufficient for personal use and small-scale deployment.*