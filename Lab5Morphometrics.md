The first GPA plot below shows all the different data points that were gathered from the 29 fish diagrams. The darker points are the averages of each of the 13 landmarks. The plot is also rotated from the origional pictures by 90 degrees counterclockwise.
![GPA 1](https://github.com/ngbrecv/WWUAdvancedPaleo/blob/master/fishGPA1.png)


Now the first PCA plot below shows the variance between the diagrams in a more collective sense. Dots closer together resemble diagrams that are more closely related while ones further represent more extreme values. Specifically this shows the compairison between the first and second primary compairison, which would be the two characteristics with the most variance.
![PCA1](https://github.com/ngbrecv/WWUAdvancedPaleo/blob/master/Rplot.png)
The summary of the PCA below shows the standard deviation, variance, and average values for the first 19 PC components.

Importance of first k=19 (out of 26) components:

                          PC1    PC2     PC3     PC4     PC5     PC6     PC7     PC8     PC9     PC10     PC11     PC12
Standard deviation     0.2365 0.1611 0.06705 0.05910 0.05004 0.04871 0.03806 0.02548 0.01305 0.008709 0.005149 0.004439
Proportion of Variance 0.5756 0.2669 0.04625 0.03594 0.02577 0.02441 0.01491 0.00668 0.00175 0.000780 0.000270 0.000200
Cumulative Proportion  0.5756 0.8425 0.88872 0.92465 0.95042 0.97483 0.98973 0.99641 0.99817 0.998950 0.999220 0.999420

                           PC13     PC14     PC15     PC16     PC17     PC18     PC19
Standard deviation     0.004198 0.003584 0.002898 0.002454 0.002338 0.001742 0.001231
Proportion of Variance 0.000180 0.000130 0.000090 0.000060 0.000060 0.000030 0.000020
Cumulative Proportion  0.999600 0.999740 0.999820 0.999880 0.999940 0.999970 0.999990

This PCA test shows that much of the origional set of skulls is clustered around the same area, around -0.1 for both PC1 and PC2.


According to the PCA plot, specimens 29 and 8 are the least similar in terms of PC1 since they are at either end of the spectrum on the PC1 axis. 
![SPC8](https://github.com/ngbrecv/WWUAdvancedPaleo/blob/master/Boreaspis_ceratops.png)
Specimen 8

![SPC29](https://github.com/ngbrecv/WWUAdvancedPaleo/blob/master/Zychiaspis_siemiradzkii.png)
Specimen 29

The large chacteristic difference that PC1 represents appears to be the distance from landmark 5 and landmarks 6 and 13. This would be how far the tips of the wing like structures are from the lowest point at the center of the skull. 


According to the PCA plot, specimens 3 and 4 are the least similar in terms of PC2.
![SPC3](https://github.com/ngbrecv/WWUAdvancedPaleo/blob/master/Belonaspis_puella.png)
Specimen 3

![SPC4](https://github.com/ngbrecv/WWUAdvancedPaleo/blob/master/Benneviaspis_anglica.png)
Specimen 4

The factor that PC2 represents is the distance between landmarks 6 and 3. This is the distance between the two wing tip structures or how close in proximity they are to the main section of the skull. 


![BAR1](https://github.com/ngbrecv/WWUAdvancedPaleo/blob/master/Rplot01.png)
The bar graph above shows the variance degree between different PC's. Meaning, PC1 has the greatest amount of variance, then PC2 and so on. This goes with the first 7 PC's attributing to 99% of the characteristic variances. 

The following code was used to plot PC1 and PC8:
fishPCA <- plotTangentSpace(fishGPA$coords, axis1 = 1, axis2 = 8, label = TRUE)
![PCA2](https://github.com/ngbrecv/WWUAdvancedPaleo/blob/master/Rplot02.png)
The PCA graph above shows the compairson of PC1 to PC8. The dots all seem to be around the horizontal line because PC8 didn't have very much variance, especially compaired to PC1. 
