# Template Tags

Most notifications need parameters sent alongside the request to function. Templates use these parameters within tags, which help to create blocks of logic within templates.

### General Syntax 

```
{% <Tag>[<Conditions>] %}
<Template Block>
{% <EndTag> %}
```

## case

Case tags control the display of information by choosing between a list of candidates.

__Syntax :__

```
{% case <Condition> %}
    {% when <Match> %>}
        <Template Block>
{% endcase %}
```

__Example :__

_InputParameter Value_ - 'Orange'

_Input :_

 ```
My favorite animal is:{% case InputParameter %}
{% when 'Black' %}
Zebra
{% when 'Blue' %}
Regal Tang
{% when 'Green' %}
Iguana
{% when 'Orange' %}
Fox
{% when 'Yellow' %}
Duck
{% endcase %}
```

_Output :_

```
My favorite animal is:
Fox
```

## comment

Comment tags hides the block from being outputted within a message.

__Syntax :__

```
{% comment %}
    <template Block>
{% endcomment %}
```

__Example :__

_Input :_ 

```
One... two... five!{% comment %}Three, sir.{% endcomment %} Three!
```

_Output :_

```
One... two... five! Three!
```

## cycle

Cycle tags alternate between a comma-separated list of items.

__Syntax :__
```
{% cycle [<Group Name>:] <item>,...n %}
```

__Example 1 :__

_Input :_

```
{% cycle 'Badger', 'Badger', 'Badger', 'Mushroom', 'Mushroom', 'Snake' %}
{% cycle 'Badger', 'Badger', 'Badger', 'Mushroom', 'Mushroom', 'Snake' %}
{% cycle 'Badger', 'Badger', 'Badger', 'Mushroom', 'Mushroom', 'Snake' %}
{% cycle 'Badger', 'Badger', 'Badger', 'Mushroom', 'Mushroom', 'Snake' %}
{% cycle 'Badger', 'Badger', 'Badger', 'Mushroom', 'Mushroom', 'Snake' %}
{% cycle 'Badger', 'Badger', 'Badger', 'Mushroom', 'Mushroom', 'Snake' %}
{% cycle 'Badger', 'Badger', 'Badger', 'Mushroom', 'Mushroom', 'Snake' %}
```

_Output :_
```
Badger
Badger
Badger
Mushroom
Mushroom
Snake
Badger
```

__Example 2 :__

_Input :_

```
{% cycle 'Numbers': '1', '2', '3', '4', '5' %}) {% cycle 'Sports': 'Soccer', 'Football', 'Rugby', 'Baseball' %}
{% cycle 'Numbers': '1', '2', '3', '4', '5' %}) {% cycle 'Sports': 'Soccer', 'Football', 'Rugby', 'Baseball' %}
{% cycle 'Numbers': '1', '2', '3', '4', '5' %}) {% cycle 'Sports': 'Soccer', 'Football', 'Rugby', 'Baseball' %}
{% cycle 'Numbers': '1', '2', '3', '4', '5' %}) {% cycle 'Sports': 'Soccer', 'Football', 'Rugby', 'Baseball' %}
{% cycle 'Numbers': '1', '2', '3', '4', '5' %}) {% cycle 'Sports': 'Soccer', 'Football', 'Rugby', 'Baseball' %}
{% cycle 'Numbers': '1', '2', '3', '4', '5' %}) {% cycle 'Sports': 'Soccer', 'Football', 'Rugby', 'Baseball' %}
```

_Output :_

```
1) Soccer
2) Football
3) Rugby
4) Baseball
5) Soccer
1) Football
```

## for

When using array parameters, for tags allow users the ability to loop through a collection.

__Syntax :__

```
{% for <item> in <Array>[Options] %}
    <Template Block>
{% endfor %}
```

__Options :__
* limit - `<Integer Value>` - Restricts the number of elements that will be looped thorugh.
* offset - `<Integer Value>` - Allows users to start looping at the nth element.
* reversed - Loops through the collection from last to first.

__Helper Variables :__
* forloop.length - Returns the length of the entire loop.
* forloop.index - Returns the index value of the current element [1, ..., n]
* forloop.index() - Returns the zero-based index value of the current element [0, ..., n]
* forloop.rindex - Returns the number of elements left to iterate through [1, ..., n]
* forloop.rindex() - Returns the zero-based number of elements left to iterate through [0, ..., n]
* forloop.first - Returns a Boolean value as to whether this is the first element within the loop
* forloop.last - Returns a Boolean value as to whether this is the last element within the loop

__Example :__

_Input :_
```
{% for error in InputParameters %}
Source - {{ error.Source }}
Time - {{ error.Time }}
Details - {{ error['Error Details'] }}
{% endfor %}
```

_Output :_

```
Source - Error 1
Time - Time 1
Details - Details 1

Source - Error 2
Time - Time 2
Details - Details 2

Source - Error 3
Time - Time 3
Details - Details 3
```

### break

Break tags immediately exits a for loop's template block.

__Syntax :__
```
{% for <Item> in <Array>[ Options] %}
    <Template Block>
    {% break %}
    <Template Block>
{% endfor %}
```

_Input :_
```
{% for error in InputParameters %}
    {% if forloop.index == 2 %}
        {% break %}
    {% endif %}
    Source - {{ error.Source }}
    Time - {{ error.Time }}
    Details - {{ error['Error Details'] }}
{% endfor %}
```

_Output :_
```
Source - Error 1
Time - Time 1
Details - Details 1
```

### continue

Continue tags immediately ends the current iteration and moves to the next element within the array.

__Syntax :__

```
{% for <Item> in <Array>[ Options] %}
    <Template Block>
    {% continue %}
    <Template Block>
{% endfor %}
```

_Input :_

```
{% for error in InputParameters %}
    {% if forloop.index == 2 %}
        {% continue %}
    {% endif %}
    Source - {{ error.Source }}
    Time - {{ error.Time }}
    Details - {{ error['Error Details'] }}
{% endfor %}
```

_Output :_

```
Source - Error 1
Time - Time 1
Details - Details 1

Source - Error 3
Time - Time 3
Details - Details 3
```

### else

Located at the end of a for loop, else tags display a template block only if there are no items within the array.

__Syntax :__

```
{% for <Item> in <Array>[ Options] %}
    <Template Block>
    {% else %}
    <Template Block>
{% endfor %}
```

_Input :_

```
{% for error in InputParameters %}
    Source - {{ error.Source }}
    Time - {{ error.Time }}
    Details - {{ error['Error Details'] }}
    {% else %}
        No errors!
{% endfor %}
```

_Output :_

```
No errors!
```

## if

__Syntax :__ 

```
{% if <Condition> %}
    <Template Block>
{% endif %}
```

_Boolean Operators :_
* and - both conditions must evaluate to true
* or - at least one condition must evaluate to true

_Comparison Operators :_

* == - Used with strings or numerical values. Returns true if the left side of the condition equals the right side
* != - Used with numerical values. Returns true if the left side of the condition does not equal the right side
* <> - Used with numerical values. Returns true if the left side of the condition does not equal the right side
* < - Returns true if the left side of the condition is numerically less than the right side
* <= - Used with numerical values. Returns true if the left side of the condition is numerically less than or equal to the right side
* \> - Used with numerical values. Returns true if the left side of the condition is numerically greater than the right side
* \>= - Used with numerical values. Returns true if the left side of the condition is numerically greater than or equal to the right side
* contains - Used with strings or array values. Returns true if the left side of the condition includes the right side of the condition within it.

__Example :__

_InputParameter Value :_
```
'Orange'
```

_Input :_
```
My favorite animal is:
{% if InputParameter == 'Orange' %}
    Fox
{% endif %}
```

_Output :_
```
My favorite animal is:
Fox
```

### elseif

__Syntax :__
```
{% if <Conditions> %}
    <Template Block>
    {% elseif <Conditions> %}
        <Template Block>
{% endif %}
```

__Example :__

_InputParameter Value :_
```
0
```

_Input :_
```
I like {% if InputParameter < 1 %}
    no
    {% elseif InputParameter == 1 %}
    one animal
    {% elseif InputParameter > 1 and InputParameter <= 4 %}
    a couple animals
    {% elseif InputParameter > 4 and InputParameter <= 6 %}
    a handful of different animals
    {% elseif InputParameter > 6 and InputParameter <= 9 %}
    several animals
    {% else %}
    a lot of animals
{% endif %}!
```

_Output :_
```
I like a handful of different animals!
```

### else

__Syntax :__
```
{% if <Conditions> %}
    <Template Block>
    {% else %}
        <Template Block>
{% endif %}
```

__Example :__

_InputParameter Value :_
```
'Green'
```

_Input :_
```
My favorite animal is:
    {% if InputParameter == 'Orange' %}
    Fox
    {% else %}
        Iguana
{% endif %}
```

_Output :_
```
My favorite animal is:
Iguana
```

## raw

Raw tags temporarily disable syntax processing. This allows users to generate content that would normally conflict with syntax.

__Syntax :__
```
{% raw %}
    <Template Block>
{% endraw %}
```

__Example :__

_Input :_
```
{% raw %}
I really need to use the mustache handlebar for my marvelously mustached smiley faces: :-{
% endraw %}
```

_Output :_
```
I really need to use the mustache handlebar for my marvelously mustached smiley faces: :-{
```

## unless

Like case and if tags, unless tags control the display of information based on a condition. Unlike if tags, an unless tag displays the template block only if the condition returns false. Unless tags cannot use elseif or else tags within them.

__Syntax :__ 

```
{% unless <Condition> %}
    <Template Block>
{% endunless %}
```

_Boolean Operators :_
* and - both conditions must evaluate to true
* or - at least one condition must evaluate to true

_Comparison Operators :_

* == - Used with strings or numerical values. Returns true if the left side of the condition equals the right side
* != - Used with numerical values. Returns true if the left side of the condition does not equal the right side
* <> - Used with numerical values. Returns true if the left side of the condition does not equal the right side
* < - Returns true if the left side of the condition is numerically less than the right side
* <= - Used with numerical values. Returns true if the left side of the condition is numerically less than or equal to the right side
* \> - Used with numerical values. Returns true if the left side of the condition is numerically greater than the right side
* \>= - Used with numerical values. Returns true if the left side of the condition is numerically greater than or equal to the right side
* contains - Used with strings or array values. Returns true if the left side of the condition includes the right side of the condition within it.

__Example :__

_InputParameter Value :_
```
'Orange'
```

_Input :_
```
My favorite animal is:
{% unless InputParameter == 'Orange' %}
    Not a Fox
{% endunless %}
```

_Output :_
```
My favorite animal is:
```
