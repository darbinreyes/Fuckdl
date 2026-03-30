# worked 3/29/2026

poetry run fuckdl dl Hulu "https://www.hulu.com/movie/9e96f51e-6806-4306-9773-e96b68d25305"

# Fails, needs upgrade to no Ads subscription

poetry run fuckdl dl --debug Netflix 81450504

## Error

 - This title is not available to watch instantly. Please try another title.
2026-03-29 15:31:45 [C] MSL : - manifest/playapi-ADS_STREAM_LEVEL_REQUEST_DISALLOWED: Stream level request for serving ads is no longer supported [viewableId=81340183]


# .wvd files

https://forum.videohelp.com/threads/413719-Ready-to-use-CDMs-available-here%21


# making a .wvd

Download zip from https://forum.videohelp.com/threads/413719-Ready-to-use-CDMs-available-here%21

In the same folder, rename

client_id.bin -> device_client_id_blob

private_key.pem -> device_private_key

Create wv.json per below

# wv.json

{
      "name": "chrome_l3",
      "session_id_type": "chrome",
      "security_level": 3
}

# wvd Command

poetry run python3 scripts/WVD/MakeWVD.py my_chrome_device/

  With the folder containing:
  my_chrome_device/
  ├── wv.json
  ├── device_client_id_blob    ← client_id.bin renamed
  └── device_private_key       ← private_key.pem renamed