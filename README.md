# Warehouse Review

Minimalistic, but fully functioning solution. This is nearly static solution that satisfy all the task requirements.

Can be deployed to any web server that can serve static files, including Github Pages.

## Screen recording

![Screen recording](SCREEN_RECORDING_LIGHT.gif "Screen recording")

## Start the server

Use eny static web server, e.g. [caddy](https://caddyserver.com/docs/install#homebrew-mac)

~~~sh
caddy file-server --listen :9000
~~~

## Upload Robot Report

To upload a robot report, simly copy JSON file in `./robot_reports` folder and update the select with the new option:

~~~sh
cp ~/www/Dexory/example-robot.json ~/www/warehouse_review_light/robot_reports/2024-02-05.json && \
sed -i '' '/<!-- NEW_REPORT -->/a\
<option value="/robot_reports/2024-02-05.json">2024-02-05.json</option>\
' ~/www/warehouse_review_light/index.html
~~~

This command assums that we have robot report file `~/www/Dexory/example-robot.json` and this app is located inside `~/www/warehouse_review_light` folder.

## Usage

Select the CSV file and choose a robot report from the select. CSV file is analyzed directly in the client (in frontend) and compared to the robot report (a JSON file that was previously uploaded to the server) which is loaded from the server.
