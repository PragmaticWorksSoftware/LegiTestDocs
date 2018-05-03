# Filters

Filters change the behaviour of the parameter. Filters proceed the pramater name with a pipe character separating each filter. Some filters
need extra arguments. These arguments proceed their respective filter by a colon and a comma-separated list.

## append

Adds the parameter to the beginning of the argument.

__Syntax :__ `{{ <Parameter> | append: <String Values> }}`

__Example 1 :__ 
 * _Input_ - `{{ 'First' | append: 'Second' }}`
 * _Output_ - `FirstSecond`

__Example 2 :__
* _InputParameter Value_ - `'input'`
* _Input_ - `{{ InputParameter | append: 'Second' }}`
* _Output_ - `'inputSecond'`

## capitalize

Capitalizes words within the parameter.

__Syntax :__ `{{ <Parameter> | capitalize }}`

__Example 1 :__ 
 * _Input_ - `{{ 'one two three four' | capitalize }}`
 * _Output_ - `One Two Three Four`

__Example 2 :__
* _InputParameter Value_ - `'the quick brown fox'`
* _Input_ - `{{ InputParameter | capitalize }}`
* _Output_ - `'The Quick Brown Fox'`

## ceil

Rounds a numerical parameter to the nearest integer.

__Syntax :__ `{{ <Parameter> | ceil }}`

__Example 1 :__ 
 * _Input_ - `{{ 3.14 | ceil }}`
 * _Output_ - `4`

__Example 2 :__
* _InputParameter Value_ - `19.7`
* _Input_ - `{{ InputParameter | ceil }}`
* _Output_ - `20`

## date

Reformats a date parameter using specified format.

__Syntax :__ `{{ <Parameter> | date: <String Value> }}`

| __Flag__ | __Description__                                 | __Flag__ | __Description__                                  |
|----------|-------------------------------------------------|----------|--------------------------------------------------|
| %a       | Abbreviated Weekday                             | %A       | Full Weekday Name                                |
| %b       | Abbreviated Month Name                          | %B       | Full Month Name                                  |
| %c       | Preferred local date and time representation    | %d       | Day of the month, zero-padded                    |
| %-d      | Day of the month, not zero-padded               | %D       | Fromats the date (dd/mm/yy)                      |
| %e       | Day of the month, blank-padded                  | %F       | Returns the date in ISO 8601 format (yyyy-mm-dd) |
| %H       | Hour of the dat, 24-hour clock, zero-padded     | %I       | Hour of the dat, 12-hour clock                   |
| %j       | Day of the year                                 | %k       | Hour of the day, 24-hour clock, non-zero padded  |
| %m       | Month of the year                               | %M       | Minute of the hour                               |
| %p       | Meridian indicator                              | %r       | 12 - hour time without seconds                   |
| %R       | 24-hour time without seconds                    | %T       | 24-hour time with seconds                        |
| %U       | Week of the year starting with the first Sunday | %W       | Week of the year starting with the first Monday  |
| %w       | Day of the week starting with Sunday            | %x       | Preferred representation for the data            |
| %X       | Preferred representation for the time           | %y       | Year without century                             |
| %Y       | Year with century                               | %z       | Time zone name                                   |

__Example 1 :__ 
 * _Input_ - `{{ '2015-06-25' | date: '%A, %B %d, %Y }}`
 * _Output_ - `Thursday, June 25, 2015`

__Example 2 :__
* _InputParameter Value_ - `2009-05-08T10:30:00`
* _Input_ - `{{ InputParameter | date 'The year was %Y, the month was %b, the day was %d and the time was %I' }}`
* _Output_ - `The year was 2009, the month was May, the day was 08 and the time was 10:30`

## default

Returns the provided value. If the parameter value is empty or not provided, then it will return the given default value.

__Syntax :__ `{{ <Parameter> | default: <String Value> }}`

__Example 1 :__ 
 * _InputParamter Value_ - 
 * _Input_ - `{{ InputParameter | default: 'This is a default value' }}`
 * _Output_ - `This is a default value`

__Example 2 :__
* _InputParameter Value_ - `This is a custom value`
* _Input_ - `{{ InputParameter | default: 'This is a default value' }}`
* _Output_ - `This is a custom value`

## divided_by

Integer division. Divides the first integer parameter by the second value.

__Syntax :__ `{{ <Parameter> | divided_by: <Integer Value> }}`

__Example 1 :__
 * _Input_ - `{{ 13 | divided_by: 5 }}`
 * _Output_ - `2`

__Example 2 :__
* _InputParameter Value_ - `42`
* _Input_ - `{{ InputParameter | divided_by: 8 }}`
* _Output_ - `5`

## downcase
 
Converts all letters withing the parameter to lowercase.

__Syntax :__ `{{ <Parameter> | downcase }}`

__Example 1 :__
 * _Input_ - `{{ 'LOUD NOISES' | downcase }}`
 * _Output_ - `'loud noises'`

__Example 2 :__
* _InputParameter Value_ - `'I DO NOT KNOW WHY I AM SCREAMING`
* _Input_ - `{{ InputParameter | downcase }}`
* _Output_ - `'i do not know why i am screaming'`

## floor 

Rounds a numerical parameter down to the nearest integer.

__Syntax :__ `{{ <Parameter> | floor }}`

__Example 1 :__
 * _Input_ - `{{ 3.14 | floor }}`
 * _Output_ - `3`

__Example 2 :__
* _InputParameter Value_ - `19.7`
* _Input_ - `{{ InputParameter | floor }}`
* _Output_ - `19`

## lstrip

Removes all white space from the beginning of the parameter.

__Syntax :__ `{{ <Parameter> | lstrip }}`

__Example 1 :__
 * _Input_ - `{{ '    These are the voyages of the starship Enterprise' | lstrip }}`
 * _Output_ - `'These are the voyages of the startship Enterprise'`

__Example 2 :__
* _InputParameter Value_ - `'            Space, the final frontier     '`
* _Input_ - `{{ InputParameter | lstrip }}`
* _Output_ - `'Space, the final frontier     '`

## minus

Subtraction. Subtracts a numerical parameter with a second value.

__Syntax :__ `{{ <Parameter> | minus: <Integer Value> }}`

__Example 1 :__
 * _Input_ - `{{ 13 | minus: 5 }}`
 * _Output_ - `8`

__Example 2 :__
* _InputParameter Value_ - `42`
* _Input_ - `{{ InputParameter | minus: 8 }}`
* _Output_ - `34`

## modulo

Remainder. Returns the remainder after dividing the integer parameter by the filter parameter.

__Syntax :__ `{{ <Parameter> | modulo: <Integer Value> }}`

__Example 1 :__
 * _Input_ - `{{ 13 | modulo: 5 }}`
 * _Output_ - `3`

__Example 2 :__
* _InputParameter Value_ - `42`
* _Input_ - `{{ InputParameter | modulo: 8 }}`
* _Output_ - `2`

## pluralize

Returns the second string if the parameter is greater than one. Otherwise returns the first string.

__Syntax :__ `{{ <Parameter> | pluralize: <Singular Value>, <Plural Value> }}`

__Example 1 :__
 * _Input_ - `{{ 1 | pluralize: 'student', 'students' }}`
 * _Output_ - `student`

__Example 2 :__
* _InputParameter Value_ - `3`
* _Input_ - `{{ InputParameter | pluralize: 'student', 'students' }}`
* _Output_ - `students`

## plus

Addition. Adds a numerical parameter with a second value.

__Syntax :__ `{{ <Parameter> | plus: <Integer Value> }}`

__Example 1 :__
 * _Input_ - `{{ 13 | plus: 5 }}`
 * _Output_ - `18`

__Example 2 :__
* _InputParameter Value_ - `42`
* _Input_ - `{{ InputParameter | plus: 8 }}`
* _Output_ - `50`

## prepend

Adds the parameter to the end of the argument.

__Syntax :__ `{{ <Parameter> | prepend: <String Value> }}`

__Example 1 :__
 * _Input_ - `{{ 'First' | prepend: 'Second' }}`
 * _Output_ - `'SecondFirst'`

__Example 2 :__
* _InputParameter Value_ - `'input'`
* _Input_ - `{{ InputParameter | prepend: 'Second' }}`
* _Output_ - `'Secondinput'`

## remove_first

Removes the first occurence of the string value found within the parameter.

__Syntax :__ `{{ <Parameter> | remove_first: <String Value> }}`

__Example 1 :__
* _InputParameter Value_ - `'The following information has been REDACTED from view by the REDACTED.'`
* _Input_ - `{{ InputParameter | remove_first: 'REDACTED' }}`
* _Output_ - `'The following information has been  from view by the REDACTED.'`

## remove

Replaces all occurences of the dstring value found within the parameter.

__Syntax :__ `{{ <Parameter> | remove_first: <String Value> }}`

__Example 1 :__
* _InputParameter Value_ - `'The following information has been REDACTED from view by the REDACTED.'`
* _Input_ - `{{ InputParameter | remove: 'REDACTED' }}`
* _Output_ - `'The following information has been  from view by the .'`

## replace_first

Replaces the first occurence of the string value found within the parameter with the replacement value.

__Syntax :__ `{{ <Parameter> | replace_first: <Search>, <Replacement> }}`

__Example 1 :__
* _InputParameter Value_ - `'The following information has been REDACTED from view by the REDACTED.'`
* _Input_ - `{{ InputParameter | replace_first: 'REDACTED', 'censored' }}`
* _Output_ - `'The following information has been censored from view by the REDACTED.'`

## replace

Replaces all occurences of the string value found within the parameter with the replacement value.

__Syntax :__ `{{ <Parameter> | replace: <Search>, <Replacement> }}`

__Example 1 :__
* _InputParameter Value_ - `'The following information has been REDACTED from view by the REDACTED.'`
* _Input_ - `{{ InputParameter | replace: 'REDACTED', 'censored' }}`
* _Output_ - `'The following information has been censored from view by the censored.'`

## round

Rounds the numerical parameter to either the nearest integer or a specified number of decimals.

__Syntax :__ `{{ <Parameter> | round: <Integer Value> }}`

__Example 1 :__
 * _Input_ - `{{ 3.14 | round: 1 }}`
 * _Output_ - `3.1`

__Example 2 :__
* _InputParameter Value_ - `19.759876`
* _Input_ - `{{ InputParameter | round: 5 }}`
* _Output_ - `19.75988`

## rstrip

Removes all trailing whitespace from the parameter.

__Syntax :__ `{{ <Parameter> | lstrip }}`

__Example 1 :__
 * _Input_ - `{{ 'These are the voyages of the starship Enterprise     ' | rstrip }}`
 * _Output_ - `'These are the voyages of the startship Enterprise'`

__Example 2 :__
* _InputParameter Value_ - `'            Space, the final frontier     '`
* _Input_ - `{{ InputParameter | rstrip }}`
* _Output_ - `'            Space, the final frontier'`

## size

Returns the size of an array or string.

__Syntax :__ `{{ <Parameter> | size }}`

__Example 1 :__
 * _InputParameter Value_ - 
 * _Input_ - `{{ InputParameter | size }}`
 * _Output_ - `0`

__Example 2 :__
* _InputParameter Value_ - `'This is fifteen'`
* _Input_ - `{{ InputParameter | size }}`
* _Output_ - `15`

# slice

Returns a subset of the string parameter based on offset and length.

__Syntax :__ `{{ <Parameter> | slice: <Offset>, <Length> }}`

__Example 1 :__
 * _Input_ - `{{ 'This is fifteen' | slice: -7, 7 }}`
 * _Output_ - `'fifteen'`

__Example 2 :__
* _InputParameter Value_ - `'Four score and seven years ago'`
* _Input_ - `{{ InputParameter | slice: 5, 15 }}`
* _Output_ - `'score and seven'`

## times

Multiplication. Multiplies the input parameter by a numerical value.

__Syntax :__ `{{ <Parameter> | times: <Numerical Value> }}`

__Example 1 :__
 * _Input_ - `{{ 13 | times: 5 }}`
 * _Output_ - `65`

__Example 2 :__
* _InputParameter Value_ - `42`
* _Input_ - `{{ InputParameter | times: 8 }}`
* _Output_ - `336`


## truncate

Returns a specific number of characters from a string.

__Syntax :__ `{{ <Parameter> | truncate: <Truncate>[, <Append>] }}`

__Example 1 :__
 * _Input_ - `{{ 'This is fifteen' | truncate: 8, 'SPARTA' }}`
 * _Output_ - `'This is SPARTA'`

__Example 2 :__
* _InputParameter Value_ - `'Four score and seven years ago'`
* _Input_ - `{{ InputParameter | truncate: 5 }}`
* _Output_ - `'Four '`

## truncatewords

Returns a specific number of words from a string.

__Syntax :__ `{{ <Parameter> | truncate: <Truncate> }}`

__Example 1 :__
 * _Input_ - `{{ 'This is fifteen' | truncatewords: 2 }}`
 * _Output_ - `'This is'`

__Example 2 :__
* _InputParameter Value_ - `'Four score and seven years ago'`
* _Input_ - `{{ InputParameter | truncatewords: 3 }}`
* _Output_ - `'Four score and'`

## upcase

Converts all letters within the parameter to uppercase.

__Syntax :__ `{{ <Parameter> | upcase }}`

__Example 1 :__
 * _Input_ - `{{ 'loud noises' | upcase }}`
 * _Output_ - `'LOUD NOISES'`

__Example 2 :__
* _InputParameter Value_ - `'i do not know why i am screaming'`
* _Input_ - `{{ InputParameter | upcase }}`
* _Output_ - `'I DO NOT KNOW WHY I AM SCREAMING'`