# srs-grafana

Grafana dashboards for SRS Prometheus exporter and business data, allows you to import to your Grafana.

# Usage

Please download json file and import to Grafana, see [Import a dashboard](https://grafana.com/docs/grafana/latest/dashboards/manage-dashboards/#import-a-dashboard).

You're also able to use curl to import it, see [create--update-dashboard](https://grafana.com/docs/grafana/latest/developers/http_api/dashboard/#create--update-dashboard). For example:

```bash
data=$(curl https://raw.githubusercontent.com/ossrs/srs-grafana/main/dashboards/helloworld-import.json 2>/dev/null)
curl -s -H "Content-Type: application/json" \
    -XPOST http://admin:12345678@localhost:3000/api/dashboards/db \
    --data-binary "{\"dashboard\":${data},\"overwrite\":true,\"inputs\":[],\"folderId\":0}"
```

For node-exporter dashboard, see [grafana-dashboards](https://github.com/rfmoz/grafana-dashboards),

