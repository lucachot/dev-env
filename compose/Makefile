MKFILE_DIR := $(dir $(abspath $(lastword $(MAKEFILE_LIST))))

IMAGE_LATEX := localhost/local/dev-latex:latest
IMAGE_CLI   := localhost/local/dev-cli:latest

FRAGMENTS := \
	-f $(MKFILE_DIR)base.yaml \
	-f $(MKFILE_DIR)git-ssh.yaml \
	-f $(MKFILE_DIR)nvim.yaml \
	-f $(MKFILE_DIR)claude.yaml

.PHONY: latex cli

latex:
	IMAGE=$(IMAGE_LATEX) docker compose $(FRAGMENTS) config > $(MKFILE_DIR)compose.yaml

cli:
	IMAGE=$(IMAGE_CLI) docker compose $(FRAGMENTS) config > $(MKFILE_DIR)compose.yaml
