# GeoReady: On-Demand Spatial Data Prep for Any Canadian Community 🇨🇦

GeoReady is a Python-based geospatial automation tool for downloading, filtering, and clipping key spatial datasets—DEMS, railways, industrial sites, and census subdivisions—for any named Canadian community. Designed for researchers, planners, and GIS analysts, GeoReady simplifies complex workflows by automating the spatial data preparation pipeline.

Created by Enrie-Joy Sala and Brian Gauthier as a submission for the 2025 GeoIgnite Hackathon with NRCan and geo.ca
For educational/hackathon purposes only
© 2025

---

## 🚀 Features

- 🔍 Search for any Canadian community by name  
- 📦 Automatically download:
  - Digital Elevation Model (SRTM)
  - Census Subdivision boundaries (2021)
  - National Rail Network shapefiles from NRCan (via FTP)
  - Industrial sites data (Metal Works, Oil & Gas, Producing Mines)
- ✂️ Clip railways and industrial sites to your area of interest (AOI)
- 🌍 Output data is reprojected to EPSG:4326 for GEE compatibility
- 🌐 Google Earth Engine integration via `geemap` and `ee`

---

## 🧰 Requirements

- Python 3.13.1
- Required Python packages:
  - `geopandas`
  - `requests`
  - `zipfile`
  - `ftplib`
  - `shapely`
  - `fiona`
  - `earthengine-api`
  - `geemap`
  - `tqdm`

Install them via pip:

    pip install geopandas requests shapely fiona geemap earthengine-api tqdm

---

## 🔧 Setup

1. **Clone the repository:**

    git clone https://github.com/6rianDigital/geoready 
    cd geoready

2. **Set up directory structure:**

The script will automatically create:

    /data/raw  
    /data/processed

3. **Set your Area of Interest (AOI):**

In the script, change:

    subdivision_name = "Tumbler Ridge"

To your desired Canadian community.

4. **Initialize Google Earth Engine:**

Uncomment this the first time you run:

    # ee.Authenticate()  
    ee.Initialize(project='your-earth-engine-project-id-here')

---

## 📂 Output

- Clipped and reprojected:
   - **railway shapefiles**  
   - **industrial site shapefiles**  
   - **Census Subdivision geometry**
   - **DEM**   
   - **Streams Network**
   - Terrain Layers
- Ready for further spatial analysis or GEE ingestion

---

## 📸 Example Use Case

Want to analyze rail and mine proximity for environmental planning in a specific BC town? Just enter the name and let GeoReady fetch and clip everything you need in one go.

---

## 📁 Folder Structure

    /geoready  
    ├── geoready.py  
    ├── /data  
    │   ├── /raw  
    │   └── /processed  
    └── README.md

---

## 🛠️ To-Do

- Add support for other administrative levels (CMA, DA, etc.)
- Add buffer and proximity analysis
- Optional upload to Google Drive or GEE asset
- GUI or streamlit app

---

## 📜 License

MIT License

---

## 👤 Authors

Brian Gauthier & Enrie-Joy Sala 
Centre of Geographic Sciences, 2025.  
https://github.com/6rianDigital/
