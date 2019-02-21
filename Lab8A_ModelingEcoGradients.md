PROBLEM SET 1

1.) How many genera are in the Miocene, Early Jurassic, Late Cretaceous, and Pennsylvanian epochs (not total, but in each epoch)? What code did you use to find out?

First I broke up the PresencePBDB data into just data for the Miocene, Early Jurrasic, Late Cretaceous, and Pennsylvanian.

> Mio<-PresencePBDB["Miocene",]

> EJur<-PresencePBDB["Early Jurassic",]

> LCre<-PresencePBDB["Late Cretaceous",]

> Penn<-PresencePBDB["Pennsylvanian",]

Next I used the sum() function to count all the inputs that are equal to 1 to find how many genera there are in each epoch.

> sum(Mio==1) 
[1] 653

> sum(EJur==1)
[1] 177

> sum(LCre==1)
[1] 396

> sum(Penn==1)
[1] 121

So, there are 653 genera in the Miocene, 177 in the Early Jurassic, 396 in the Late Cretaceous, and 121 in the Pennsylvanian

2.) How many geologic epochs are included in this dataset? What code did you use to find out?

First I isolated the column of epochs to work with less data,

> Epochs<-PresencePBDB[,1]

Then I made all values equal 1 since some were 0 and for my purpose that wasn't necessary,

> Epochs[which(Epochs==0)]<-1

Lastly I summed all the values which would be the ammount of epochs,

> sum(Epochs)
[1] 29

So, there are 29 epochs.

3.) Which epochs contain specimens of the genus Mytilus (a type of mussel)? What code did you use to find out?

First I isolated just the Mytilus specimens from the rest of the specimens,

> Mytilus<-PresencePBDB[,"Mytilus"]

This provided the epochs with values of 1 and 0 that corresponded with whether that epoch contained this specimen or not. The total amount of epochs that contained the specimen was then calculated,

> sum(Mytilus)
[1] 16

So there are 16 epochs that have the specimen. To find out which exact epochs these were instead, I used the following code.

> which(Mytilus==1)

         Pridoli   Early Devonian    Late Jurassic           Eocene  Late Cretaceous Early Cretaceous  Middle Jurassic        Paleocene 
               8               10               14               15               16               17               18               19 
       Oligocene          Miocene   Early Jurassic      Pleistocene  Middle Triassic    Late Triassic         Pliocene   Early Triassic 
              20               21               22               23               25               26               27               28 

This also displayed how many of the Mytilus specimens were found in each of the epochs, bonus!

4,) Look at the epochs in the geologic timescale. Using your answer to question 3, in which epochs can we infer that Mytilus was present, even though we have no record of them in the PBDB? How did you deduce this?

By looking at my Mytilus value, I can see where this specimen pops up in which epochs,

> Mytilus

    Pennsylvanian  Early Ordovician Middle Ordovician   Late Ordovician        Llandovery           Wenlock            Ludlow 
                0                 0                 0                 0                 0                 0                 0 
          Pridoli     Mississippian    Early Devonian   Middle Devonian     Late Devonian        Cisuralian     Late Jurassic 
                1                 0                 1                 0                 0                 0                 1 
           Eocene   Late Cretaceous  Early Cretaceous   Middle Jurassic         Paleocene         Oligocene           Miocene 
                1                 1                 1                 1                 1                 1                 1 
   Early Jurassic       Pleistocene       Guadalupian   Middle Triassic     Late Triassic          Pliocene    Early Triassic 
                1                 1                 0                 1                 1                 1                 1 
        Lopingian 
                0 

By looking at this data I can see gaps of where Mytilus is and isn't in the time scale. For example, it first appears in the Pridoli epoch but isn't in the following epoch, the Mississippian. It wouldn't make sense for an organism to just suddenly dissapear in the geologic time scale so it can be deduced that, even though there isn't a record of the specimen during this epoch, that it still existed during this time. Following this logic, its probable that Mytilus also existed in the Middle and Late Devonian, Cisuralian, and Guadalupian. So in total, Mytilus most likely existed from the Pridoli to Early Triassic.


PROBLEM SET 2

1.) Using your own custom R code, find the Jaccard similarity of the Pleistocene and Miocene "samples" in your PresencePBDB matrix. It is possible to code this entirely using only functions discussed in the R Tutorial.



2.) How can you convert your similarity index to a distance?



3.) Install and load the vegan package. Read the help file for the vegdist( ) function, then use vegdist( ) to calculate the Jaccard distance of the Miocene and Pleistocene samples from the PresencePBDB matrix. Your answer should be identical to your answer to Question 2.



4.) Using the vegdist( ) function, calculate the Jaccard distances for all of the following epochs in PresencePBDB: Pleistocene, Pliocene, Miocene, Oligocene, Eocene, Paleocene. What code did you use? Which two epochs are the most dissimilar?
