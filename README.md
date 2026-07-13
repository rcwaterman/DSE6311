# DSE6311 - Predicting Thermal Error in High Accuracy Accelerometers
## Bockground
Accelerometers embedded in Inertial Measurement Units (IMU's) are subject to erroneous output due to internal stresses from thermal expansion and contraction. IMUs, particularly in Integrated Circuit (IC) form, are ubiquitous in embedded systems from drones to phones, serving the critical function of measuring 6 degree-of-freedom motion. In highly precise applications, error in the accelerometer measurement as a result of thermal variance can lead to system level performance issues. 
## Question
Can a machine learning model accurately predict cartesian axis measurement error due to thermal fluctuation, effectively correcting this failure mode?   
## Hypothesis and Predictions
Given sufficient, clean data, a model can sufficiently predict the offset vector required to cancel error due to thermal drift. 
