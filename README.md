# matplotlib-challenge
The following was given to us with two CSV files. In this study, 249 mice who were identified with SCC tumors received treatment with a range of drug regimens. Over the course of 45 days, tumor development was observed and measured. The purpose of this study was to compare the performance of Pymaceuticals’ drug of interest, Capomulin, against the other treatment regimens.

I used nunique to display the number of unique mice IDs in the data, and then checked for any mouse ID with duplicate time points. There is a new data frame created where the duplicate data is removed.

There is a data frame containing a row for each drug regimen. These regimen names are in the index column as well as a column for each of the following statistics: mean, median, variance, standard deviation, and SEM of the tumor volume. I used .agg(['mean', 'median', 'var', 'std', 'sem']). 
The results were
Drug Regimen mean median var std sem
Capomulin 40.675741 41.557809 24.947764 4.994774 0.329346 Ceftamin 52.591172 51.776157 39.290177 6.268188 0.469821 Infubinol 52.884795 51.820584 43.128684 6.567243 0.492236 Ketapril 55.235638 53.698743 68.553577 8.279709 0.603860 Naftisol 54.331565 52.509285 66.173479 8.134708 0.596466 Placebo 54.033581 52.288934 61.168083 7.821003 0.581331 Propriva 52.393463 50.909965 43.138803 6.568014 0.525862 Ramicane 40.216745 40.673236 23.486704 4.846308 0.320955 Stelasyn 54.233149 52.431737 59.450562 7.710419 0.573111 Zoniferol 53.236507 51.818479 48.533355 6.966589 0.516398

Two bar charts were created first bar chart with the Pandas DataFrame.plot() method and the second bar chart with Matplotlib's pyplot methods displaying how many mice recieved each drug.
Two pie charts were created, the first pie chart with the Pandas DataFrame.plot() method and the second pie chart with Matplotlib's pyplot methods displaying the sex of the mice used.

The final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Then, calculate the quartiles and IQR, and determine if there are any potential outliers across all four treatment regimens using fig1, ax1 = plt.subplots() ax1.set_ylabel('Final Tumor Volume (mm3)') box_plot = ax1.boxplot(vol_data, labels=treatments) outliers = box_plot['fliers'] for outlier in outliers: outlier.set(marker='o', markerfacecolor='red', markersize=10) plt.show() which I recieved from the expert learning assistant in BootCampSpot. An outlier is highlighted in the plot by changing their color and style for the infubinol.

A line plot and scatter plot was created with single mouse that was treated with Capomulin using .sample.

The correlation coefficient, 0.8419363424694722, and linear regression model between mouse weight and average observed tumor volume for the entire Capomulin treatment regimen done using the same formula from class activites. The linear regression model is on top of the scatter plot.

