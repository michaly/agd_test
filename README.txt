Python version:  3.6. 
OS: macOS High Sierra, version 10.313.6, 64bit.

Required packages:
	- numpy
	- pandas
	- matplotlib
	- sklearn
	- csv
	- unidecode 

** All packages (except unidecode) exist under Anaconda3. To install unidecode via conda run: 'conda install -c anaconda unidecode'

Required files under the project directory:
	- mappinghotelsdataset.xlsx: the provided data file. The data file path/name can be configured in agd_test.ipynb (input_file_path). 
	- agd_test.ipynb: the Jupyter notebook.

To run the script on NEW dataset:
1. Configure the parameters in the first cell: input_file_path, p1_sheet_name.
2. No need to run the following cells (where first line in cell is):
	a. # # # # evaluate model on example data with a range of total_sim_threshold - help defininf the parameter value # # # # # 
	b. # # # # # evaluate model on example data with the chosen total_sim_threshold parameter value # # # # #
3. Run the (last) cell, where its first line is:
	# # # # # # predict matches between P1 & P2 data # # # # # # 
4. To evaluate the the result:
	a. Load the mappings.csv into a pandas.DataFrame (or simply use pred_matched_keys_list)
	b. Load the known/true mapping keys list into a pandas.DataFrame (e.g. known_match_list)
	c. Run:
		 precision, recall, fbeta = estimateResultsPerformance(pred_matched_keys_list, known_match_list)
	d. Hopefully precision and recall will be high enough :)    
