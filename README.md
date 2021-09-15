# Prometheus sensor for Home Assistant

Query latest values from prometheus metrics and import them as as sensors into home assistant.

Tested with Home Assistant 2021.8.8.

## Example usage

```
sensor:
  - platform: prometheus
    url: http://localhost:9090
    queries:
      - name: Energy usage
	expr: energy_usage_wh / 1000
        unit_of_measurement: kWh
	device_class: energy
	state_class: measurement
      - name: Energy solar production
	expr: energy_solar_wh / 1000
        unit_of_measurement: kWh
	device_class: energy
	state_class: measurement
      - name: Energy grid consumption
        unit_of_measurement: kWh
	expr: energy_grid_wh / 1000
	device_class: energy
	state_class: measurement
```

