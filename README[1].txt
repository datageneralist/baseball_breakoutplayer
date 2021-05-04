
Description:

This package contains instructions and code to obtain the raw baseball data that we used to
develop this model, how to clean that data in the same manner that we cleaned it, how to run
the model we ultimately used to populate the visualization, how to run the visualization,
and how to use the visualization. 

Once everything is operating as expected, you will be able to run the dashboard and sort
through the baseball players and find the ones with the potential for the greatest increase
in their “On Base Plus Slugging” average for the 2021 baseball season. 


Installation:

Directory Setup
1) Download our CODE directory and unzip the files
2) An empty ./data and ./data/cleaned_data directory should exist, if not, create them
3) Download the Lahman Datasets (required) MARCEL (optional) 
	- Lahman - http://www.seanlahman.com/baseball-archive/statistics/ 
	 	- Select 2020 - comma-delimited version
 	- MARCEL Model predictions - https://www.baseball-reference.com/leagues/MLB/2018-projections.shtml 
	 	- This is not needed to run our jupyter notebooks, however, you can review this to compare their predictions to ours.

	- Save Lahman zip file/downloads inside the data directory and unzip
4) Rename the unziped directory containing the Lahman datasets as "csv_data"
	- At this point you should have two directories inside of ./data
		- "./data/cleaned_data"
		- "./data/csv_data"

5) Make sure "data_prep.ipynb" and "xgboost_model.ipynb" are at the same level as ./data
6) Using conda cmd line or terminal, follow the Environment Setup instructions and troubleshooting guide below.
	- be sure to navigate inside the CODE directory so the team116_env.yml and requirements.txt file are in the current working directory.

Environment Setup
1) conda env create -f team116_env.yml
2) conda activate cse6242-team116-env


Troubleshooting Environment Setup
1) If using conda and unable to create the environment from the yml file:
	- conda update --all
	- conda update -n base -c defaults conda
2) If using conda and still unable to create the environment after updating conda
	- create a new conda environment and install the packages listed in the yaml file; allow conda to resolve dependicies
		- conda create --name cse6242-team116-env python=3.8
		- conda install package_name
			- some packages may not be available from default channel, in which case use conda-forge
			- conda install -c conda-forge package_name
			- use pip install package_name as a last resort
3) If using python virtual environment and pip
	- install packages using the versions in requirements.txt


Execution:

Our visualization can be found at https://agent-smithds.github.io/cse6242-final-project/index.html 

Dashboard Instructions

Upon loading, the layout includes a baseball diamond (to facilitate position-centric searches) and a map (to facilitate team-centric searches).
The user can navigate through these shortcuts, or by selecting various search elements from drop down selectors (team, position or individual name).
With each interaction, the output updates to display which players meet the selection criteria and are predicted to have a breakout year.
The display also includes the selected players’ previous years OPS numbers, filtered to a manageable number of players.

Supporting images are dashboard_01.png - _04.png, which are also in the Dashboard_instructions.pdf
