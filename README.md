# HuggingFace
Testing and Running HuggingFace Models and just having fun

[![riaz](https://circleci.com/gh/riaz/HuggingFace/tree/v0.0.1.svg?style=svg)](https://circleci.com/gh/riaz/HuggingFace/?branch=v0.0.1)


### Setup


	# Create a new conda environment, running python 3.9
	conda create -n huggingface python=3.9

	# Install huggingface transformers conda package
	conda install -c huggingface transformers

	# Install Flax conda package , a NN lib for JAX [Autograd + XLA]
	conda install -c conda-forge flax

	#Intalling Pytorch and related packages
	conda install pytorch torchvision torchaudio -c pytorch

	#Installing tox
	pip install tox

	# Saving envionment into environment.yml for CI/CD
	conda env export > environment.yml


### Developement

	Make sure you name the commits after JIRA tickets/ meaningful branch
	And Create Tags for Important Commits, which become the release versions

	git checkout -b init_commit

	git add *

	git commit -m "Initial commit"

	git tag v0.0.1


### Next we will try to publish package to PyPi

	# Build  - creates wheels in dist
	tox -e build

	# Publish to PyPi Test
	tox -e publish

	# Example Publish Link
	https://test.pypi.org/project/HuggingFace/0.0.2/

	# Publishing to PyPi
	tox -e publish -- --repository pypi

### Tox How-To

	# Build a package in isolation
	tox -e build

	# Clean old builds
	tox -e clean

	# Create docs for the project
	tox -e docs

	# Create/Invoke doc tests
	tox -e doctests

	# Check for broken links in the documentation
	tox -e linkcheck

	# Publish the package to a package index server
	tox -e publish
