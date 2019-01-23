1.) What does the replace = argument of the sample( ) function do?

      The replace = arguement of the sample() function, in this case it is TRUE, basically just tells R how to "randomize" the data. For instance, if replace = FALSE then all possible elements will occur. Whereas if replace = TRUE, one element can occur several times while another may not occur at all. Fior example, a sample size of 3 with possible elements 1,3, and 4 an replace = FALSE could return 3 1 4, while a replace = TRUE could return 1 1 3.

2.) Using as(MyMatrix,"numeric") will not convert MyMatrix to a numeric data! Can you use another property of logicals other than as( ) that will convert the logicals of MyMatrix to 0's and 1's?
      
      Using the function as.numeric(), so 
      
      > as.numeric(MyMatrix) 
      
      will convert all the values to 0's and 1's. 

3.) If you wanted to check if all the elements in each row are true, how would you do this?

      One way to check if all the elements in a row are true is by using the apply() and all() functions. In this case, I used 
      
      > apply(MyMatrix,1,all) 
      
      with MyMatrix still consisting of a matrix of logicals (not numerics), 1 represents the dimension (1 = rows), and all that searches for TRUE being in the entire set given to search (by row in MyMatrix). This returns 
      
      [1] FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
      
      or eight FALSE's which is consistant with eight rows, so no rows' elements are all TRUE. 
      
4.) How many times does the number 7 occur in MyMatrix?

      The number 7 occurs nine times in MyMatrix. There are two ways to find this. First I used 
      
      > MyMatrix[which(MyMatrix==7) 
      
      to find every instance of 7 in the matrix, this retuned 
      
      [1] 7 7 7 7 7 7 7 7 7 
      
      The second way is lazier in that I didn't have to count all the 7's, I used 
      
      > sum(MyMatrix==7) 
      
      which returned 
      
      [1] 9 

5.) How do you find the sum of each column?

      To find the sum of each column, use 
      
      > apply(MyMatrix,2,sum) 
      
      which returns 
      
      [1] 46 35 32 50 45 61 38 47 38 39 57 50

6.) How do you find the product of each column?

      To find the product of each column, use 
      
      > apply(MyMatrix,2,prod) 
      
      which returns 
      
      [1] 100000    9600    6804  840000  241920 7741440   12600  403200   70000   38880 4408992 1008000

7.) How can you change every instance of the number 1 to 11?

      To change every instance of 1 to 11, use 
      
      > MyMatrix[which(MyMatrix==1)]<-11

8.) How many values in MyMatrix are greater than 3 and less than 8?

      After converting all the 11's back into 1's, use 
      
      > sum(MyMatrix>3 & MyMatrix<8) 
      
      to find how many values are greater than 3 and less than 8. This returns 
      
      [1] 34
      
      so 34 values are greater than 3 and less than 8.

9.) How can you change the elements of column 12 into character data, while keeping columns 1-11 as numeric data?

      First I changed the matrix into a dataframe because only a dataframe can be made up of more than one kind of data
      
      > MyMatrix<-as.data.frame(MyMatrix)
      
      Then I changed only one the 12th column of MyMatrix to characters with
      
      > MyMatrix[,12]<-as.character(MyMatrix[,12])
      
      I checked to make sure that the other rows were still numeric while the 12th one was character and everything checked out.

10.) Find which rows of MyMatrix have a sum >70. Make a new version of MyMatrix where the 13th column is a set of TRUE and FALSE values denoting which rows have a sum >70. (Hint: What type of object allows you to store both logical and numeric data at once?)

      By using the apply function,
      
      > apply(MyMatrix, 1, sum)

      the sum of the rows are returned,
      
      [1] 69 66 70 60 61 70 75 67
      
      So, rows 3 and 6 sum to 70. To aadd a 13th column to MyMatrix that's a logical and not a numeric, I first converted MyMatrix into a dataframe simce dataframes can only have more than one data type,
      
      > MyMatrix<-as.data.frame(MyMatrix)
      
      Then to add a 13th column where the third and sixth values are TRUE and the others are FALSE I used
      
      > MyMatrix[,13]<-c("FALSE","FALSE","TRUE","FALSE","FALSE","TRUE","FALSE","FALSE")
      
      So when displaying MyMatrix, the result is
      
      > MyMatrix
        V1 V2 V3 V4 V5 V6 V7 V8 V9 V10 V11 V12   V13
      1 10  6  7  3  1  8  1  4  5   8   6  10 FALSE
      2  1  2  1 10  6  9 10  3 10   1   8   5 FALSE
      3  5  5  2  8  6  8  1 10  5   6   7   7  TRUE
      4  1  1  3  5 10  8  5  7  2   3   6   9 FALSE
      5 10  2  9  5  7  3  7  3  5   5   3   2 FALSE
      6 10  8  3 10  4  8  9  2  2   1   9   4  TRUE
      7  4 10  1  2  3 10  4  8  7   9   9   8 FALSE
      8  5  1  6  7  8  7  1 10  2   6   9   5 FALSE
