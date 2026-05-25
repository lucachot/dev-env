IMAGE_BASE  := localhost/local/dev-base:latest
IMAGE_CLI   := localhost/local/dev-cli:latest
IMAGE_LATEX := localhost/local/dev-latex:latest

.PHONY: all base cli latex clean
all: latex

base: Containerfile.base
	podman build -f Containerfile.base -t $(IMAGE_BASE) .

cli: Containerfile.cli base
	podman build -f Containerfile.cli -t $(IMAGE_CLI) .

latex: Containerfile.latex cli
	podman build -f Containerfile.latex -t $(IMAGE_LATEX) .

clean:
	-podman rmi $(IMAGE_LATEX)
	-podman rmi $(IMAGE_CLI)
	-podman rmi $(IMAGE_BASE)
