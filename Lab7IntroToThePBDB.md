PART 1

1.) How many collections are associated with this reference?

  There are 704 collections associated with this reference.

2.) What is the reference ID number for the article?

  The reference ID is 24429.

3.) The first two taxa in the taxonomic list are bryozoans, and the third taxon listed is Rafinesquina alternata. Next to the taxonomic name is the citation (Conrad 1838). What is the class, family, genus and species of the fourth taxon in the taxonomic list?

  The class is Strophomenata, the family is Strophomenida, the genus is Strophomenidae, and the species is Strophomena planumbona.

4.) In what county was the data collected?

  The data was collected in Union County, Indiana.

5.) What age (Period) is the data from?

  The data is from the late Ordovician.

6.) What is the name of the geologic formation that the data was collected from?

  The data is from the Liberty formation.


PART 2

1.) Zoom in so that you can see from Texas to Florida and from Florida to New York. Some of the occurrences are orange and others are yellow. What is the significance of the different colors?

  In this area all the occurences are from the Cenozoic. All the orange occurances are from the Paleogene and most of the yellow occurances are from the Neogene. Some of the yellow occurances indicate broadly that it's just from the Cenozoic.

2.) Zoom back out. Add an additioanl filter to the search bar, the Ypresian stage. The Ypresian is a time interval ranging from 47.8-56.0 million years ago. In what countries are there Ypresian occurrences of Abra?

  Ypresian stage Abra occurances are in the US, the UK, and Belgium.

3.) Clear the Abra and Ypresian filters from the search. Look for the genus Ambonychia (another genus of bivalve). Within the United States, find the city with the most occurrences of Ambonychia. What is the name of this city?

  Most of the occurances are around Cincinnati.

4.) What age (Period) are most Ambonychia occurrences?

  Most of the the Ambonychia occurances come from the Ordovician.

5.) During this time period, were most occurrences of Ambonychia arrayed parallel or perpendicular to the equator?

>>>>>>>>>

6.) Click on the little insect icon on the left side of the screen. This brings up taxonomic information about the target taxon. What order does Ambonychia belong to?

  Ambonychia belongs to the Myalinida order.
  
  
  PART 3
  
1.) All occurrences of Ambonychia in the Lexington Limestone as a JSON

  https://paleobiodb.org/data1.2/occs/list.json?datainfo&rowcount&base_name=Ambonychia&strat=Lexington Limestone

2.) All occurrences of mammals present in the Paleocene through Oligocene epochs as a csv

  https://paleobiodb.org/data1.2/occs/list.csv?datainfo&rowcount&base_name=mammalia&interval=Paleocene,Oligocene

3.) All opinions on the order Testudines in the Mesozoic

   https://paleobiodb.org/data1.2/occs/opinions.csv?datainfo&rowcount&base_name=Testudines&rank=order&interval=Mesozoic&op_type=all

4.) All collections of Aves, Marsupialia, and Sirenia in the United States as a csv

  https://paleobiodb.org/data1.2/colls/list.csv?datainfo&rowcount&base_name=Aves, Marsupialia, Sirenia&cc=US

5.) All occurrences of the gastropod genus Ficus as a csv

  https://paleobiodb.org/data1.2/occs/list.csv?datainfo&rowcount&base_name=Ficus&taxon_reso=genus

6.) What family does the genus Gastrocopta belong to?

  The genus Gastrocopta belongs to the family Gastrocoptidae.

7.) There is only one occurrence of Isoetes in Portugal. What age is it?

  The occurance of Isoetes in Portugal is from the Miocene (23.0 - 2.6 Ma).

8.) What is the age of the oldest occurrence of Gastrocopta?

  The oldest occurence of Gstrocopta is from the Eocene.

9.) There is only one occurrence of Tiktaalik in the PBDB. Was that occurrence located in the tropics or the extratropics when that organism was alive?

  When this organism was alive it was located on/around the equator so it'd be in the tropics. 

10.) There are two occurrences of Namacalathus in Siberia. What geologic formations are they found in?

  The two occuranes of Namacalathus in Siberia are located in the Kotodzha formation and the Raiga formation.
  
 
PART 4
 
1.) In your morphometrics lab, you downloaded a csv file of ammonite sizes from a GitHub URL directly into R. What code would you use to download the following PBDB data directly into R?
 
  URL<-"https://paleobiodb.org/data1.2/colls/list.csv?base_name=Mammut&interval=Pliocene"

  Then to make it visible,
  RData<-read.cvs(URL)
 
2.) Download the data from the URL above into R. What are its dimensions?

  The data frame from the URL has  two dimensions, 14 variables (columns) and 70 observations (rows).

3.) Did the above call use the occurrences, collections, references, opinions, or specimens route?

  The call uses the collections route.

4.) What genus is being called for? What is its colloquial name? What age was the call limited to?

  The genus mammut is being called for, this genus inclueds mammals. The call is limited to the Pliocene. 

5.) Look through the service doumentation for the appropriate route (based on your answer to Question 2). Find out how to extend the age search range from the Miocene Epoch through the Pleistocene Epoch. Give the new data query URL.

  https://paleobiodb.org/data1.2/colls/list.csv?base_name=Mammut&interval=Miocene,Pleistocene

6.) What URL would you use to show the paleocoordinates (i.e., paleolatitude and paleolongitude) of each data point?

  https://paleobiodb.org/data1.2/colls/list.csv?base_name=Mammut&interval=Miocene,Pleistocene&show=paleoloc
    

PART 5

1.) Write an R function that will take a taxonomic name (as a character string) and an interval (as a character string) as its argument, and will download all fossil occurrences in R. See above.

Following the Mammut and Pliocene trend, to search and download these parameters directly from the PBDB to R would be,

MammutData<-downloadPBDB(taxon="Mammut",interval="Pliocene")
