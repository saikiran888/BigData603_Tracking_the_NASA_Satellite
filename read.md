## ISS Satellite Location Tracking Code Explanation

This code is designed to track the International Space Station (ISS) location and display it on a world map. It collects streaming data of the ISS's longitude and latitude coordinates provided by NASA's Open Notify API.

### Key Features:

1. **Data Collection and Visualization:**
   - The code connects to the [Open Notify API](http://api.open-notify.org/iss-now.json) to collect real-time ISS location data.
   - The ISS location is visualized on a world map using [Plotly](https://plotly.com/), a popular Python graphing library.

2. **Data Persistence:**
   - The collected location data is saved to a CSV file for future reference.

3. **Data Resumption:**
   - The code checks if a CSV file containing previous data exists.
   - If the file exists, it prompts the user to decide whether to use the existing data or start a new data collection.
   - This is helpful because the data collection process takes approximately one hour, and this feature allows you to continue from where you left off.

### How the Resumption Feature Works:

When you run the code, it performs the following steps:

1. **Checking for Existing Data:**
   - The code checks if a CSV file with location data exists in the specified file location.

2. **User Prompt:**
   - If the file exists, it asks the user for their preference:
     - To use the existing data and continue the visualization.
     - To start a new data collection from scratch.

3. **Usage Scenarios:**
   - If you choose to use existing data, it loads the data from the CSV file and continues visualizing the ISS's location on the map.
   - If you choose to start over, it deletes the existing CSV file and begins a new data collection.

This feature ensures that users have control over whether to reuse previously collected data or start fresh, making the code more flexible and user-friendly.

Please note that due to the fast travel of the ISS, the resulting map will likely show more than half of the Earth's surface covered with the satellite's track during the one-hour data collection.
