# Customer-Geo-Location-Clustering-for-Service-Point-Placement

This project has been developed as a Project in Data Science (COMP592DL), under the MSc in Data Science at the University of Nicosia.

For this project, we have gathered open-source data to serve as a sample population, to demonstrate how the use of machine learning methods, and specifically the k-Means unsupervised clustering algorithm, can provide data driven insight to any company that is interested in the optimal placement of its service points, when the distance to its customers is important.

The results of this model demonstrate that near-optimal locations can be identified, and if utilized can benefit any retailer company. For the sample population examined, the optimal placement revealed that a smaller number of service points when strategically placed leads to reduced operating cost, while simultaneously reducing the distance-to-be-travelled to a service point.  

### Project Description

The project has been implemented with both PySpark and Python code. The initial data processign and address translation to geoloctions has been implemented with PySpark, and run on DataProc virtual machines in Google Cloud Platform. The rest of the project was implemented with Python and run on local Jupyter notebook. All data soures and output files have been uploaded to a Google Cloud Storage Bucket, with public read access.

#### Initial Data Sources

The initial data source for the model’s sample population was the Cyprus National OpenData Portal(1). More specifically, we have used the following files from the “Μητρώο Εγγεγραμμένων Εταιρειών, Εμπορικών Επωνυμιών και Συνεταιρισμών στην Κύπρο”(2): “Κατάλογος Οργανισμών”, which contains the list of all legal entities of Cyprus that are registered with the Registrar of Companies, and “Κατάλογος Διευθύνσεων Εγγεγραμμένου Γραφείου”, which is a list of all the registered office addresses of legal entities ever registered in Cyprus. The two files could be joined on the address sequence number, present as key in both files. The initial files used for this project are the organisations_51.csv and registered_office_52.csv

#### PySpark / Python Code Files

The code files for this project should be executed / viewed in the below order:

1. GeolocationPrjCM_AddressTranslation.ipynb
This file has been implemented with PySpark, and has been ran on DataProc in Google cloud Platform. Address translation has been implemented by the use of the Google Maps Geocoding API. The API Key has been replaced by a dummy code for illustration purposes.
This notebook runs in batches, which are user-defined, and translates all the text addresses provided to their geocoordinates.

2. 
