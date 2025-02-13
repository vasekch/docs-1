# Makefile for Sphinx documentation
# You can set these variables from the command line.

SPHINXOPTS    =
SPHINXBUILD   = sphinx-build
PAPER         =
VENV = env/bin/activate
PORT = 8001
BUILDDIR      = build

# Internal variables.
PAPEROPT_a4     = -D latex_paper_size=a4
PAPEROPT_letter = -D latex_paper_size=letter
ALLSPHINXOPTS   = -n -d build/doctrees $(PAPEROPT_$(PAPER)) $(SPHINXOPTS) .

# list the targets that we don't want confused with files in the directory
.PHONY: help clean html dirhtml pickle json htmlhelp qthelp latex changes linkcheck doctest

# "help" is first so that "make" without an argument acts like "make help".
help:
	@echo "Please use \`make <target>' where <target> is one of"
	@echo "  html      to make standalone HTML files"
	@echo "  run       to build the docs, watch for changes, and serve them at http://0.0.0.0:8001"
	@echo "  dirhtml   to make HTML files named index.html in directories"
	@echo "  pickle    to make pickle files"
	@echo "  json      to make JSON files"
	@echo "  htmlhelp  to make HTML files and a HTML help project"
	@echo "  qthelp    to make HTML files and a qthelp project"
	@echo "  latex     to make LaTeX files, you can set PAPER=a4 or PAPER=letter"
	@echo "  changes   to make an overview of all changed/added/deprecated items"
	@echo "  linkcheck to check all external links for integrity"
	@echo "  doctest   to run all doctests embedded in the documentation (if enabled)"
	@echo "  spelling  to check for typos in documentation"


html:
	. $(VENV); $(SPHINXBUILD) -b html $(ALLSPHINXOPTS) build/html
	@echo
	@echo "Build finished. The HTML pages are in build/html."
#  sphinx-build -b html  -n -d build/doctrees -D latex_paper_size=a4  -D latex_paper_size=letter build/html

install:
	@echo "... setting up virtualenv"
	python3 -m venv env
	. $(VENV); pip install -r requirements.txt

	@echo "\n" \
	      "-------------------------------------------------------------------------------------------------- \n" \
		    "* watch, build and serve the documentation: make run \n" \
		    "* check spelling: make spelling \n" \
		    "\n" \
				"enchant must be installed in order for pyenchant (and therefore spelling checks) to work. See \n" \
				"http://docs.django-cms.org/en/latest/contributing/documentation.html#install-the-spelling-software \n" \
	      "-------------------------------------------------------------------------------------------------- \n" \

clean:
	-rm -r $(BUILDDIR)/*

dirhtml:
	. $(VENV); $(SPHINXBUILD) -b dirhtml $(ALLSPHINXOPTS) build/dirhtml
	@echo
	@echo "Build finished. The HTML pages are in build/dirhtml."

pickle:
	. $(VENV); $(SPHINXBUILD) -b pickle $(ALLSPHINXOPTS) build/pickle
	@echo
	@echo "Build finished; now you can process the pickle files."

json:
	. $(VENV); $(SPHINXBUILD) -b json $(ALLSPHINXOPTS) build/json
	@echo
	@echo "Build finished; now you can process the JSON files."

htmlhelp:
	. $(VENV); $(SPHINXBUILD) -b htmlhelp $(ALLSPHINXOPTS) build/htmlhelp
	@echo
	@echo "Build finished; now you can run HTML Help Workshop with the" \
	      ".hhp project file in build/htmlhelp."

qthelp:
	. $(VENV); $(SPHINXBUILD) -b qthelp $(ALLSPHINXOPTS) build/qthelp
	@echo
	@echo "Build finished; now you can run "qcollectiongenerator" with the" \
	      ".qhcp project file in build/qthelp, like this:"
	@echo "# qcollectiongenerator build/qthelp/FeinCMS.qhcp"
	@echo "To view the help file:"
	@echo "# assistant -collectionFile build/qthelp/FeinCMS.qhc"

latex:
	. $(VENV); $(SPHINXBUILD) -b latex $(ALLSPHINXOPTS) build/latex
	@echo
	@echo "Build finished; the LaTeX files are in build/latex."
	@echo "Run \`make all-pdf' or \`make all-ps' in that directory to" \
	      "run these through (pdf)latex."

changes:
	. $(VENV); $(SPHINXBUILD) -b changes $(ALLSPHINXOPTS) build/changes
	@echo
	@echo "The overview file is in build/changes."

linkcheck:
	. $(VENV); $(SPHINXBUILD) -b linkcheck $(ALLSPHINXOPTS) build/linkcheck
	@echo
	@echo "Link check complete; look for any errors in the above output " \
	      "or in build/linkcheck/output.txt."

doctest:
	. $(VENV); $(SPHINXBUILD) -b doctest $(ALLSPHINXOPTS) build/doctest
	@echo "Testing of doctests in the sources finished, look at the " \
	      "results in build/doctest/output.txt."

spelling:
	. $(VENV); $(SPHINXBUILD) -b spelling $(ALLSPHINXOPTS) build/spelling
	@echo
	@echo "Check finished. Wrong words can be found in " \
		"build/spelling/output.txt."

run:
	. $(VENV); sphinx-autobuild $(ALLSPHINXOPTS) build/html --host 0.0.0.0 --port $(PORT)
