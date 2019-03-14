
UNAME := $(shell uname)

ifeq ($(UNAME),Darwin) 
define terminal
	osascript -e 'tell application "Terminal" to do script "cd $(PWD); $1"'
endef
endif
ifeq ($(UNAME),Linux)
define terminal
	sh -c "cd $(PWD);$1"
endef
endif
install:
	pip install -r requirements.txt


demo:
	$(call terminal, python server.py)
	sleep 3
	@echo "==============================================================================="
	@echo "Get the info"
	@echo "==============================================================================="
	curl http://localhost:8080/cloudmesh/cpu
	@echo
	@echo "==============================================================================="

