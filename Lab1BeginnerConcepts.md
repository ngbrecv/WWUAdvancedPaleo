1) What class of object is mtcars? What function did you use to find out?

      mtcars is a data grame. I first used head(mtcars) to see what the data looks like. Since it appeared to have multiples types of           data, I tried is(mtcars,"list") which returned FALSE, so then I tried is(mtcars,"data.frame") which returned TRUE.
      
2.) Is islands defined as a 1-dimensional array or a vector? How did you find out?

      islands is a vector. When checking if it is an array, is(islands,"array") returns FALSE. When checking if it is a vector, is             islands,"vector") returns TRUE.
      
3.) How would you convert the data.frame beaver1 into a matrix?

      After several attempts and the suggestion of creating a new object, I created the matrix "beaver matrix" by using a as.matrix ()         command. So, beavermatrix <- as.matrix(beaver1). I then checked to make sure that it converted by using class(beavermatrix) which       returned "matrix" as expected. 

4.) What is the name of the 8th landmass in the islands dataset? How did you find out?

      Since islands is a vector, it's one dimensional so when searching I only used one dimension. So, I checked islands[8] which would       ask for the eighth piece of data which returned "Borneo 280"

5.) What function would you use if you wanted to combine all three datasets into a single object?

      By creating a new variable, I would use used list() command to bind all three sets of data. So, it would look like datalist<-list       mtcars,beaver1,islands)

6.) Does islands consist of numeric data? How did you find out?

      islands consists of numeric data. I found out by using class(islands) which returned "numeric"
      
7.) Code four different ways to subscript the 2nd row and 7th column of mtcars using bracket notation. (Hint: You are looking to return the number 17.02)

      Four ways to subscript the desired information that then retuns 17.02 are 
      mtcars[2,7]
      mtcars[2,"qsec"]
      mtcars[,"qsec"][2]
      mtcars["Mazda RX4 Wag",7]
      
8.) How would you change the landmass values of "Iceland", "Kyushu", and "Tierra del Fuego" to 82, 21, and 10 in the islands dataset? (Hint: You will need to use subscripts and the <- operator).

      >>>When creating a new object, islandslist, for the three areas, I can't separate out the name from the number.
      
9.) Are there any times when the beaver in the beaver1 dataset had a temperature lower than 36.30 degrees? How did you find out?

      There are no times when the beaver's temperature is lower than 36.30 degrees. I found out by searching the entire temperature           column of beaver1 for any value that was under 36.3, so any(beaver1[,"temp"]<36.3 which returned FALSE.

10.) Take the sum of all elements in the column temp in the beaver1 dataset and call this value ValueA. Take the sume of all elements in the row Valiant in the mtcars dataset and call this value ValueB. Take the sum of the first 7 elements of the islands dataset and call this value ValueC. Divide ValueC by ValueB and add ValueA. What is your final answer? Show your code.
