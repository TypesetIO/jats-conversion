# JATS conversion and validation

Check an XML file against:
 * [JATS Article Publishing DTD](http://jats.nlm.nih.gov/publishing/tag-library/1.1d1/)
 * [PMC Style Checker](http://www.ncbi.nlm.nih.gov/pmc/tools/stylechecker/)

Convert and validate against:
 * [CrossRef Deposit Schema](http://help.crossref.org/#deposit_schema)
 * [DataCite Deposit Schema](http://schema.datacite.org/)
 * [DOAJ Deposit Schema](http://www.doaj.org/doaj?func=loadTempl&templ=uploadInfo)

## Usage

* Run ```cd schema && make fetch``` to fetch all the resources.
* Run ```tests/validate.sh filename``` to validate a JATS XML file.
* Output: any validation errors; NLM style report; HTML article preview.

## TODO

* JS rules for validating the HTML
* Microdata extraction tests


## NOTE:
For testing against a particular dtd, just add the following below <?xml version="1.0"?> command in your xml file.

```shell
 <!DOCTYPE article PUBLIC "-//NLM//DTD JATS (Z39.96) Journal Archiving DTD v1.1 20120330//EN"
    "file://"{{LOCATION}}>

 example of {{Location}}: home/shanu/jats-conversion/schema/jats/archiving/1.1/JATS-Archiving-1-1-MathML3-DTD/JATS-archivearticle1-mathml3.dtd

```

The JATS-Archiving-1-1-MathML3-DTD is the entire folder containing the .dtd modules and .ent modules. You could download the zip file from ftp://ftp.ncbi.nlm.nih.gov/pub/jats/archiving/1.1/