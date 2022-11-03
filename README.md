#Projectome_finder
This project includes three different notebooks

-Notebook_1__Load_data_transform_object
	-Section A: Load the data from the original data
	-Section B: Define a way so that it is simple to:	
			-save part or all the data
			-load part or all the data


Notebook_2_Building_artifact_library
	-Section C: Building the library of artifacts
			-load data
			-find artifacts
			-save artifacts

Notebook_3_Making_tensor
	-Creates a 5D tensor: "raw_data_to_tensor"
		Dim 0: all electrodes, (0 to 15)
		Dim 1: all muscles (0 to 13)
		Dim 2: all amplitudes (0 to 32)
		Dim 3: all repeats (0 to 11) (since trials are repeated with the same amplitude, max 11x)
		Dim 4: EMG Raw (time array of 1404 EMG values)
		size of tensor: torch.Size([16, 14, 32, 11, 1404])
	-Creates a 3D tensor: "amplitude_data_to_tensor"
		Dim 0: all electrodes, (0 to 15)
		Dim 1: all muscles (0 to 13)
		Dim 2: all amplitudes (32 amplitude values starting from 0.5 to 3.7, if for specific combination no EMG data for specific amplitude, space filled with "nan") 
	-df_muscles: list of muscles with indices
	-df_elecs: list of electrodes with indices
	All data is saved as pickle file 

Notebook_4_Plot_tensor
	-plots max, min and middle amplitude of a elec-muscle combination

Notebook_5_Peak_to_peak_analysis
	-get muscle number from name
	-get data tensor from muscle name
	-get amplitude tensor from muscle name
	-get max EMG for normalisation
	-get peak to peak value
	-get histogram
	-analysing data by plotting histograms


Notebook_x_Cleaning_data
	This notebook is put on hold for now, since we don't focuse on artifact removal anymore
	-Section D: For each artifact:
		-load the data
		-create an artefact-free series (new attribute of object)
		-save the data



