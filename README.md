Aligned recordings of neural spiking activity and licking behavior in thirsty mice
===
What is Brain Science Data Center in Chinese Academy of Sciences?
---
The Brain Science Data Center is an institution established by the Institute of Neuroscience, Chinese Academy of Sciences, for storing brain science data. The stored data includes, but is not limited to, EEG, fMRI, calcium imaging, and neural connection brain atlas data. <img width="100" height="100" alt="d58423d59f79555631dd09870c20b9cb" src="https://github.com/user-attachments/assets/d60a103f-f900-4b7b-a122-a0ec4c40727f" />

The raw data used in this study is stored in this center website https://www.braindatacenter.cn/datacenter/web/\#/dataSet/details?id=1722131061926764546 and https://www.braindatacenter.cn/datacenter/web/\#/dataSet/details?id=1722129114939236354

Code Description
---
<img width="1762" height="587" alt="mouse_lick" src="https://github.com/user-attachments/assets/ab6e7aea-c019-452a-84de-2663c177faff" />
The main steps of our data processing pipeline are illustrated in the figure above. First, channel selection and spike signal detection were performed to convert electrophysiological data into spike-based data. 
Next, the data collected daily were segmented according to the duration of each trial, resulting in two strictly aligned sets of data: one for spikes and the other for behavior. Finally, a resampling method was applied to unify the sampling rates of both datasets and generate strictly synchronized AI-ready data instances.


The code can help users load all the raw data and preprocess the data into aligned AI ready dataset. M2_preprocess is the code for processing the data collected from M2 brain region, while SNR_preprocess, VLS_preprocess are used to process the data collected from VLS and SNR brain regions. Resampling algorithm is offered for users
to reshape the data into expected format, users may select the .mat files they want to resample and choose the 


Usage notes
---
The code for preprocessing the data into aligned trials has been provided. Users only need to modify the file paths to perform data extraction and preprocessing on all results stored in the raw dataset. Code for resampling the spiking dataset is also provided, users may use example.mat file to reshape trials into the size 
they need.



Datasets
---
The dataset is composed by 3 brain regions including M2, VLS and SNR. Data from M2 is collected from 5 mice while VLS and SNR are collected from 8 mice. In our github website, we provide the users with the data collected from M2 region as an example, users may segment the file with our code and reshape the trials into their ideal size.
