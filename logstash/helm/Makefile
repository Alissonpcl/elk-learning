default: install

RELEASE := logstash
TIMEOUT := 1200s

install:
	helm upgrade --wait --timeout=$(TIMEOUT) --install --values values.yaml $(RELEASE) elastic/logstash

purge:
	helm del $(RELEASE)
