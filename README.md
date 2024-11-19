# Live Weather Dashboard

Pequeño proyecto para aprender el patrón "observer"

## Description
Create a weather dashboard that displays real-time weather updates for multiple cities. The application will have a "Weather Publisher" that fetches data from a weather API and multiple "Weather Subscribers" (components) that display data for specific cities. When the publisher updates, all the subscribers automatically reflect the latest weather data.

## Learning Goals
- Understand and implement the **Observer Design Pattern** in React.
- Learn to manage and update state efficiently.
- Practice building reusable components and hooks.

---

## Features
1. **Weather Publisher (Centralized State):**
   - Fetches real-time weather data for selected cities.
   - Updates the state when new data is available.

2. **Weather Subscriber (Components):**
   - Displays weather information for a specific city (e.g., temperature, humidity, conditions).
   - Automatically updates when the weather data changes in the publisher.

3. **Dynamic Subscriptions:**
   - Add or remove cities from the dashboard dynamically.
   - Each new city component subscribes to the central weather state.

4. **Styling:**
   - Use a simple UI with cards for each city's weather data.

---

## Design Pattern Implementation

1. **Publisher (Observable):**
   - A `WeatherProvider` context manages the centralized weather data state.
   - It uses a custom hook (`useWeatherData`) to allow subscribers to register themselves.

2. **Subscribers (Observers):**
   - Each `CityWeatherCard` component subscribes to updates for a specific city's weather data.
   - When the publisher updates, all registered subscribers rerender.

---

## Steps to Build
1. **Set Up Project:**
   - Create a new React app using `Vite` or `Create React App`.
   - Install dependencies like `axios` for API calls.

2. **Create WeatherProvider:**
   - Use React Context to act as the "Publisher."
   - Fetch weather data from an API (like OpenWeatherMap).
   - Store the data in a central state.

3. **Create CityWeatherCard:**
   - A component that displays weather data for a city.
   - Subscribes to the `WeatherProvider` to get updates.

4. **Add Subscription Logic:**
   - Use custom hooks or context consumers for the subscription mechanism.
   - Ensure efficient updates to avoid unnecessary re-renders.

5. **Add Functionality:**
   - Allow users to add or remove cities.
   - Use a form to input the city name and dynamically create new `CityWeatherCard` components.

6. **Styling:**
   - Add a simple, clean UI using `Tailwind CSS` or `CSS Modules`.

---

## Bonus Challenges
- Add error handling for API requests.
- Implement a caching mechanism to avoid frequent API calls for the same city.
- Introduce animations for adding/removing cities.
