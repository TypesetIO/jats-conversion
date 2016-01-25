#TMPDIR := $(shell mktemp -d)
#trap "rm -rf $TMPDIR" EXIT

.PHONY: fetch nlm jats pmc

fetch: | jats

# Archive files
DOWNLOADS := /tmp/downloads

$(DOWNLOADS):
	mkdir -p $(DOWNLOADS)

# JATS DTD

jats: | jats/archiving/1.1 jats/articleauthoring/1.1

# JATS 1.1

# archiving
# "test" = version of the DTD with no xml:base
jats/archiving/1.1: | $(DOWNLOADS)/jats-archiving-dtd-1-1.zip
	mkdir -p jats/archiving/1.1 jats/articleauthoring/1.1
	unzip $(DOWNLOADS)/JATS-Archiving-1-1-MathML3-DTD.zip -d jats/archiving/1.1

$(DOWNLOADS)/jats-archiving-dtd-1-1.zip: | $(DOWNLOADS)
	wget -c -P $(DOWNLOADS) ftp://ftp.ncbi.nih.gov/pub/jats/archiving/1.1/JATS-Archiving-1-1-MathML3-DTD.zip

# articleauthoring
jats/articleauthoring/1.1: | $(DOWNLOADS)/jats-articleauthoring-dtd-1-1.zip
	mkdir -p jats/articleauthoring/1.1
	unzip $(DOWNLOADS)/JATS-Authoring-1-1-MathML3-DTD.zip -d jats/articleauthoring/1.1

$(DOWNLOADS)/jats-articleauthoring-dtd-1-1.zip: | $(DOWNLOADS)
	wget -c -P $(DOWNLOADS) ftp://ftp.ncbi.nih.gov/pub/jats/articleauthoring/1.1/JATS-Authoring-1-1-MathML3-DTD.zip
