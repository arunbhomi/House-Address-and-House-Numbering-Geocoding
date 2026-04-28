# 🗺️ Address Geocoding Pipeline using House Numbers

## 📌 Overview
This project develops a complete geocoding pipeline to convert raw, unstructured address data into geographic coordinates (latitude and longitude).  

The workflow focuses on Kathmandu-based addresses and handles messy, real-world data using cleaning, parsing, and road-network-based geocoding techniques.

---

## 🎯 Objectives
- Clean and standardize raw address data  
- Extract structured components (street name, house number)  
- Handle inconsistent and noisy address formats  
- Generate accurate geographic coordinates using road geometry  
- Build a fully reproducible geocoding pipeline  

---

## ⚙️ Workflow Pipeline

### 🧹 Section 1: Address Cleaning
- Converts text to lowercase  
- Removes noise (phone numbers, unwanted words)  
- Standardizes common terms (e.g., road → marg)  
- Handles spelling variations  

Output:
- `1cleaned_housenumber.csv`

---

### 🛣️ Section 2: Street Extraction (Marg / Galli)
- Extracts street names using regex  
- Identifies patterns ending with Marg or Galli  
- Creates structured `street_name` field  

Output:
- `2street_address.csv`

---

### 🏠 Section 3: House Number Extraction
- Extracts house numbers from address strings  
- Supports formats like:
  - `12`
  - `12/3`
- Avoids incorrect numeric matches  

Output:
- `3housenumber_street_address.csv`

---

### 📍 Section 4: Geocoding using Road Network
- Matches street names with road shapefile  
- Uses interpolation along road geometry  
- Applies offset logic for left/right side placement  
- Converts projected coordinates to latitude/longitude  

Output:
- `Final Output with Lat_Long.csv`

---

## 🧰 Technologies Used
- Python  
- Pandas  
- GeoPandas  
- Shapely  
- NumPy  
- Regular Expressions (re)  

---

## ▶️ How to Run

1. Clone repository
2. Install dependencies
3. Open notebook
4. Run all cells sequentially

---

## 📌 Key Features
- Fully automated pipeline  
- Handles noisy and unstructured address data  
- Road-network-based geocoding approach  
- Suitable for regions with informal addressing systems  

---

## ⚠️ Notes
- Ensure road shapefile is available before running Section 4  
- Street name matching depends on data consistency  
- Accuracy depends on quality of input addresses  

---

## 🚀 Future Improvements
- Fuzzy matching for street names  
- Integration with external APIs (Google / Baato)  
- Accuracy evaluation with ground truth data  
- Interactive map visualization  

---

## 👤 Author
- [@arunbhomi](https://github.com/arunbhomi)
- This project was developed as part of research work conducted at Kathmandu Living Labs, focusing on geospatial data processing and address-based geocoding.

---

## 📜 License
This project is for academic and research purposes.
