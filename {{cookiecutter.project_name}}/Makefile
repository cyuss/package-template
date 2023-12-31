# Makefile

.DEFAULT_GOAL := help

docker_image_name = "{{ cookiecutter.project_slug }}"
docker_container_name = "{{ cookiecutter.project_slug }}"
repo_name = "{{ cookiecutter.project_slug }}"
version = "{{ cookiecutter.version }}"


help:
	@echo "AVAILABLE COMMANDS"
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf " \033[36m%-30s\033[0m %s\n", $$1, $$2}'

bake: ## Init a poetry env and installing some useful packages (run this first). Install poetry with `pip install poetry`.
	@poetry add loguru
	@echo "Installing dev dependencies."
	@poetry add --group test pytest pytest-cov hypothesis
	@poetry add --group dev radon cloc black mypy fire ruff
	@echo "Installing documentation dependencies."
	# @poetry add --group docs mkdocs-material mkdocs-minify-plugin mkdocs-redirects mkdocstrings mkdocs-autorefs
	@echo "Python 🐍 env set using Poetry 🎉"
	@git init .
	@echo "Coding time! ✨ 🚀"