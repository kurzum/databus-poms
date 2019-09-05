# Geonames parsed to NTriples 
Geonames provides a malformed RDF/XML dump, we parsed it, because we needed it in our project. 


## Procedure
Johannes, Marvin and me needed a while to finally get it working with `parallel`. There were quite a few scripts out there already like [this one](https://swebdev.wordpress.com/2012/10/01/loading-geonames-in-virtuoso/) from 2012, so the problem seems to stay with us.   
```
cat all-geonames-rdf.txt | grep -v "^http" | parallel --pipe -N1 rapper -i rdfxml - urn:base > all-parallel.nt 2> all-paralle.log
```
We are hosting this for us mainly, but as long as this there, feel free to download and use it. Hopefully, it will save you some hours of work. 
Also I put some extra effort in this docu as a demo for the databus. Copying Retrieval date, Source and License is recommended, as you also sign this with your private key. But I am very sure, I did copy and paste it correctly.  

## Source
retrieved: September 5th, 2019
from:  http://www.geonames.org/ontology/documentation.html
*[RDF dump](http://download.geonames.org/all-geonames-rdf.zip) with 11701589 features and about 176 mio rdf triples (2018 03 11). The dump has one rdf document per toponym on every line of the file. Note: The file is pretty large. Make sure the tool you use to uncompress is able to deal with the size and does not stop after 2GB, an issue that happens with some old (windows) tool versions.* 

## License 
retrieved: September 5th, 2019
from: http://download.geonames.org/export/
copied relevant parts:
* "free : GeoNames data is free, the data is available without costs."
* "cc-by licence (creative commons attributions license). You should give credit to GeoNames when using data or web services with a link or another reference to GeoNames."
* "commercial usage is allowed"
* "'as is' : The data is provided "as is" without warranty or any representation of accuracy, timeliness or completeness."

