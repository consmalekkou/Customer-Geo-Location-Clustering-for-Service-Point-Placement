# Service-Point-Placement-By-Customer-Geo-Location-Clustering
### Location, Location, Location When Distance, Distance, Distance Matters 

The location of a physical store is important for any retailer company that relies on a distributed branch network for the promotion of its goods and services. The distance to the nearest service point is an important factor to consider, as it is a measure of convenience for its customers. The initial set-up costs required for the establishment of a new service point should be carefully weighed against the expected benefits, as future relocations or new establishments translate to additional, unnecessary costs. The insights of this model would be useful to the retailer company’s management as it would facilitate data driven decision making regarding the retailer’s physical service point locations.

The purpose of this project is to try to identify the optimal number and placement of physical store locations, for a retailer company that depends on a physical network for the distribution of goods and services to its customers. The target variable is the minimization of the distance to the nearest service point by the retailer’s customers. 

To this extend, we have gathered open-source data to serve as a sample population, and used the k-Means unsupervised clustering algorithm, for the model development. The results of the model are the optimal number and geographical positions of service points for a retailer company, based on the actual point geolocations of the retailer’s customers. The service points proposed by the developed model minimize the distance-to-be-travelled by the customers to the nearest service point, with the least number of service points, resulting to reduced operating costs. 

This project has been developed as a Project in Data Science (COMP592DL), for the MSc in Data Science at the University of Nicosia.

### Project Description

The project has been implemented with both PySpark and Python code. The initial data processign and address translation to geoloctions has been implemented with PySpark, and run on DataProc virtual machines in Google Cloud Platform. The rest of the project was implemented with Python 3.9 and run on local Jupyter notebook. All data soures and output files have been uploaded to a Google Cloud Storage Bucket, with public read access.

#### Initial Data Sources

The initial data source for the model’s sample population was the Cyprus National OpenData Portal(1). More specifically, we have used the following files from the “Μητρώο Εγγεγραμμένων Εταιρειών, Εμπορικών Επωνυμιών και Συνεταιρισμών στην Κύπρο”(2): “Κατάλογος Οργανισμών”, which contains the list of all legal entities of Cyprus that are registered with the Registrar of Companies, and “Κατάλογος Διευθύνσεων Εγγεγραμμένου Γραφείου”, which is a list of all the registered office addresses of legal entities ever registered in Cyprus. The two files could be joined on the address sequence number, present as key in both files. The initial files used for this project are the organisations_51.csv and registered_office_52.csv, to be found in the 'initial data sources.ip'

#### PySpark / Python Code Files

The code files for this project should be executed / viewed in the below order:

1_GeolocationPrjCM_AddressTranslation.ipynb
This file has been implemented with PySpark, and has been ran on DataProc in Google cloud Platform. Address translation has been implemented by the use of the Google Maps Geocoding API. The API Key has been replaced by a dummy code for illustration purposes.
This notebook runs in batches, which are user-defined, and translates all the text addresses provided to their geocoordinates.

2_GeolocationPrjCM_Customers.ipynb
This file and all consecutive notebooks have been implemented with Python 3.9 and ran on local Jupyter notebook installation. 

This notebook merges the two initial datasets with the geolocations from the previous notebook. At the end it calculates the distances of each instance to two sample companies existing service points. The two sample companies are considered to be market competitors over the same set of customers.

3_GeolocationPrjCM_Distances.ipynb
In this notebook, the calculations of the nearest service piint per customer per company are being calculated. After the closest service point has been selected for each customer, we perform some baseline counts that will be used for comparison purposes of the initial status and the suggested model status. 

4_GeolocationPrjCM_Clustering_KMEANS.ipynb
The k-means clustering model is implemented in this notebook. The initial customers have been clustered according to their geolocations into clusters and suggested service points have been derived. Then we have calculated the same metrics as for the 2 companies for comparison purposes. 

5_GeolocationPrjCM_Comparisons.ipynb
In this final notebook we compare the measurements that have been made on the same dataset of customers for the 2 competing companies and the model service points. 

The Technical Report attached contains full project details and model results.

Developed by: Constantia Malekkou

Contact email: constantia.malekkou@gmail.com

Supervised by: Dr. Demetris Trihinas
