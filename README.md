# Saltmarsh

Saltmarsh is a tide and coastal-conditions API for small marinas, harbour offices and sailing clubs. It answers one question well: what will the water be doing at a given place over the next few days.

## What it does

- **Tide predictions** for any of the 2,400 reference stations we maintain, as high and low water times and heights, or as a height curve at ten-minute resolution.
- **Live conditions** where a station has a gauge: observed water level, wind speed and direction, and air pressure, refreshed every five minutes.
- **Sunrise, sunset and moon phase** for the station's coordinates, because crews plan around daylight as much as around water.
- **Alerts**: register a station and a threshold and we call your webhook when the predicted or observed level crosses it.

## How people use it

Everything is HTTPS and JSON. Each account has one or more API keys, sent as a bearer token on every request. The hosted base URL is `https://api.saltmarsh.example/v1`.

The main resources are **stations** (look one up by id, or search by name or by a latitude and longitude with a radius), **predictions** (ask a station for tides between two timestamps), **observations** (the latest readings from a gauged station) and **alerts** (create, list and delete threshold alerts, each pointing at a webhook URL). Predictions and observations are read-only; alerts are the only thing an account writes.

Requests are limited to 300 per minute per key. Heavier users get a dedicated key with a higher limit.

## Where things are going

We are working on a Python client library and on a self-serve dashboard for managing keys and alerts. There is no public documentation site yet; this file is what customers get today.

## Contact

support@saltmarsh.example
