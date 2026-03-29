# worked 3/29/2026

poetry run fuckdl dl Hulu "https://www.hulu.com/movie/9e96f51e-6806-4306-9773-e96b68d25305"

# Fails, needs upgrade to no Ads subscription

poetry run fuckdl dl --debug Netflix 81450504

## Error

 - This title is not available to watch instantly. Please try another title.
2026-03-29 15:31:45 [C] MSL : - manifest/playapi-ADS_STREAM_LEVEL_REQUEST_DISALLOWED: Stream level request for serving ads is no longer supported [viewableId=81340183]