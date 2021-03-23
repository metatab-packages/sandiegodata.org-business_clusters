# San Diego Business Clusters

This dataset processes the City of San Diego Master Business file to add
geocoded addresses and links to business clusters. San Diego publishes two
lists of businesses, which are based on payment of the San Diego City business
tax: the Master Business File, and a [SANGIS file that includes geographic
information.
](https://data.sandiegodata.org/dataset/sangis-org-business-sites/) Unfortunatel
y, these files are quite different and cannot be linked. The SANGIS file is
oriented toward the tax assessors parcel that the business occupies, and the
Master Business List has account numbers and addresses, but there is no common
key between the files.

The files in this package add address geocodes to the Master Business List, and
links the businesses to clusters of businesses. The Clusters are created by
collecting nearby businesses from Open Street Map data. The cluster types are:

* NA: No cluster, 31787 businesses
* shop: OSM tags 'shop', 'clothes', 'supermarket', 'bank', 'laundry', 'parking',  14615 businesses
* ent: Entertainment, OSM tags 'cafe', 'restaurant', 'bar', 14320 businesses
* casual: Fast food and convenience stores, OSM tags  'fast_food', 'convenience', 10991 businesses

The ``sd_business_clusters`` file has the clusters and their WKT geographies.
The ``sd_custered_businesses`` links San Diego businesses to clusters, and a
single business may be in more than one cluster because the clusters of
different tyoes overlap.

## NAICS Codes

It appears that the  NAICS codes used in the Master Business List are vintage 2007. The code '72221' appears frequently, which is valid in 2007 NAICS, but not in 2012 or 2016 NAICS. 

## Geocoding

The geocoding was performed with a local installation of Pelias. There are some notable errors in the geocoding. For instance, Ba Ho Liquor and Deli, with address of '4031 AVATI DR SUITE I SAN DIEGO 92117-4403, CA', was geocoded to 4144 Avati, moving the location from a neighborhood mini-mall to a residence. It is unknown how many such error there are, so use the geocodes with caution. 
