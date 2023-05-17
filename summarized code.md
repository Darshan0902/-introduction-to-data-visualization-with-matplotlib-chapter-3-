# Importing the essential libraries...
import matplotlib.pyplot as plt
<br>import pandas as pd


```
fig, ax = plt.subplots()
# Plot a histogram of "Weight" for mens_rowing
ax.hist(mens_rowing["Weight"])

# Compare to histogram of "Weight" for mens_gymnastics
ax.hist(mens_gymnastics["Weight"])

# Set the x-axis label to "Weight (kg)"
ax.set_xlabel("Weight (kg)")

# Set the y-axis label to "# of observations"
ax.set_ylabel("# of observations")

plt.show() 
```

<h2> Stacked Bar Chart : </h2>

A stacked bar chart contains bars, where the height of each bar represents values. In addition, stacked on top of the first variable may be another variable. The additional height of this bar represents the value of this variable. And you can add more bars on top of that.

In this exercise, you will have access to a DataFrame called medals that contains an index that holds the names of different countries, and three columns: "Gold", "Silver" and "Bronze". You will also have a Figure, fig, and Axes, ax, that you can add data to.

You will create a stacked bar chart that shows the number of gold, silver, and bronze medals won by each country, and you will add labels and create a legend that indicates which bars represent which medals.

Call the ax.bar method to add the "Gold" medals. Call it with the label set to "Gold".

Call the ax.bar method to stack "Silver" bars on top of that, using the bottom key-word argument so the bottom of the bars will be on top of the gold medal bars, and label to add the label "Silver".

Use ax.bar to add "Bronze" bars on top of that, using the bottom key-word and label it as "Bronze".

```
# Add bars for "Gold" with the label "Gold"
ax.bar(medals.index,medals["Gold"], label="Gold")

# Stack bars for "Silver" on top with label "Silver"
ax.bar(medals.index,medals["Silver"], bottom=medals["Gold"], label="Silver")

# Stack bars for "Bronze" on top of that with label "Bronze"
ax.bar(medals.index,medals["Bronze"],bottom=medals["Silver"]+medals["Gold"],label="Bronze")

# Display the legend
ax.legend()

plt.show()
```


<h2> Creating histograms </h2> 


Histograms show the full distribution of a variable. In this exercise, we will display the distribution of weights of medalists in gymnastics and in rowing in the 2016 Olympic games for a comparison between them.

You will have two DataFrames to use. The first is called mens_rowing and includes information about the medalists in the men's rowing events. The other is called mens_gymnastics and includes information about medalists in all of the Gymnastics events.


<h2> INSTRUCTIONS </h2> 


Use the ax.hist method to add a histogram of the "Weight" column from the mens_rowing DataFrame.
Use ax.hist to add a histogram of "Weight" for the mens_gymnastics DataFrame.
Set the x-axis label to "Weight (kg)" and the y-axis label to "# of observations".

```

fig, ax = plt.subplots()
# Plot a histogram of "Weight" for mens_rowing
ax.hist(mens_rowing["Weight"])

# Compare to histogram of "Weight" for mens_gymnastics
ax.hist(mens_gymnastics["Weight"])

# Set the x-axis label to "Weight (kg)"
ax.set_xlabel("Weight (kg)")

# Set the y-axis label to "# of observations"
ax.set_ylabel("# of observations")

plt.show()

```


<h2> Step Histogram : </h2>

```

fig, ax = plt.subplots()

# Plot a histogram of "Weight" for mens_rowing
ax.hist(mens_rowing["Weight"], histtype='step', label="Rowing", bins=5)

# Compare to histogram of "Weight" for mens_gymnastics
ax.hist(mens_gymnastics["Weight"], histtype='step', label="Gymnastics", bins=5)

ax.set_xlabel("Weight (kg)")
ax.set_ylabel("# of observations")

# Add the legend and show the Figure
ax.legend()
plt.show()

```
Use the hist method to display a histogram of the "Weight" column from the mens_rowing DataFrame, label this as "Rowing".
Use hist to display a histogram of the "Weight" column from the mens_gymnastics DataFrame, and label this as "Gymnastics".
For both histograms, use the histtype argument to visualize the data using the 'step' type and set the number of bins to use to 5.
Add a legend to the figure, before it is displayed

```
fig, ax = plt.subplots()

# Plot a histogram of "Weight" for mens_rowing
ax.hist(mens_rowing["Weight"], histtype='step', label="Rowing", bins=5)

# Compare to histogram of "Weight" for mens_gymnastics
ax.hist(mens_gymnastics["Weight"], histtype='step', label="Gymnastics", bins=5)

ax.set_xlabel("Weight (kg)")
ax.set_ylabel("# of observations")

# Add the legend and show the Figure
ax.legend()
plt.show(

```
<h2> Adding error-bars to a bar chart</h2> :

Add a bar with size equal to the mean of the "Height" column in the mens_rowing DataFrame and an error-bar of its standard deviation.
Add another bar for the mean of the "Height" column in mens_gymnastics with an error-bar of its standard deviation.
Add a label to the the y-axis: "Height (cm)".


```

fig, ax = plt.subplots()

# Add a bar for the rowing "Height" column mean/std
ax.bar("Rowing",mens_rowing["Height"].mean(), yerr=mens_rowing["Height"].std())

# Add a bar for the gymnastics "Height" column mean/std
ax.bar("Gymnastics",mens_gymnastics["Height"].mean(),yerr=mens_gymnastics["Height"].std())

# Label the y-axis
ax.set_ylabel("Height (cm)")

plt.show()

```



<h2> Creating boxplots </h2>
INSTRUCTIONS

Create a boxplot that contains the "Height" column for mens_rowing on the left and mens_gymnastics on the right.
Add x-axis tick labels: "Rowing" and "Gymnastics".
Add a y-axis label: "Height (cm)"


```

fig, ax = plt.subplots()

# Add a boxplot for the "Height" column in the DataFrames
ax.boxplot([mens_rowing["Height"],mens_gymnastics["Height"]])

# Add x-axis tick labels:
ax.set_xticklabels(["Rowing","Gymnastics"])

# Add a y-axis label
ax.set_ylabel("Height (cm)")

plt.show()

```

<h2> SIMPLE SCATTERPLOT </h2> : 
Using the ax.scatter method, add the data to the plot: "co2" on the x-axis and "relative_temp" on the y-axis.
Set the x-axis label to "CO2 (ppm)".
Set the y-axis label to "Relative temperature (C)".

```



fig, ax = plt.subplots()

# Add data: "co2" on x-axis, "relative_temp" on y-axis
ax.scatter(climate_change["co2"],climate_change["relative_temp"])

# Set the x-axis label to "CO2 (ppm)"
ax.set_xlabel("CO2 (ppm)")

# Set the y-axis label to "Relative temperature (C)"
ax.set_ylabel("Relative temperature (C)")

plt.show()


```
