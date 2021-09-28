# DSL Errors/Internet Speed/Weather Monitor

Polls the Arris NVG443B ADSL/VDSL2+ modem for stats (errors, connection speed, etc)
Polls speedtest.net for internet speed data
Polls pirateweather.net for weather data which may impact DSL line quality


![Alt text](https://raw.github.com/keithknott26/dsl_internet_monitoring/master/dsl_internet_monitoring_screenshot.png?raw=true "Grafana Screenshot")


## Grafana

https://grafana.com/docs/grafana/latest/administration/configure-docker/

```shell
docker volume create grafana-storage
```

## PirateWeather API Key

Obtain a PirateWeather API key from www.pirateweather.net and configure Line 10 of weather/weather.py:

```PIRATE_WEATHER_API_KEY = "xxxxxxxxxxxxx"```

Find your LAT and LONG and replace, at the top of weather/weather.py

```LAT_LONG = "48.578471,-73.41749"```

## Arris DSL Modem address

Open dsl/parse_arris_stats_page.py and replace 192.168.254.254 with your Modem's IP address if different.

## Dependencies

```brew install docker-compose docker```

## Bring the services up

```
docker-compose build
docker-compose up
```

## Navigate to the running services

Grafana: http://localhost:3000   (a pre configured dashboard is already installed under Dashboards -> Manage)
Prometheus: http://localhost:9000


Credits [repo(s)](https://github.com/ziply-dsl-monitor).



