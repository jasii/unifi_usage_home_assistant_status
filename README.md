# unifi_usage_home_assistant_status

This repo contains the files used to monitor monthly data usage on a Ubiquiti USG Pro. If you have a crappy ISP, this will allow you to quickly see how close you are to hitting your monthly data cap.

Uses POST /api/states/<entity_id> from the Home Assistant API

https://developers.home-assistant.io/docs/api/rest#actions

Visit tynick's blog https://tynick.com/blog/12-30-2019/internet-data-usage-monitoring-so-you-dont-hit-your-data-cap/ for full instructions on how to get everything setup.
Instructions are basically the same. Just change the curl URL to point to your server and plug in your own "Long-Lived Access Token"

## get_usage.sh

Queries the WAN port to see how much data has been used (RX and TX) since the last time it was reset.

Sends HTTP request to Home Assistant with data usage.

## reset_usage.sh

Very simple script to reset the counters on the WAN port.

## config.gateway.json

This JSON file will configure cron jobs to run the previous bash scripts at specific intervals.
