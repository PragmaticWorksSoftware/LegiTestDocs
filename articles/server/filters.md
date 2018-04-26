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