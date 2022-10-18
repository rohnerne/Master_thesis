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
	-Creates a tensor:
		Alternative A: 2D all trials x (Time-points, Amplitudes, Raw, Elecs(encoded), Muscles(encoded)
		Alternative B: one tensor for each of the above mentioned data (=5 in total)
	The two alternatives exist, since the goal would have been to create a 5D tensor, but the data doesn't have the same amounts of 	columns, and it wouldn't make sense to fill up the muscles& elecs to fit the raw data.

Notebook_3_Cleaning_data
	This notebook is put on hold for now, since we don't focuse on artifact removal anymore
	-Section D: For each artifact:
		-load the data
		-create an artefact-free series (new attribute of object)
		-save the data



