Aligned recordings of neural spiking activity and licking behavior in thirsty mice
===
What is Brain Science Data Center in Chinese Academy of Sciences?                                   <img width="50" height="50" alt="d58423d59f79555631dd09870c20b9cb" src="https://github.com/user-attachments/assets/d60a103f-f900-4b7b-a122-a0ec4c40727f" />
---

The Brain Science Data Center is an institution established by the Institute of Neuroscience, Chinese Academy of Sciences, for storing brain science data. The stored data includes, but is not limited to, EEG, fMRI, calcium imaging, and neural connection brain atlas data. 
The raw data used in this study is stored in this center website https://www.braindatacenter.cn/datacenter/web/\#/dataSet/details?id=1722131061926764546 and https://www.braindatacenter.cn/datacenter/web/\#/dataSet/details?id=1722129114939236354


Experiment procedure
---

<img width="1200" height="260" alt="image" src="https://github.com/user-attachments/assets/1309605e-0e74-4748-9d45-dc8327789f99" />

The procedure of experiment has been shown as the figure above. It contains interval period, experiment period and fixation period.
The dataset is composed by 3 brain regions including M2, VLS and SNR. Data from M2 is collected from 5 mice while VLS and SNR are collected from 8 mice.






Datasets
---
<img width="1765" height="517" alt="image" src="https://github.com/user-attachments/assets/822b64d7-6e86-4614-8943-2f0d9ee8dca7" />


The main steps of our data processing pipeline are illustrated in the figure above. First, channel selection and spike signal detection were performed to convert electrophysiological data into spike-based data.  Next, the data collected daily were segmented according to the duration of each trial, resulting in two strictly aligned sets of data: one for spikes and the other for behavior. Finally, a resampling method was applied to unify the sampling rates of both datasets and generate strictly synchronized AI-ready data instances.

<img width="1130" height="476" alt="image" src="https://github.com/user-attachments/assets/19903cab-ee67-41eb-8f31-c79d2fd58583" />

We collected data from 13 mice across three brain regions (M2, SNR, and VLS), with a total recording duration of 119 days spanning 203 experimental hours. Each experimental trial comprises 32-channel neural recordings collected throughout the 119-day period, accompanied by corresponding time-series neural spike data.

<img width="1000" height="670" alt="image" src="https://github.com/user-attachments/assets/f333d936-2c99-4fa4-8d5c-032fa255ac99" />
The top left plots show consistency of neural spikes and behavior across three brain regions. The top right plots are firing rates across channels through four days. The bottom plots show the box plot of firing rate distribution across days among different mice in the M2 brain region. The consistency between spikes and behavior can be observed in all three regions of the brain, M2, VLS, and SNR. To quantify this relationship, we compute the Pearson correlation coefficient between spikes and behavior. The coefficients exceed 0.7 for all three brain regions, indicating a strong correlation between the data and ensuring its validity for encoding and decoding across regions.

The top right panel of Fig.\ref{fig:cross} illustrates the variations in firing rates(frequency at which a neuron generates action potentials per second) across different channels of the same mouse over multiple days. The labels M2, SNR, and VLS denote three distinct brain regions. The horizontal axis corresponds to the 32 channels, while the vertical axis indicates the firing rate of each channel. The four polylines represent recordings obtained from the same brain region over four days, with data from M2 collected in one mouse and data from VLS and SNR collected in another. We observed that the distribution of firing rates across channels remains largely consistent over days, exhibiting a Pearson correlation coefficient of approximately 0.75 between different days. This consistency suggests that cross-day decoding for the same mouse is feasible.

The bottom plot in Fig.\ref{fig:cross} illustrates the distribution of firing rates across different days. The x-axis corresponds to the mouse ID, while the y-axis represents the summed firing rate across all 32 channels. Each box plot displays the firing rate distribution of one mouse over multiple days. The median firing rates are consistently centered around 70 Hz, with the overall summed firing rates ranging from 50 to 80 Hz. These results indicate the feasibility of cross-subject decoding and simulation.



Code Description
---
In our github website, we provide the users with the data collected from M2 region in the example file. We also offer the code of data preprocessing in our github, users may segment the file with our code and reshape the spike or behavior trials into their ideal size. To evaluate the practical effectiveness of our dataset, we designed an experiment using 32-channel neural spike data as input to decode mouse licking behavior. We tested the decoding accuracy of this dataset under two algorithmic frameworks: Multilayer Perceptron (MLP) and Support Vector Machine (SVM), with results shown in the figure below
<img width="994" height="719" alt="image" src="https://github.com/user-attachments/assets/046490b1-c6c0-43a6-acc0-260526298348" />


The figure illustrates the decoding performance of MLP and SVM algorithms under three experimental conditions. The top panel presents MLP decoding results, and the left graph depicts same-day decoding accuracy across brain regions (represented by dual bars indicating performance from two distinct experimental sessions). The middle graph demonstrates cross-day generalization, where models trained on two daily sessions were evaluated on two other days. The right graph shows cross-subject performance, with models trained on two mice and tested on another two subjects. The bottom panel replicates this experimental paradigm using SVM classification.


Quantitative analysis demonstrates that MLP exhibited superior generalization capabilities, attaining consistently high accuracy in same-day (mean ± SD: 0.94 ± 0.01), cross-day (0.91 ± 0.02), and cross-subject (0.89 ± 0.03) contexts. Additionally, SVM achieved relatively lower decoding accuracy for same-day data (0.90 ± 0.02), with maintained performance under cross-day (0.82 ± 0.01) and cross-subject (0.78 ± 0.02) conditions. These findings indicate that both models effectively utilize the representational capacity of the dataset. The robust performance across both temporal and inter-subject domains confirms the dataset’s utility for neural decoding in scientific research.




Examples
---

We provide the users with the example code of utilizing MLP to implement decoding from spiking activity to mice behavior in the file example. Example data from M2 brain region is also attached in this file. Reseachers may download the ipynb file and change the file path to run the code.



