# Heat_Index_Research_Latest

Hello. This code lets you compare Lu and Romps' (2022) Heat Index algorithm to others' (named in the notebooks. Lu and Romps' (2022) algorithm is available in Python, R, and Fortran code at https://romps.berkeley.edu/papers/pubs-2020-heatindex.html#:~:text=To%20extend%20the%20heat%20index,observable%20measure%20of%20physiological%20stress.

To run the code, you will need some spatial data. I used ERA5-Land data at the hourly level for the Limpopo province of South Africa. This data can be acquired using step 1 below.

Many files below have a back-end equivalent. While you need to download all files, you will only need to edit content, such as file paths to your data, in the front-end files.

The following files (Jupyter Notebooks and not Python files – for your editing convenience) need to be executed in order:
- **Step 1:** Step_1_ERA5_Data_Requests.ipynb OR Step_1_ERA5-Land_Data_Requests.ipynb depending on what spatial resolution you want
  - You will need a Copernicus (CDS) account and to specify your CDS API Key. See the following link for a tutorial: https://ecmwf-projects.github.io/copernicus-training-c3s/cds-tutorial.html
   - You can easily find the coordinate bounds using this helpful tool: https://boundingbox.klokantech.com/.
- **Step 2:** Step_2_Creating_and_concatenating_cubes.ipynb
   - This will create Iris "cubes" from the individually requested files from Step 1.
- **Step 3**: Step_3_Cube_creation_frontend.ipynb
  - This will create Heat Index cubes for the first 21 algorithms, to be used in Step 5
- **Step 4**: Step_4_Algorithm_22_Processing.ipynb
  - This will create the final Heat Index cube, using Lu and Romps' (2022) algorithm. It uses multiprocessing, so ensure you have sufficient CPUs and RAM.
- **Step 5**: Step_5_Data_Analysis_frontend.ipynb
  - Creates spatial plots, time series plots, and tables to visualise the data

**Useful tips**
- Don't worry about the equivalent "backend" files unless you'd like to make some changes to the outputs
- If files crash, batch process data by extracting subsets of the cubes and then concatenating them.
