SHELL := /bin/sh
CORTEX_RULER_ADDR := http://127.0.0.1:9009
CWD = $(abspath $(patsubst %/,%,$(dir $(abspath $(lastword $(MAKEFILE_LIST))))))
JOB_TARGET = up-instances

.PHONY: all
all: $(JOB_TARGET)

$(JOB_TARGET): %:%
	@echo "Submitting $(CWD)/$@.yaml ..."
	@curl -XPOST $(CORTEX_RULER_ADDR)/api/v1/rules/fake -H 'Content-type: application/yaml' -d "`cat $(CWD)/$@.yaml`"

