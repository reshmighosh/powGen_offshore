# PowGenoffshore

This codebase is an extension of the the python module developed by students and researchers at University of Michigan, Ann Arbor [PowGen](https://github.com/ijbd/powGen). The basic PowGen package has been improoved to include the ability to convert solar and wind resources into their corresponding capaccity factors in the offshore region surrounding mainland US using the NREL System Advisor Model [SAM](https://sam.nrel.gov/).

## Extract MERRA data


## Process MERRA data

Along with the standard instructions provided in [PowGen](https://github.com/ijbd/powGen), the selection of offshore wind turbine is very critical. SAM database lists a number of onshore wind turbines, but only a few offshore wind turbines. For my doctoral research, we used the Senvion 6.2-MW offshore wind turbine from the database. Once you have chosen an appropriate offshore wind turbine, copy the wind turbine power curve values by right-clicking on the image of the curve in the SAM GUI as a python list, and interpolate the values to match the wind speed intervals of onshore wind turbines. This can be simply achieved by cop

`# Import libraries
import numpy as np
import pandas as pd
from scipy.interpolate import interp1d

# Interpolate the power curve values to make them homogeneous to the range of onshore wind turbine
# power outputs from SAM
onshore_windspeed_range = np.arange(1, 30.25, 0.25)
power_curve = pd.read_csv('graphdatanew.csv')
interpolate_func = interp1d(power_curve['wind_speed_(m/s)'], power_curve['turbine_output'])
offshore_power_interp = interpolate_fun(onshore_windspeed_range)

# Copy the offshore_power_interp output to the existing wind_turbine_power_curves.xlsx under column 
# offshore_wind. This is your interpolated offshore wind turbine power output values homogeneous to 
# the range of onshore wind`





the and paste it into wind_turbin_power_curves.xlsx.
