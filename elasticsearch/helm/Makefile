default: test

RELEASE := elasticsearch
TIMEOUT := 1200s

install:	
	helm upgrade --wait --timeout=$(TIMEOUT) --install --values values.yaml $(RELEASE) elastic/elasticsearch

test: install
	helm test $(RELEASE)

purge:
	helm del $(RELEASE)
