# srs-grafana

Grafana dashboards for SRS Prometheus exporter and business data, allows you to import to your Grafana.

## how to import a dashboard

### through the web

* refer to the offical guide [Import a dashboard](https://grafana.com/docs/grafana/latest/dashboards/manage-dashboards/#import-a-dashboard), you can download the dashboard json file in ./dashboards, and uplpoad it.

### through the http api

* refer to the official guide [create--update-dashboard](https://grafana.com/docs/grafana/latest/developers/http_api/dashboard/#create--update-dashboard), run 
```
result=$(curl https://raw.githubusercontent.com/ossrs/srs-grafana/main/dashboards/helloworld-import.json) && curl -s -H "Content-Type: application/json" -X POST -d "{\"dashboard\":$result,\"overwrite\":true,\"inputs\":[],\"folderId\":0}" http://admin:12345678@localhost:3000/api/dashboards/db
```
