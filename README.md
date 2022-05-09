# CCS Paper Artifacts
This repo stores codes related to the paper submitted to CCS. 

### - Datasets
Due to limitations as described in the paper, we cannot provide the full ClientHello dataset and the Lab Dataset. Instead, we provide the following datasets in the **datasets** folder:
  - A sub ClientHello dataset, containing a random sample of 100 rows from the full ClientHello dataset:
      - ```sample_100.csv``` (a random sample of 100 rows from the full ClientHello dataset, with visited SNIs)
  - A ciphersuite-mapping dataset: ```ciphersuite_map.csv``` (to map ciphersuite code to actual algorithms)
  - A full dataset containing all SNIs that 2014 IoT devices talked to: ```sni_used_to_generate_pcaps.parquet```
  - A full Server Certificate datasets, from three geolocations: New York, Frankfurt, and Singapore:
      - ```ny_serv_withcrt.parquet``` (parsed server-side dataset captured from New York, merged with crt.sh query results)
      - ```ny_zeek_sslx509.csv``` (Zeek processed New York capture, ssl.log merged with x509.log on certificate fingerprints for info on leaf certificates/chains)
      - ```ny_zeek_x509.csv``` (Zeek processed New York capture, for info on intermediate/root certificates)
      - ```ff_serv.parquet``` (parsed server-side dataset captured from Frankfurt)
      - ```sin_serv.parquet``` (parsed server-side dataset captured from Singapore)
  - A full dataset containing crt.sh query results: ```ct_res.csv```
  - A host-blocking list: ```hosts-blocklists.txt```(reference: https://github.com/notracking/hosts-blocklists/)
  - A full Smart TV dataset
 
### - Analysis Code
  - We performed analysis mainly using Jupyter Notebooks, and we provide all the notebooks in the **notebooks** folder. We named each notebook based on the its content. Note that analysis in **Case Study: Section 6.2 PKI on the local network** were performed using Wireshark, so there are no related notebooks. 

### - Notebook status and running notebooks
  - All notebooks are in the status of showing all statistics/tables/figures that we put in the paper.
  - Running notebooks of the server-side analysis (Section 5.1, 5.2, 5.3, 5.4, 5.6(Geolocations) and Section 6.1) with the provided server-side datasets should generate the same results as the original notebooks show. Note that the relative path defined in notebooks is: ```"../datasets/dataset_name"```.
  - Running notebooks of the client-side analysis (Section 4.1, 4.2, 4.3, 5.5(TLS and PKI Correlation)) with the provided **partial** dataset will result in **different** results as compared to what the original notebooks show. Note that the relative path defined in notebooks is also: ```"../datasets/dataset_name"```. **To run with the partial dataset, please replace ```2014dev_fps.csv``` or ```2014dev_fps_with_sni.parquet``` with ```sample_100.csv```** (```pd.read_parquet``` would need to be changed into ```pd.read_csv``` if want to read in a parquet file instead of the original csv).
  - Some libraries (as imported in the first code block in each notebook) may need to be installed to run notebooks. 
