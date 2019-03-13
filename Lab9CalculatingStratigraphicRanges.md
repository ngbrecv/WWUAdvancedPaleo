1.) What do the max_ma and min_ma columns of DataPBDB represent? 

The max_ma and min_ma represent the maximum and minumum occurance in millions of years. That is, in all the data for that species, its oldest record and youngest record.

2.) What is oldest age of each genus? [Hint: Use the tapply( ) and max( ) functions we've used in previous labs]. Show the code you would use to find out.

There are a lot of geni, too many to paste.
> tapply(DataPBDB$max_ma, DataPBDB$genus, max)

3.) What is the youngest age of each genus? [Hint: Use the tapply( ) and min( ) functions we've used in previous labs]. Show the code you would use to find out.

> tapply(DataPBDB$min_ma, DataPBDB$genus, min)

4.) Find which genus has the most occurrences in the dataset [Hint: Use the table( ) function!]. What code did you use?

The Anadara genus has the most occurances, 2105 occurances.

> sort.int(table(DataPBDB$genus),decreasing = TRUE)

5.) What is the stratigraphic range of this taxon (i.e., your answer to question 4). Show your code.

The maximum age for Anadara is 66 million years,
> tapply(DataPBDB$max_ma, DataPBDB$genus=="Anadara", max)

The minimum age for Anadara is 0 million years,
> tapply(DataPBDB$min_ma, DataPBDB$genus=="Anadara", min)

6.) Qualitatively describe what is happening in the following lines of code. A good answer should identify what the different arguments are for each function, and what they are used for.

> PaleoLng <- na.omit(Lucina$paleolng)

This function is collecting all the Lucina Paleo longatude data from the Lucina dataset and obmitting all the entries that don't have an input, or in other words are NA or have no value.

> mean(sample(PaleoLng, length(PaleoLng), replace=TRUE))

This function is taking the Paleo longatude data from the Lucina dataset, excluding repeated numbers, and calculating the mean paleo latitud for Lucina.

7.) Plot a kernel density graph of ResampledMeans. Show your code. Does the distribution look approximately Gaussian? Explain why you think it does or does not.

> plot(density(ResampledMeans))

The kernel density graph, as seen below, looks to be Gaussian because it looks like a bell curve, or evenly distributed about the mean.
https://github.com/ngbrecv/WWUAdvancedPaleo/blob/master/Problem7.png

8.) Find the mean of ResampledMeans, is it similar to the mean of the original data?

> MeanResampledMeans<-mean(ResampledMeans)

> MeanResampledMeans

[1] 24.76644

> OriginalMean

[1] 24.8

The mean of ResampledMeans is apporoximately the same as the origional mean.

9.) Sort ResampledMeans from lowest to highest. [Hint: We learned how to sort a vector in Lab 6].

> SortResampledMeans<-sort(ResampledMeans)

10.) Now that you have sorted ResampledMeans, what is the 2.5th percentile of ResampledMeans and what is the 97.5th percentile of Resampled means. If you do not know what a percentile is, or how to calculate it, you can use google. Show your code.

> 0.25*1000

[1] 250

> SortResampledMeans[250]

[1] 23.87917

> 0.975*1000

[1] 975

> SortResampledMeans[975]

[1] 27.28373

11.) Incidentally, these numbers (your answer to question 5) are the lower and upper confidence interval of the mean! Qualitatively explain why this is the case.

The answer to number 5 was about Anadara, not Lucina...
Since the maximum age of Lucina is 66 million years and the minimum is 0 million years, it would make sense that the confidence interval is from 0 to 66 million years because a confidence interval in this case is the interval of time we can confidentally say that Lucina is present.

12. Based on the confidence intervals given above, do you think it likely or unlikely that Lucina is still alive?

I'm going to assume it means Anadara instead of Lucina, in reference to the answer to number 5.
It is likely that Anadara is still alive since the minimum of its confidence interval is 0 million years aka the present.

13. Find the extinction confidence interval for the genus Dallarca. Show your code.

> tapply(DataPBDB$max_ma, DataPBDB$genus=="Dallarca", max)

FALSE  TRUE 
66.00 23.03 

> tapply(DataPBDB$min_ma, DataPBDB$genus=="Dallarca", min)

FALSE  TRUE 
0.000 2.588 

The confidence interval for Dallarca is from 2.588 million years to 23.03 million years

14. A pure reading of the fossil record says that Dallarca went extinct at the end of the Pliocene Epoch. Based on its confidence interval, do you think it is possible that Dallarca is still extant (alive)?

Since the Pliocene ended approximately 2.58 million years ago and this confident interval ends at 2.58 million years, it is unlikely that Dallarca is extant.

15.) In this case, should we trust the confidence interval or a pure reading of the fossil record? Explain your reasoning.

I think we should trust both confidence intervals and pure readings or at least compare the two because testing against two things is always better than just relying on one thing or another.

16.) State one ecological reason why this assumption is unlikey to be true.

Over time one region can change in the type of environment. For example, an inland ocean can turn into a desert. With a change in encironment comes a change in the kinds of organisms found there. So having fossils be randomly distributed thoughout many strata wouldn't correspond with a changing environment.

17.) State one geological reason why this assumpiton is unlikely to be true.

Geological events can erode, move, distroy, or alter fossils. Uplift can expose fossils, glaciers can move fossils hundereds of miles, a volcanic episode can distroy a specimen, or permineralization can help petrify remains, etc.

18.) How many occurrences are in DataPBDB. How many are in ExtantData? How many occurrences were lost by limiting our anaysis to only extant bivalves?

> length(DataPBDB$occurrence_no)

[1] 71380

> length(ExtantData$occurrence_no)

[1] 62102

There are 71380 occurences in DataPBDB and 62102 occurances in ExtantData. If we only limited our data to extant bivalves we'd be missing 9278 genera.

19.) How many unique( ) genera were in DataPBDB and ExtantData, respectively. Using this information, what percentage of Cenozoic bivalves in the PBDB are still extant today.

> length(unique(DataPBDB$genus))

[1] 1095

> length(unique(ExtantData$genus))

[1] 548

There are 1095 unique geni in DataPBDB and 548 unique geni in ExtantData. This means approximately half of Cenezoic bivalves are still extant today.

20.) Find the stratigraphic range of fossil occurrences for each genus in the ExtantData dataset. If you do not remember how to do this, revisit Problem Set 1 of this lab.



21.) Using your answer to question 3, find which genera in ExtantData are not extant according to the PBDB - i.e., do not have a minimum min_age of zero. Show your code.



22.) Calculate the confidence interval for the extinction of the following genera (careful with your spelling!): Scrobicularia, Meiocardia, Dimya, Digitaria, Cuspidaria, Arctica, Aloides, Kurtiella, Gouldia, and Acrosterigma. Show your code. What percentage of these taxa have confidence intervals indicating that the taxon might still be extant?

