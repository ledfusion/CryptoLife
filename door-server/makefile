.DEFAULT_GOAL := info
.PHONY: info dev

PATH  := node_modules/.bin:$(PATH)
SHELL := /bin/bash

###############################################################################
## INFO
###############################################################################

info:
	@echo "Available actions:"
	@echo
	@echo "  $$ make         Runs 'make info' by default"
	@echo "  $$ make info    Shows this text"
	@echo "  $$ make init    Install dependencies"
	@echo
	@echo "  $$ make dev     Start the server for development"
	@echo "  $$ make run     Start the server"
	@echo "  $$ make deploy  Deploy to Heroku"
	@echo

###############################################################################
## RECIPES
###############################################################################

init:
	@yarn || npm install

dev: 
	@PORT=7000 nodemon server

run:
	@if [ ! -f "../blockchain/build/__contracts_Bookings_sol_Bookings.abi" ] ;\
	then cd ../blockchain ; make build ;\
	fi
	@PORT=7000 node server

deploy:
	@git push heroku master
