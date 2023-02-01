#Projectome_finder
This project includes different notebooks  which all were combine to "Notebook_combined" 
and two different datasets: artifact data and robins data




## Notebook_combined

combined_NB_31.01.ipynb

	-Load data (muscles) and simulation (roots)
	-plot recruitment curves

	-process recruitment
		- Heatmap
		- Sigmoid fit

	-Evaluate: combine roots and muscles
		- Combine activation pattern (muscles, roots)
		- Compare projectome (from paper) with generated
		- Plot Heatmap (Spinalcord, projectome)

## Notebook evaluation

	-Evaluate: combine roots and muscles
	

## Notebook_muscles

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

	-Plot Filtered EMG
	-EMG Processing: plot peak to peak values = recruitment curves
		
	-Muscle recruitment processing
		-A: Heat map
			-Normalisation of data
			-build heat map ( with and without interpolation)
			-plot heatmap
		-B: Fit recruitment to sigmoids
			-with max value set by data
			-with interpolated max value (higher than data)


## Notebook_roots

Notebook_9_Loading_Neuron_Sim_Results
	-Load the simulations 
	-Restructure it to a df
	-Save it as pickle file

Notebook_10_Load_roots_simulation
	-Plot the roots recruitment curve
	-build and plot the heat map
	-build and plot the sigmoid curve

## Notebooks on hold

Notebook_x_Cleaning_data

	This notebook is put on hold for now, since we don't focus on artifact removal anymore
	-Section D: For each artifact:
		-load the data
		-create an artefact-free series (new attribute of object)
		-save the data

## Notebook_artifacts

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



