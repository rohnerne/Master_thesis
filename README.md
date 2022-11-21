#Projectome_finder
This project includes eight different notebooks and two different datasets: artifact data and robins data


## Notebook_artifacts_ds

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
	All data is saved as pickle file /csv file

Notebook_4_Plot_tensor

	-plots max, min and middle amplitude of an elec-muscle combination

Notebook_5_Peak_to_peak_analysis

	-get muscle number from name
	-get data tensor from muscle name
	-get amplitude tensor from muscle name
	-get max EMG for normalisation
	-get peak to peak value
	-get histogram
	-analysing data by plotting histograms


## Notebook_Robins_ds

Notebook_6_Notebook_6_Loading_Mat_from_RD

	-Load the data from matlab format
	-Restructure it to a class
	-Save it as pickle file

Notebook_7_Create_tensor_filteredData

	-Creates a 5D tensor with filtered data "filtered_data_to_tensor"
		Dim 0: all electrodes, (0 to 15)
		Dim 1: all muscles (0 to 13)
		Dim 2: all amplitudes (0 to 40)
		Dim 3: all repeats (0 to 39) (since trials are repeated with the same amplitude, max 40x)
		Dim 4: EMG Raw (time array of 1404 EMG values)
		size of tensor: torch.Size([16, 16, 40, 39, 1000])

	-Creates a 5D tensor with peak to peak value per trial "peak2peak_data_to_tensor"
		Dim 0: all electrodes, (0 to 15)
		Dim 1: all muscles (0 to 13)
		Dim 2: all amplitudes (0 to 40)
		Dim 3: all repeats (0 to 39) 
		Dim 4: peak to peak value (1 value)
		size of tensor: torch.Size([16, 16, 40, 39, 1])

	-Creates a 3D tensor: "amplitude_filtereddata_to_tensor"
		Dim 0: all electrodes, (0 to 15)
		Dim 1: all muscles (0 to 13)
		Dim 2: all amplitudes (40 amplitude values starting from 0.2 to 4.9, if for specific combination no EMG data for specific amplitude, space filled with "nan")

Notebook_8_Analysis
	-Plots the recruitment curve based on peak to peak values, for every electrode
	-on hold: Plots the recruitment curve based on integral of the filtered data, for every electrode

## Notebooks on hold
Notebook_x_Cleaning_data
	This notebook is put on hold for now, since we don't focuse on artifact removal anymore
	-Section D: For each artifact:
		-load the data
		-create an artefact-free series (new attribute of object)
		-save the data



