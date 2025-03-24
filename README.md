# 2024_ia651_puthenveettil

## Dataset Description
This project uses the Airline On-Time Performance and Delay Causes dataset, which provides comprehensive information about U.S. domestic flights, compiled by the U.S. Bureau of Transportation Statistics (BTS).
The dataset used is structured monthly and includes:
- Time information: `year`, `month`
- Flight identification: `carrier`, `carrier_name`
- Location data: `airport`, `airport_name`
- Flight counts and delay metrics:
    - `arr_flights`: Total arrival flights
    - `arr_del15`: Number of flights delayed by 15 minutes or more
    - `arr_cancelled`, `arr_diverted`: Cancellations and diversions
    - `arr_delay`: Total delay minutes for that month
- Delay causes:
    - `carrier_ct`, `weather_ct`, `nas_ct`, `security_ct`, `late_aircraft_ct`
    - Corresponding delay durations: `carrier_delay`, `weather_delay`, `nas_delay`, etc.

This dataset is valuable as it not only captures how often delays occur, but also why they occur, enabling deeper insights into the factors influencing airline performance. It covers all major U.S. airports and airlines, making it well-suited for national-level modeling and operational improvement strategies.

## Process overview