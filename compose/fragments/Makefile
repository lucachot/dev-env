MKFILE_DIR  := $(dir $(abspath $(lastword $(MAKEFILE_LIST))))

IMAGE_LATEX := localhost/local/dev-latex:latest
IMAGE_CLI   := localhost/local/dev-cli:latest

COMMON := \
	-f $(MKFILE_DIR)base.yaml \
	-f $(MKFILE_DIR)git-ssh.yaml \
	-f $(MKFILE_DIR)nvim.yaml \
	-f $(MKFILE_DIR)claude.yaml

.PHONY: up-latex up-cli down

up-latex:
	IMAGE=$(IMAGE_LATEX) docker compose $(COMMON) up -d

up-cli:
	IMAGE=$(IMAGE_CLI) docker compose $(COMMON) up -d

down:
	docker compose down
