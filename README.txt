********************************************************************
D R U P A L    M O D U L E
********************************************************************

Name: taxonomy_nco
Authors:  Russell Blakeborough & Peter Brownell
Sponsor: School of Everything [www.schoolofeverything.com]
Drupal: 5.x

********************************************************************
DESCRIPTION:

This module uses Normalised Co-occurrence data to find 
similarities between taxonomy terms. It is completely dependent on 
data which it expects to find in a database table called 
taxonomy_nco

The data in the taxonomy_nco table would normally be created by the 
companion module taxonomy_nco_analysis 

function taxonomy_nco_similar_terms allows other modules to query the
NCO table to find related terms for a given NCO and intersection
cutoff value.

function theme_taxonomy_nco_related_terms($tids, $minimum_nco) gives
a themed set of taxonomy links.
 
function theme_taxonomy_nco_skos_rdf gives RDF SKOS serialisation XML
to express similarities found by NCO.
 
function theme_taxonomy_nco_skos_rdfa gives RDFa inline SKOS
serialisation to express similarities found by NCO.
 
Views argument handler taxonomy_nco gives a taxonomy view filter for 
a given term and similar terms. The NCO cutoff value is passed in
the option field.

********************************************************************
INSTALLATION:

It is assumed that you have Drupal up and running.  Be sure to
check the Drupal web site if you need assistance.  If you run into
problems, you should always read the INSTALL.txt that comes with the
Drupal package and read the online documentation.

You will need a large vocabulary to give enough data for this
module to find statistically significant co-occurence between terms.

- Install the taxonomy_nco_analysis module.

- Install this module & enable it.

- If you're intested in clustering you might like to check out the
  code of the clustering module. Otherwise don't enable it.

********************************************************************
CONFIGURATION:

Check that you have the right vocabulary set in the defines at the
top of taxonomy_nco_analysis.module - the default is vocabulary 1

DEFINE('TAXONOMY_NCO_VOCABULARY', 1); // $vid to analyse

- Use the taxonomy_nco_analysis admin interface to run the big batch 
process. This runs on consecutive cron runs and may take some time.

- Sort out some output from this module. Options are:
  - taxonomy_nco_similar_terms
  - theme_taxonomy_nco_related_terms
  - theme_taxonomy_nco_skos_rdfa
  - theme_taxonomy_nco_skos_rdf
  - Views argument handler taxonomy_nco
  
(see above DESCRIPTION: and inline comments in taxonomy_nco.module)

********************************************************************
ACKNOWLEDGEMENTS:

www.schoolofeverything.com


