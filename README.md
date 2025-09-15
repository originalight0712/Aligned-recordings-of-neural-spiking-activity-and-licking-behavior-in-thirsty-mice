Aligned recordings of neural spiking activity and licking behavior in thirsty mice
===
What is Brain Science Data Center in Chinese Academy of Sciences?
---
The Brain Science Data Center is an institution established by the Institute of Neuroscience, Chinese Academy of Sciences, for storing brain science data. The stored data includes, but is not limited to, EEG, fMRI, calcium imaging, and neural connection brain atlas data. 
The raw data used in this study is stored in this center website https://www.braindatacenter.cn/datacenter/web/\#/dataSet/details?id=1722131061926764546 and https://www.braindatacenter.cn/datacenter/web/\#/dataSet/details?id=1722129114939236354

Code Description
---
<img width="1762" height="587" alt="mouse_lick" src="https://github.com/user-attachments/assets/ab6e7aea-c019-452a-84de-2663c177faff" />
The main steps of our data processing pipeline are illustrated in the figure above. First, channel selection and spike signal detection were performed to convert electrophysiological data into spike-based data. 
Next, the data collected daily were segmented according to the duration of each trial, resulting in two strictly aligned sets of data: one for spikes and the other for behavior. Finally, a resampling method was applied to unify the sampling rates of both datasets and generate strictly synchronized AI-ready data instances.


The code can help users load all the raw data and preprocess the data into aligned AI ready dataset. M2_preprocess is the code for processing the data collected from M2 brain region, while SNR_preprocess, VLS_preprocess are used to process the data collected from VLS and SNR brain regions. Resampling algorithm is offered for users
to reshape the data into expected format.


Examples
---




Datasets
---
