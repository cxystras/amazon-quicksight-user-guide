# extract Function<a name="extract-function"></a>

`extract` returns a specified portion of a date value\. Requesting a time\-related portion of a date that doesn't contain time information returns 0\.

`extract` is supported for use with analyses based on SPICE data sets\.

## Syntax<a name="extract-function-syntax"></a>

```
extract('period', date)
```

## Arguments<a name="extract-function-arguments"></a>

 *period*   
The period that you want extracted from the date value\. Valid periods are as follows:  

+ YYYY: This returns the year portion of the date\.

+ MM: This returns the month portion of the date\.

+ DD: This returns the day portion of the date\.

+ WD: This returns the day of the week as an integer, with Sunday being 1\.

+ HH: This returns the hour portion of the date\.

+ MI: This returns the minute portion of the date\.

+ SS: This returns the second portion of the date\. \(Not supported when added inside SPICE\-based analyses\.\)

 *date*   
A date field or a call to another function that outputs a date\.

## Return Type<a name="extract-function-return-type"></a>

Integer

## Example<a name="extract-function-example"></a>

The following example extracts the day from a date value\.

```
extract('DD', {order date})
```

The following are the given field values\.

```
order date      
=========
01/01/14  
09/13/16
```

For these field values, the following values are returned\.

```
01
13
```