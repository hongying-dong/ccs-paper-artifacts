# ccs-paper-artifacts
This repo stores codes related to the paper submitted to CCS. 

### - Datasets
Due to limitations as described in the paper, we cannot provide the full ClientHello dataset and the Lab Dataset. Instead, we provide the following datasets in the **datasets** folder:
  - A sub ClientHello dataset, containing a random sample of 100 rows from the full ClientHello dataset
  - A full Server Certificate datasets (parsed), from three geolocations: New York, Frankfurt, and Singapore
  - A full dataset containing crt.sh query results
  - A full Smart TV dataset (parsed)
 
### - Analysis Code
  - We performed analysis mainly using Jupyter Notebooks, and we provide all the notebooks in the **notebooks** folder. We named each notebook based on the its content. Note that analysis in **Case Study: Section 6.2 PKI on the local network** were performed using Wireshark, so there are no related notebooks. 

### - Notebook status and running notebooks
  - All notebooks are in the status of showing all statistics/tables/figures that we put in the paper.
  - Running notebooks of the server-side analysis (Section 5.1, 5.2, 5.3, 5.4, 5.6(Geolocations) and Section 6.1) with the provided server-side datasets should generate the same results as the original notebooks show. Note that the relative path defined in notebooks is: ```"../datasets/dataset_name"```.
  - Running notebooks of the client-side analysis (Section 4.1, 4.2, 4.3, 5.5(TLS and PKI Correlation)) with the provided **partial** dataset will result in **different** results as compared to what the original notebooks show. Note that the relative path defined in notebooks is also: ```"../datasets/dataset_name"```. 
  - Some libraries (as imported in the first code block in each notebook) may need to be installed to run notebooks. 
