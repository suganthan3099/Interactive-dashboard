# Monitoring covid cases across England from 2020 to 2021
Data
- [Shapefile](https://geoportal.statistics.gov.uk/datasets/127c4bda06314409a1fa0df505f510e6_0/explore?location=50.499108%2C0.348505%2C5.00)
- [Covid 19](https://ukhsa-dashboard.data.gov.uk/covid-19-archive-data-download)
## Introduction
Covid-19 “Coronavirus Disease 2019,” an infectious disease caused by novel coronavirus SARS-CoV-2. The virus first surfaced in Wuhan, China, towards the end of 2019. It spreads mostly by respiratory droplets that are released when an infected person talks, sneezes, or coughs (Mohan & Vinod, 2020). On January 29, 2020 covid19 was first confirmed in England. And initial cases were from international travellers resulting in escalating cases by local transmission. In response to rising cases on march 2020 national lockdown was announced in England to control the spread.

This study focuses on monitoring monthly COVID-19 cases admitted in England. The data used for this study is sourced from UKSHA, which contains health data across England. For this analysis, data on COVID-19 cases and deaths from June 2020 to January 2021 are utilized. The COVID-19 cases data includes new cases admitted, and the death data comprises new deaths recorded on daily basis at the Upper Tier Local Authority (UTLA) level. In this context, England's COVID-19 data has been recorded across 149 UTLA levels. And England shapefile data is acquired from Office for National Statistics. The actual aim of this dashboard is to show the users varying spatial and temporal pattern of covid cases across England this makes user understand on which period and on which place covid was relatively high and vice versa. Integration of the COVID-19 data and England shapefile on UTLA level, visualises the COVID-19 data on a map. In order to create a temporal map on monthly basis total number of cases and deaths recorded on each months are summed to create a monthly report on COVID-19 data.

### Animated Map of COVID-19 Cases
![image](https://github.com/user-attachments/assets/58662246-045b-44ff-8441-3e48e784bdba)

### Animated Map of COVID-19 Deaths
![image](https://github.com/user-attachments/assets/9c1670d6-9455-4d09-93a3-0a3a522b325f)

## Building an Interactive Dashboard
Dashboard containing interactive choropleth map just as discussed above and also an interactive Bar graph built from holoview and a Dataframe. The dashboard was built from pannel library and folium for making an interactive map. additionally geometry and file size are suppressed to have quick and efficient interactive dashboard with low memory

### Cartographic Interactivity:
Zooming and Panning: The map is built using Folium, which inherently supports zooming and panning. This allows users to focus on specific regions of interest, making the exploration of data spatially intuitive. The zoom level is initially set to show a broader overview, encouraging users to dive deeper into specific areas as needed.

***Color Scaling***: A linear color scale from the branca.colormap module, dynamically coloring regions based on the data magnitude (e.g., cases or deaths). This visual gradient provides an immediate visual cue about the severity and distribution of COVID-19 impact across different regions, making it easier to spot areas with high or low data values. here RdGy_11 colour gradient is used were Red denotes high and grey denotes low value intermediates are white.

***Tooltips***: Implementing tooltips with Folium’s GeoJsonTooltip enhances user interaction by displaying detailed data about the area (like area code and attribute data) when hovered over. This feature keeps the map uncluttered while providing data on-demand, improving user experience by combining simplicity with depth of information.

***Legend and Scale***: A clear and concise legend is made from branca.colormap and scale were included to aid in interpretation, ensuring that even viewers unfamiliar with the data could understand the maps without requiring extensive background information.

## Interactive Components:
Data Attribute Selection: The data_select select dropdown allows users to switch between different data categories (cases, deaths), instantly changing the map visualization. This enables quick comparative analysis without the need for external controls or refreshes. Temporal Data Navigation: The death_slider, cases_slider, these slider provides a temporal dimension to the data. By selecting different months , users can observe how the situation has evolved over time. This slider dynamically updates its options based on the selected data category (cases or deaths), guided by the data_select dropdown, which is a smart way to ensure the data consistency and relevance. Responsive Updating: The dashboard uses Panel's reactive programming model to update visualizations dynamically. When a user changes the selection in any dropdown or slider, the map bar graph and Table update automatically without requiring manual intervention. This responsiveness makes the dashboard highly interactive and engaging. Bar Graph Visualization: Alongside the map, a bar graph provides a summarized view of the data, allowing for quick comparison between regions. This dual visualization strategy (map for spatial analysis and bar graph for quantitative comparison) ensures that users can obtain a holistic understanding of the data from different perspectives. Also provides Stat values of selected attributes on a table.

