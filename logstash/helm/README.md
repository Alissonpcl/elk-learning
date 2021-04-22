> This project was built using a mix of sso and elasticsearch examples that can be found in [https://github.com/elastic/helm-charts/tree/master/logstash/examples](https://github.com/elastic/helm-charts/tree/master/logstash/examples).

# Logstash

This example deploy Logstash which connects to Elasticsearch (see [values][]).


## Usage

* Deploy [Elasticsearch Helm chart](../../elasticsearch).

* Deploy Logstash chart: `make install`

Maybe it might be necessary to add elastic repo before the command above: `helm repo add elastic https://helm.elastic.co`.

* You can now setup a port forward to query Logstash indices:

  ```
  kubectl port-forward svc/elasticsearch-master 9200
  curl localhost:9200/_cat/indices
  ```


## Testing

You can also run [goss integration tests][] using `make test`


[elasticsearch helm chart]: https://github.com/elastic/helm-charts/tree/master/elasticsearch/examples/default/
[goss integration tests]: https://github.com/elastic/helm-charts/tree/master/logstash/examples/elasticsearch/test/goss.yaml
[values]: https://github.com/elastic/helm-charts/tree/master/logstash/examples/elasticsearch/values.yaml
