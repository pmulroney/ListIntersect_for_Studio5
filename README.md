# ListIntersect

Omnis Lists are powerful constructs that allow us to manipulate data in memory.  A common operation is selecting lines in the list, often based on another list.  A fairly simple way to do this would be to have two nested loop operations like the following pseudocode:

```omnis
For vList1.$line from 1 to vList1.$linecount step 1
   For vList2.$line from 1 to vList2.$linecount step 1
      If vList1.field=vList2.field
         Select list line(s) {#L}
   End For
End For
```

For this code, it executes the inner loop n x m times - where n = list 1 linecount, and m = list 2 linecount. If List 1 or List 2 are large, then you could be executing the inner loop millions of times, and take a significant amount of time to do so.

This is where the $ListIntersect() function comes in.  This method has been written so that you only process the smallest list *once*, which results n a significant performance increase.

## USAGE
```omnis
oListInterection.$ListIntersect(plList1,plList2,psFieldname,psFieldtype)
```
IN: 
* plList1 - the larger of the two lists to process.  It can have duplicate values in the column that you're testing
* plList2 - the smaller of the two lists.
* psFieldname - the column name in the list that you're comparing again
* psFieldtype - options are Char, Int, Num or Date.
OUT: All lines in list1 that exist in list2 will be selected in list1.

## NOTE
Both lists will be sorted by the nominated field name.
The comparison column must be the same name/type in both lists.

## EXAMPLE
See Example1 for a trivial example of this method in operation.  For a given list of cities/states in Australia, only select lines for a number of cities
In our software we use it as part of our search filtering process for some reports.

## AUTHORS
@pmulroney, submitted on behalf of Logical Developments

## Contributing
1. Fork this repository
1. Add a branch for your feature
1. Add the feature and perform a new JSON export
1. Submit a pull request
