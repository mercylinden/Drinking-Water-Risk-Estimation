# Drinking-Water-Risk-Estimation
Human health risk estimation based on sampling of drinking water disinfection byproducts and microbial risks in distribution systems. 

This repository contains the most recent iterations of the analysis code that was constructed to interpret disinfection byproduct and microbial monitoring data from drinking water distribution system monitoring. This approach constructs a point estimate of risk, and does not account for changes in risk between point of monitoring and tap. 

# Required Downloads
This model relies upon the tidyverse, data.table, mpower and EnvStats packages, which are loaded at the start of the code but must be installed before use using install.packages on the local operating system. 

This code also requires 2 unique input databases, which are available in the ToxRef folder here. 

# Input Data Format - Disinfection Byproducts
This code anticipates disinfection byproduct data to be included as wide data. Standard Abbreviations, as seen in the 'totalDBP' reference file, are used for column headers. 
| SampleID | Metadata | DBP1 | DBP2 | Etc... |
| ---- | ----- | ----- | ----- | -----|
| ID1 | Concentration | Concentration | Concentration |Concentration |
| ID2 | Concentration | Concentration | Concentration |Concentration |
| Etc... | Concentration | CConcentration |Concentration |Concentration |

# Input Data Format - Microbial Data
The code here anticipates a summary of 16S sequencing at the Genus level. The current iteration of the coed is set up to run risk assessment for Legionella pneumophila, Mycobacterium avium, and Clostridium perfringens, but can be modified to run risk assessment for any of the available QMRA models in the reference data by modifying the 'qmra' variable. These calculations assume that an environmentally appropriate percentage of a genus is pathogenic.

The expected format of input data is as follows:

| Genus | Date1 | Date2 | Date3 | Etc... |
| ---- | ----- | ----- | ----- | -----|
| Genus1 | Count | Count |Count |Count |
| Genus2 | Count | Count |Count |Count |
| Etc... | Count | Count |Count |Count |

# Any questions?
For questions or comments please reach out to mercy@live.unc.edu or mercylinden@gmail.com.
