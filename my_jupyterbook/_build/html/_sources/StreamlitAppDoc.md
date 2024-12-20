
# FrontEnd-Streamlit Code

This Python script creates a web-based interface using **Streamlit** for a **Disease Prediction System**. Users can input various health parameters and receive predictions from a backend API.

---

## Key Features

### Libraries Used:
- **Streamlit**: For the user interface.
- **Requests**: To send data to the backend API.
- **JSON**: To handle data configurations and input.
- **OS**: For file path management.
- **Math**: For rounding slider values.

### Input Parameters:
Users can adjust the following health metrics using sliders:
- Pregnancies
- Age
- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI
- DiabetesPedigreeFunction

---

## Workflow

1. **Dynamic Configuration:**
   - Loads slider ranges from a configuration file `streamlit_options.json`.
   - Dynamically creates sliders in the Streamlit sidebar.

2. **User Interaction:**
   - Collects user input for health parameters.

3. **API Integration:**
   - Sends the user input as JSON to the API endpoint `http://localhost:8008/predict` via a `POST` request.
   - Displays the API's prediction result alongside the user input.

---

## Code Overview

### **Streamlit App Code**
```python
import math
import streamlit as st
import requests
import os
import json

# Load slider configurations from a JSON file
user_options = {}
current_dir = os.path.dirname(os.path.abspath(__file__))
file_path = os.path.join(current_dir, "streamlit_options.json")
print("Looking for:", file_path)
StreamLit_SlideBar = json.load(open(file_path))

# Create sliders dynamically
for field_name, range in StreamLit_SlideBar["slider_fields"].items():
    min_val, max_val = range
    current_value = round((min_val + max_val) / 2)
    user_options[field_name] = st.sidebar.slider(field_name, min_val, max_val, value=current_value)

# Trigger prediction on button click
if st.button('Predict'):
    data = json.dumps(user_options, indent=2)
    r = requests.post('http://localhost:8008/predict', data=data)
    st.write(user_options)
    st.write(r.json())
```

---

## Outputs

1. **User Input Display:**
   - Shows the user-selected values for all parameters.
   
2. **API Response Display:**
   - Outputs the prediction received from the backend API (e.g., `{"prediction": 1}`).

---

## Example Input & Output

### Input:
- Pregnancies: 3  
- Age: 30  
- Glucose: 120  
- BloodPressure: 80  
- SkinThickness: 20  
- Insulin: 150  
- BMI: 25.0  
- DiabetesPedigreeFunction: 0.5  

### Output:
- **User Input:** Displays the above input values.
- **Prediction:** A JSON response from the API (e.g., `{"prediction": 1}`).

---

## How to Run
1. Ensure `streamlit_options.json` is in the same directory as the script.
2. Run the application using:
   ```bash
   streamlit run StreamLitApp.py
   ```
3. Adjust the sliders, click **Predict**, and view the results.
