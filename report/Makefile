PROJECT=main

build:
	docker compose run --rm latex-builder latexmk -pdf -interaction=nonstopmode -halt-on-error $(PROJECT).tex

watch:
	docker compose run --rm latex-builder latexmk -pdf -pvc -f $(PROJECT).tex

clean:
	docker compose run --rm latex-builder latexmk -c

clean-all:
	docker compose run --rm latex-builder latexmk -C
