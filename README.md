Download Link: https://assignmentchef.com/product/solved-cmpt141-assignment6-arrays
<br>
<strong>Question 1 </strong>

<strong>Purpose: </strong>To practice arithmetic and indexing with arrays.

<strong>Degree of Difficulty: </strong>Easy to Moderate.

In this question, you will again use information from the City of Saskatoon Open Data Catalogue

(http://opendata-saskatoon.cloudapp.net/). The file Neighbourhood Dwelling Unit Count has been retrieved and saved as the file q6.txt. It contains information on the numbers of various types of dwellings in the various neighbourhoods in Saskatoon( as of 2016). Each dwelling is classified as either single family, two unit or multi unit. The overall goal of the assignment is to determine which are the dense neighbourhoods with fewer that 40% single family dwellings. The input file is a tabular file with commas for delimiters (if you want a better view of what the data in the file looks like, open it in Excel, OpenOffice, or similar spreadsheet program; this will nicely visualize the data in columns for you).

To complete the assignment, do the following parts. Make sure each part is correct before moving on to the next one. <strong>The final three parts must be done with array slicing and array operations.</strong>

<ul>

 <li>Begin by opening and reading the file a6.txt into Python. Next, the first line in the file is discarded as it contains only column labels. The first line can be discarded by invoking the readline() method for file objects. Next, use the file to produce a Python list , referred to with variable dataList, whose items are lists containing the contents of each line. Each line is a list of strings. Print a slice of dataList containing the first two items.</li>

</ul>

The contents of this slice should be should be

[[’027f2eb8-dc58-4057-b120-afcfca01653a’, ’Parkridge’,

’4’, ’1136’, ’124’, ’329’, ’1589’, ’166’, ’409’, ’10’, ’4’],

[’07767a30-94e5-4f98-8904-4a0334cc7896’, ’Aspen Ridge’,

<table>

 <tbody>

  <tr>

   <td> </td>

  </tr>

 </tbody>

</table>

’’, ’’, ’’, ’’, ’’, ’’, ’’, ’’, ’’]]

In each line we are interested in the second item, which is the neighbourhood, the fourth item, which is the number of single family dwellings, the fifth item, which is the number of two unit dwellings, the sixth item which is the number of multiunit dwellings and the seventh item, which is the total number of dwellings in the neighbourhood

<ul>

 <li>As seen above, the second item in dataList is a list that contains a bunch of empty strings. All those empty strings indicate that, as of 2016, there was no known dwellings in the neighbourhood “Aspen Ridge”. In order to do our analysis, we need to change the empty strings to zeros for the items we use. In this part clean dataList by converting empty strings to zeros for the items whose index is 3,4,5, or 6 (The fourth through seventh items), in every row. After doing this the second item in dataList should look like</li>

</ul>

[’07767a30-94e5-4f98-8904-4a0334cc7896’, ’Aspen Ridge’, ’’, 0, 0, 0, 0, ’’, ’’, ’’, ’’] Print the second item in dataList to the console.

<ul>

 <li>Create a one dimensional numpy array neighbourhood that contains the names of the neighbourhoods. Also create a 2D numpy array dwelling where each row contains information about a single neighbourhood, and the first column is the number of single family dwellings, the second column is the number of two unit dwellings, the third column which is the number of multiunit dwellings and the fourth column is the total number of dwellings in the neighbourhood. These numbers should be integers. The first row of dwelling should look like [ 1136 124 329 1589] <strong>For full marks use list comprehesions rather than loops to do this. </strong>Print the first row of dwelling.</li>

</ul>

(d)Print out the shape attribute of both neighbourhood and dwelling

<table>

 <tbody>

  <tr>

   <td> </td>

  </tr>

 </tbody>

</table>

(77,) (77, 4)

(e)Some of the rows, or some of the columns ,can be selected from a 2D array by logically indexing with a 1D array. For example the following code

<table width="626">

 <tbody>

  <tr>

   <td width="626">import numpy as npa = np.array([[1,2,3],[4,5,6],[7,8,9]])print(a) z = np.array([True,False,True])print(z) c = a[z,:] print(c)d = a[:,z] print(d)</td>

  </tr>

 </tbody>

</table>




<table width="626">

 <tbody>

  <tr>

   <td width="626">[[1 2 3] [4 5 6][7 8 9]][ True False True][[1 2 3][7 8 9]][[1 3] [4 6][7 9]]</td>

  </tr>

 </tbody>

</table>




produces the following output

Remove the rows in in both neighbourhood and dwelling for neighbourhoods in which there are no  dwellings by doing the following. First create a 1d Boolean array nonzero where an item is TRUE if the corresponding neighbourhood has some dwellings. <strong>Do this by indexing </strong>every row and the fourth column of dwelling and comparing the value to zero. Next use nonzero to <strong>logically index </strong>both neighbourhood and dwelling, and then remove the empty neighbourhoods. Again print out the shape

attribute of both neighbourhood and dwelling.

<table>

 <tbody>

  <tr>

   <td> </td>

  </tr>

 </tbody>

</table>

(74,) (74, 4)

(f)Create an array notsingle which contains, for each remaining neighbourhood, the number of dwellings that are either two unit or multiunit. <strong>Do this without using a loop, by indexing dwelling. </strong>The first two items in notsingle should be 453 and 150. Print a slice of notsingle which contains the first two items.

<strong>Use array arithmetic </strong>to create an array dense_ratio which for each neighbourhood remaining contains the ratio of the dwellings which contains more than one unit to the total number of dwellings. The first two numbers in dense_ratio should be approximately 0.28508496 and 0.11169025 Print a slice of dense_ratio which contains the first two items.

(g) Create an array dense_boolean which is a boolean array which is True for a neighbourhood if the dense_ratio value for that neighbourhood is greater than 0.6. <strong>Do this using array operations and without using a loop</strong>. <strong>Use array logical indexing </strong>to print out the names of the dense neighbour-

hoods, ie those whose dense_ratio are greater than 0.6.

[’Airport Business Area’ ’Nutana SC’ ’Lakewood SC’ ’Blairmore SC’

’U of S Lands South MA’ ’West Industrial’ ’Wildwood’ ’Pleasant Hill’ ’Central Business District’ ’Nutana’ ’Kensington’ ’Confederation SC’

’Lawson Heights SC’ ’University Heights SC’ ’City Park’

<table>

 <tbody>

  <tr>

   <td> </td>

  </tr>

 </tbody>

</table>

’Central Industrial’]