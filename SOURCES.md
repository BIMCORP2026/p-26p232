# B-71 prototype: data sources and licenses
Built by B.I.M. Corporation for Metropolitan Council RFP 26P232 (prototype, public data). Static files only: HTML, JavaScript, GeoJSON. No API keys, no basemap service, no cookies, no analytics or trackers. No Council non-public data was used (Section 9).

| Data | Source | License |
|---|---|---|
| Transitway stations (existing), mode and corridor | Metropolitan Council, "Transitway Stations" layer, https://arcgis.metc.state.mn.us/arcgis/rest/services/MTS/rsa/MapServer/0 (downloaded Nov 17, 2026); described on the Minnesota Geospatial Commons as "Transitways Generalized (Alignments and Stations)" | Public domain under the Minnesota Government Data Practices Act (Minn. Stat. ch. 13), per the dataset metadata |
| Transitway alignments | Same service, layer 7 "Transitway Alignments" | Same |
| Renter households (B25003), median gross rent (B25064), gross rent as % of income (B25070), census tracts | U.S. Census Bureau, American Community Survey 2019–2023 5-year estimates, table-based summary files, https://www2.census.gov/programs-surveys/acs/summary_file/2023/table-based-SF/ | U.S. government work, public domain |
| Tract boundaries | U.S. Census Bureau, 2023 cartographic boundary file cb_2023_27_tract_500k | Public domain |
| Map library | MapLibre GL JS 4.7.1 (vendored in vendor/) | BSD-3-Clause (vendor/MAPLIBRE-LICENSE.txt) |

Method notes: station areas are half-mile (804.672 m) buffers; station-area and corridor values are area-weighted from the tracts they overlap; "avg. median rent" is a renter-weighted average of tract medians (an approximation, not a true median). Cost burden = renters paying 30% or more of income on gross rent, excluding "not computed". ACS figures carry margins of error not shown here. The trend chart in the side panel is SAMPLE DATA, clearly labeled, standing in for the 2006–2025 Analysis-team outputs. Rebuild: `python build_data.py` (needs geopandas) from `source-data/`.
