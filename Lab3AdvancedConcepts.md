1.) Write a function that returns the phrase "Hello, world."

      In my opinion writing a function for this is overly complicated when you can just write a print() statement. But anyways, I used the function: 
> greetings<-function(Arguement){
+     print("Hello, world.")
+ }
which returned "Hello, world." when anything was typed in, such as greetings(hi).

2.) Load the iris dataset. Write a function that takes iris as its argument and returns three subsets of the data.frame, split by the three different types of species (saved as a single object).

      To creat three seperate subsets of the iris dataset, I created the function:
irisfunction<-function(iris){
  irislist<-list(iris[1:50,],iris[51:100,],iris[101:150,])
  print(irislist)
}

3.) Write a function that takes iris as its argument. The function should, for each row, add Sepal.Length and Petal.Length if Sepal.Width is >3.1. It should subtract Petal.Length from Sepal.Length if Sepal.Width is <3.1. The answer should be returned as a vector.

The following function takes a given row in the iris dataset and does math to it accordingly. 

irismath<-function(iris,row){
  if(iris[row,2]>3.1){
    return(iris[row,1]+iris[row,3])
  }
  else if(iris[row,2]<3.1){
    return(iris[row,1]-iris[row,3])
  }
}

4.) Load the mtcars dataset. Write a function that takes the number of cylinders as its argument. Have the function return the average miles per gallon (column mpg) for all cars with that number of cylinders (column cyl).

      Below is the code I used to do what was asked. Since there were only three options of cylinder size, 4, 6, and 8, I just copied the same formatting for each. After selecting the cylinder size, the rows in which have those cylinders are selected. Then the sum of the mpg column for those rows are calculated and the length (or how many) of the rows is recorded. Lastly it does the math to find the average. Additionally, if a number is imputed that is not 4, 6, or 8, the return will be the statement "invalid"
      
mtcarsCylinders<-function(cyls){
  if(cyls==4){
    cyl<-which(mtcars[,2]==4)
   cylall<-sum(mtcars[cyl,1])
   cylamount<-length(cyl)
   return(cylall/cylamount)
  }
  else if(cyls==6){
    cyl<-which(mtcars[,2]==6)
  cylall<-sum(mtcars[cyl,1])
  cylamount<-length(cyl)
  return(cylall/cylamount)
  }
  else if(cyls==8){
    cyl<-which(mtcars[,2]==8)
    cylall<-sum(mtcars[cyl,1])
    cylamount<-length(cyl)
    return(cylall/cylamount)
  }
  else{
    print("invalid")
  }
}

5.) Write a function that simulates 1,000,000 PowerBall drawings. A PowerBall drawing takes a randome sample of five numbers (without replacement) from 1-69, plus one powerball number ranging from 1-26. The function should return a single object recording all of your draws.

6.) Write a function that takes a single set of lottery numbers (as a vector) as its argument. As before, write a function that simulates 1,000,000 PowerBall drawings. Have the function return a TRUE or FALSE value indicating if you won any of the drawings.

To create a random power ball number, 
basefive<-sample(1:69,5,replace = FALSE)
powernumber<-sample(1:26,1,replace = FALSE)
powerball<-c(basefive,powernumber)

