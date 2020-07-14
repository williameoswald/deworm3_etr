![Deworm Logo](/image/logo.png)

# Electronic Treatment Register

We developed the electronic treatment register for the DeWorm3 Project, a cluster-randomised, controlled trial in Benin, India, and Malawi testing the feasibility of interrupting transmission of soil-transmitted helminths through community-wide mass drug administration. The electronic treatment register was designed in xlsform logic, deployed via the SurveyCTO mobile data collection platform, and implemented on smartphones running the Android operating system. The versatile system enables collection of census and treatment status information, facilitates data aggregation and visualisation, and permits real-time feedback loops during implementation of mass drug administration.

For further information please read our description in [*Global Health Action*](https://doi.org/10.1080/16549716.2020.1785146). 

### Prerequisites

The provided xlsform is designed for deployment via SurveyCTO, for which you will need a subscription. For further information, please visit [**SurveyCTO**](https://www.surveycto.com). We have not tested the xlsform in Open Data Kit, though it should be usable barring some features. 

Information for setting up SurveyCTO Collect and securing and encrypting Android devices is available [here](https://www.nhm.ac.uk/content/dam/nhmwww/our-science/our-work/sustainability/deworm3/DeWorm3_SOP_901.%20Set%20up%20mobile%20data%20collection%20devices%20V3.pdf#).

### Files

**Electronic Treatment Register.xlsx** - xlsform, **version: 2020071401**

The DeWorm3 project sites each relied upon compiled registries of villages, schools, and field officers. These registries are attached to the Electronic Treatment Register to allow users to select their identification number and select village and school as preloaded choices within the form. These registries are fixed and are only used to preload information in the Electronic Treatment Register. Here we have provided template .csv files to show the structure of these attached registries. 

**master_village_registry** - Village registry template. For all DeWorm3 activities, villages are the lowest level administrative unit (level 1) and nested in up to four higher units. 'level1_id' refers to a unique numeric identifier for each village unit and 'level1' is the village name. 'intervention' indicates whether villages nested within clusters (level2) were randomised to the intervention (1) or control (0) arm. Dependencies within the electronic treatment register rely on this value, but this can be set to '1' for treatment activities occurring in all communities.

**master_officer_registry** - Field officer registry template. 'officer_id' is a unique numeric identifier for each field officer along with their name in 'officer_name'. This registry permits users of the electronic treatment register to select their name within the form and record their ID in the dataset. 'active' indicates (yes=1/no=0) whether an officer was active during the current activity.

**master_school_registry** - School registry template. 'school_id' is a unique numeric identifier for each school within the DeWorm3 study site. 'school' refers to the school name. 

**master_monitoring** - This .csv file contains the monitoring server dataset to which aggregated household visit-level information is published with a unique 'monitoring_key' from the Electronic Treatment Register. Data is published in a single direction from the Electronic Treatment Register to this dataset and household visit-level records are updated to show revisits and track numbers treated, etc. This aggregated and pseudonymised dataset can then be published via SurveyCTO to Google Sheets for visualisation or linked directly to a dashboard markdown in R (coming soon!). 

**master_treatment_list** - This .csv contains the list of households to be targeted for treatment. 'key' refers to a unique UUID string that is used to reference and overwrite rows within the dataset. This can be pre-populated using available household census data or populated using the Electronic Treatment Register as new households are added. 

### Installing

For instructions on how to load a xlsform, please visit [**SurveyCTO**](https://www.surveycto.com).

The fixed registries need to be manually uploaded as server datasets on your SurveyCTO server and then attached to the Electronic Treatment Register. This attachment will ensure that the information is preloaded within the form.

After uploading the xlsform, the easiest way to set up the treatment list and monitoring datasets is to upload the provided .xml files. Within SurveyCTO, select the option to 'add server dataset' and then select 'New dataset from definition.' Select the relevant xml and select 'Upload'. Doing so will automatically create a server dataset with the required columns and create the  linkage to the values in the xlsform, so data are published from the form to update the relevant fields in the treatment list and monitoring datasets. You will then need to upload and replace the treatment list dataset with your initial household treatment listing, but the monitoring dataset can be left empty to be populated when forms are submitted.

## Contributors

Please contact [me](https://www.lshtm.ac.uk/aboutus/people/oswald.william) with any questions or suggestions.

[William Oswald](https://github.com/williameoswald), [David Kennedy](https://github.com/dsbkennedy), Jasmine Farzana, Saravanakumar Puthupalayam Kaliappan, Eloic Atindegla, Parfait Houngbégnon, Alvin Chisambi, Stefan Witek-McManus, Sean R. Galagan, Mira Emmanuel-Fabula, Marie-Claire Gwayi-Chore, Hugo Legge, Elodie Yard, Khumbo Kalua, Moudachirou Ibikounlé, Sitara Swarna Rao Ajjampur, Arianna Rubin Means, Kristjana H. Ásbjörnsdóttir, Katherine E. Halliday, Judd L. Walson on behalf of the DeWorm3 Trials Team

## Citation

If you use the Electronic Treatment Register in a project, please cite:

```
Oswald WE, Kennedy DK, Farzana J, et al. Development and application of an electronic treatment register: A system for enumerating populations and monitoring treatment during mass drug administration. Global health action. 2020; https://doi.org/10.1080/16549716.2020.1785146.
```

## License

The Electronic Treatment Register and xlsform are made available for use under a CC BY-NC-SA 4.0 license (https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode).
