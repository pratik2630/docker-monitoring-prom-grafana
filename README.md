# docker-monitoring-prom-grafana /


mkdir container-monitoring

create/download following files: /
docker-compose.yml /
prometheus.yml /
grafana.ini /

docker-compose up -d


To change Grafana.ini

docker cp grafana:/etc/grafana/grafana.ini ./grafana.ini

make changes

vim Grafana.ini

[smtp]
enabled = true
host = smtp.gmail.com:587
user = your-mail@gmail.com
# If the password contains # or ; you have to wrap it with triple quotes. Ex """#password;"""
password = your-passkey
;cert_file =
;key_file =
skip_verify = false
from_address = your-mail@gmail.com

from_name = Grafana
 

docker cp ./grafana.ini grafana:/etc/grafana/grafana.ini

docker restart container-name
