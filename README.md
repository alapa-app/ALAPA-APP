# Cross-city transfer learning for station-level PM2.5 forecasting in Metro Manila

## Station bounding boxes (OpenAQ)

| City | Latitude | Longitude |
|---|---|---|
| Metro Manila | 14.34–14.78°N | 120.93–121.15°E |
| Bangkok | 13.48–13.97°N | 100.32–100.94°E |
| Los Angeles | 33.70–34.34°N | 118.15–118.67°W |

## Inputs

- Time features: sine and cosine of hour of day, day of week and month, in each city's local time.
- Meteorology: each station takes its nearest grid cell, without interpolation.

## GBT

- PM2.5 lags: 0, 1, 2, 3, 6, 12, 24, 48 and 71 hours before the origin.
- XGBoost histogram method, squared-error loss, fixed number of boosting rounds.
- MMD-weighted pooling: c is chosen on Metro Manila validation together with the tree settings.

## Ridge regression

- The penalty is chosen on validation.
