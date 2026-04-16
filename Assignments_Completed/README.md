## Completed Assignments

## My Submissions for Assignments

--- Work Zone ---
Assn 00: Easy Peasy, just markdown stuff
Assn 01: Python Review, not much to say but it was annoying
Assn 02: Missile Geometry 101: Oh boy
    00 - Breeze
    01 - Breeze
    02 - I manually found the coordinates of Jimmy's Egg, but couldn't change the color despite my best efforts. Code below:
    ```py
    
    ```
    03 - After struggling with Codespaces for an hour, I finally figured out how to use VS Code which took another hour. I had ChatGPT write this function for me and plugged it into the whole code which ultimately worked:
    ```py
    # Go here https://python-visualization.github.io/folium/latest/advanced_guide/colormaps.html
    # There is an example with a function to change the fill color of the feature


    # This code tests to see if the "ADMIN" properties first letter is in a - m:
    #   feature["properties"]["ADMIN"][0].lower() in ["a", "b", "c", "d", "e", "f", "g","h", "i", "j", "k", "l", "m"]
    # You can use that test to return one color or another based on first letter.


    m2 = folium.Map(location=[0,0], zoom_start=3)

    def style_by_name(feature):

        name = feature["properties"]['ADMIN']
        if not name:
            return {"fillColor": "gray", "color": "black", "weight": 1, "fillOpacity": 0.5}

        first_letter = name.strip()[0].upper()

        if first_letter <= "M":
            fill_color = "blue"
        else:
            fill_color = "green"

        return {
            "fillColor": fill_color,
            "color": "black",
            "weight": 1,
            "fillOpacity": 0.6,
        }
    
    # Display map without changing colors
    folium.GeoJson(
        data,
        name="world",
        style_function=style_by_name
    ).add_to(m2)
    
    m2
    ```

    04 - Read Through and clicked stuff
    05 - Read Through and clicked stuff
    06 - Utilized ChatGPT to accomplish the tasks and it output this code
    ```py
    from pathlib import Path
    import sys
    import math
    import json

    ####################################
    # Copied code from Micro Lesson 04 #
    ####################################
    GEO_OK = False

    # First attempt: normal import
    try:
        from wdo.geo import haversine_km, destination_point
        GEO_OK = True
    except (ImportError, ModuleNotFoundError) as e:
        print(f"[WARN] Optional geo functions unavailable: {e}")

    # Fallback: add src to sys.path, then retry
    if not GEO_OK:
        print("[WARN] Trying src-path fallback (temporary workaround).")

        p = Path.cwd().resolve()
        repo_root = next(
            (c for c in [p, *p.parents] if (c / "pyproject.toml").exists()), None
        )

        if repo_root is not None:
            src_path = repo_root / "src"
            if src_path.exists() and str(src_path) not in sys.path:
                sys.path.insert(0, str(src_path))

            try:
                from wdo.geo import haversine_km, destination_point
                GEO_OK = True
                print("[INFO] Loaded wdo via src-path fallback.")
            except (ImportError, ModuleNotFoundError) as e:
                print(f"[WARN] Fallback import failed: {e}")

    # Final no-crash fallback functions
    if not GEO_OK:
        def haversine_km(lat1, lon1, lat2, lon2):
            # simple fallback implementation
            R = 6371
            phi1, phi2 = math.radians(lat1), math.radians(lat2)
            dphi = math.radians(lat2 - lat1)
            dlambda = math.radians(lon2 - lon1)

            a = math.sin(dphi/2)**2 + math.cos(phi1)*math.cos(phi2)*math.sin(dlambda/2)**2
            c = 2 * math.atan2(math.sqrt(a), math.sqrt(1-a))
            return R * c

        def destination_point(*args, **kwargs):
            return None



    # Locate data/world_cities_large.json safely
    debug = False

    cwd = Path.cwd()

    # search upward for repo root, then into data/
    repo_root = next((c for c in [cwd, *cwd.parents] if (c / "data").exists()), cwd)
    city_file = repo_root / "data" / "world_cities_fixed.json"

    if debug:
        print("Looking for:", city_file)

    assert city_file.exists(), f"❌ Missing file: {city_file}"

    print("[INFO] Loading city dataset...")

    with open(city_file, "r", encoding="utf-8") as f:
        cities = json.load(f)

    print(f"[INFO] Total cities loaded: {len(cities)}")



    # Reference point: MSU Texas

    msu_lat, msu_lon = 33.87, -98.51



    # Limit by distance (recommended)
    MAX_KM = 500  # keep manageable set

    # ChatGPT Assisted with the logic here
    filtered = []
    for c in cities:
        lat = c.get("lat")
        lon = c.get("lng") or c.get("lon")

        if lat is None or lon is None:
            continue

        d = haversine_km(msu_lat, msu_lon, float(lat), float(lon))

        if d is not None and d <= MAX_KM:
            filtered.append(c)

    print(f"[INFO] Filtered cities: {len(filtered)}")


    # -------------------------------------------------------
    # Build GeoJSON LineString features
    # -------------------------------------------------------
    geojson = {
        "type": "FeatureCollection",
        "features": []
    }

    for c in filtered:
        lat = float(c["lat"])
        lon = float(c.get("lng") or c.get("lon"))
        name = c.get("city", "Unknown")

        feature = {
            "type": "Feature",
            "properties": {
                "from-city": "MSU",
                "to-city": name,
                "stroke": "#ff8800"
            },
            "geometry": {
                "type": "LineString",
                "coordinates": [
                    [msu_lon, msu_lat],
                    [lon, lat]
                ]
            }
        }

        geojson["features"].append(feature)


    print("[INFO] GeoJSON lines created:", len(geojson["features"]))


    # Save output
    output_file = repo_root / "data" / "msu_city_lines.geojson"

    with open(output_file, "w", encoding="utf-8") as f:
        json.dump(geojson, f, indent=2)

    print("[INFO] Saved:", output_file)
    ```
    I also saved an image in my downloads for later use
    07 - Click through and copy and paste some code with some minor edits
    08 - Click through and have ChatGPT help make a few code segments because I was lazy, but it was otherwise simple stuff.
    09 - Created a file in `/src/wdo/` and copied and pasted some code and called it good.

------------------