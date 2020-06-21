#change this
CHARTNAME = helm-guestbook
ENV ?= dev
RELEASE_NAME = $(CHARTNAME)
DESCRIPTION ?= $(RELEASE_NAME) #ideally this is commit hash / release-version (unique)

lint:
	helm install --debug --dry-run --values=values.$(ENV).yaml .
	helm lint --values=values.$(ENV).yaml

release:
	helm upgrade --install --description=$(DESCRIPTION) $(RELEASE_NAME) .

delete:
	helm delete --purge $(RELEASE_NAME)

.PHONY: release delete
