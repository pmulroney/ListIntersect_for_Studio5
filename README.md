# ListIntersect

Omnis Lists are powerful constructs that allow us to manipulate data in memory.  A common operation is selecting lines in the list, often based on another list.  Omnis Lists are powerful constructs that allow us to manipulate data in memory.  A common operation is selecting lines in the list, often based on another list.  This routine is an optimised way of processing the list such that in the best case scenario only iterates through the smallest list once, and the worst case scenario only iterates through the longest list once.

This is really cool, so if you're going to pinch it, make sure you acknowledge us ok?

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
