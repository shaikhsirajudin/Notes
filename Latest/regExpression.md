# Regular Expressions

![Snipet 1](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/reg1.PNG)

![Snipet 2](https://github.com/shaikhsirajudin/Notes/blob/master/images/how/reg2.PNG)

##  Letters: abc

-  Write a pattern that matches all three rows, it may be as simple as the common letters on each line.
 
match: abcdefg Success 
match: abcde Success 
match: abc 

- Matches all character
- Match ony first character
```
abc.*

abc

```

## Digits:  123
- Write a pattern that matches all the digits in the strings below, and notice how your pattern matches anywhere within the string, not just starting at the first character.

match: abc123xyzted 
match: define "123"
match: var g = 123; 

- typing the common numbers '123' from all the lines to see them match.
```
123

```


## Any Digit:  \d  
The character \d can be used in place of any digit from 0 to 9. The preceding slash distinguishes it from the simple d character and indicates that it is a metacharacter.

match: abc123xyzted 
match: define "123"
match: var g = 123;  

```

\d\d\d

```

## Any Non-digit character:  \D    

## Any Character: .   
The concept of a wildcard, which is represented by the . (dot) metacharacter, and can match any single character (letter, digit, whitespace, everything).

-  write a single pattern that can match the first three strings

match: cat  
match: 896 
match: ?=+ 

```
...

```


## Period: \.    
In order to specifically match a period, you need to escape the dot by using a slash \. accordingly.

- write a single pattern that can match the first three strings, but not the last (to be skipped). You may find that you will have to escape the dot metacharacter to match the period in some of the lines.

match: cat. 
match: 896. 
match: ?=+. 
skip: abc1 

- You can use '...\.' to match the first three (wildcard) characters, and escape the final wildcard meta-character to match the period instead. This ensures that it will not match the '1' in the fourth line.

```

...\.

```

## Only a, b, or c: [abc] 
The dot metacharacter is pretty powerful, but if we are matching phone numbers for example, we don't want to validate the letters "(abc) def-ghij" as being a valid number!

There is a method for matching specific characters using regular expressions, by defining them inside square brackets. 
For example, the pattern [abc] will only match a single a, b, or c letter and nothing else.


-  To match the first three strings, but not the last three strings. Notice how we can't avoid matching the last three strings if we use the dot, but have to specifically define what letters to match using the notation above.

match: can  
match: man  
match: fan  
skip : dan   
skip : ran  
skip : pan 

- You can use the expression '[cmf]an' to match only 'can', 'man' and 'fan' without matching any other line. As you will see in the next lesson, you can also use the inverse expression '[^drp]an' to match any three letter word ending with 'an' that does not start with 'd', 'r' or 'p'.

```

[cmf]an

[^drp]an

[^drp]..

```

## Not a, b, nor c:  [^abc]   
we use a similar expression that excludes specific characters using the square brackets and the ^ (hat). For example, the pattern [^abc] will match any single character except for the letters a, b, or c.

- a pattern that matches only the live animals (hog, dog, but not bog). Notice how most patterns of this type can also be written using the technique from the last lesson as they are really two sides of the same coin. By having both choices, you can decide which one is easier to write and understand when composing your own patterns.

match: hog  
match: dog  
skip : bog 

- The simplest solution to match any line that ends in 'og' but is not 'bog' would be the expression '[^b]og'. Alternatively, you could use what we learned from the previous lesson and use '[hd]og' to match 'hog' and 'dog' but not 'bog'. Note that it is slightly more restrictive expression because it limits the strings it can match.

```

[^b]..
[^b]og

```

## Characters a to z: [a-z]  
## Numbers 0 to 9: [0-9] 
 If we want to match a character that can be in a sequential range characters? Do we have no choice but to list them all out?

Tthe square bracket notation, there is a shorthand for matching a character in list of sequential characters by using the dash to indicate a character range. For example, the pattern [0-6] will only match any single digit character from zero to six, and nothing else. And likewise, [^n-p] will only match any single character except for letters n to p.

- the match and skip lines have a pattern, and use the bracket notation to match or skip each character from each line. Be aware that patterns are case sensitive and a-z differs from A-Z in terms of the characters it matches (lower vs upper case).



match: Ana  
match: Bob   
match: Cpc  
skip : aax  
skip : bby  
skip : ccz  

- All the characters are sequential, so you can use the different ranges in the expression '[A-C][n-p][a-c]' to match only the first three lines.
```
[^a-c]..

[A-C][n-p][a-c]

```

## Any Alphanumeric character: \w 
Multiple character ranges can also be used in the same set of brackets, along with individual characters. An example of this is the alphanumeric \w metacharacter which is equivalent to the character range [A-Za-z0-9_] and often used to match characters in English text.

- the match and skip lines have a pattern, and use the bracket notation to match or skip each character from each line. Be aware that patterns are case sensitive and a-z differs from A-Z in terms of the characters it matches (lower vs upper case).

match: Ana  
match: Bob   
match: Cpc  
skip : aax  
skip : bby  
skip : ccz  

```
[^a-c]\w.
[^a-c]\w+
[^a-c]\w\w

```

## Any Non-alphanumeric character: \W   

## m Repetitions: {m}  
how about the number of repetitions of characters that we want to match? One way that we can do this is to explicitly spell out exactly how many characters we want, eg. \d\d\d which would match exactly three digits.

A more convenient way is to specify how many repetitions of each character we want using the curly braces notation. For example, a{3} will match the a character exactly three times. 

- write a pattern that matches only the first two spellings by using the curly brace notation above.

match wazzzzzup  
match wazzzup  
skip wazup 

```
waz{3}z*up

```

## m to n Repetitions:  {m,n}  
Certain regular expression engines will even allow you to specify a range for this repetition such that a{1,3} will match the a character no more than 3 times, but no less than once for example.

This quantifier can be used with any character, or special metacharacters, for example w{3} (three w's), [wxy]{5} (five characters, each of which can be a w, x, or y) and .{2,6} (between two and six of any character).


- write a pattern that matches only the first two spellings by using the curly brace notation above.

match: wazzzzzup  
match: wazzzup  
skip : wazup 

- There are a couple 'z's in the first two lines we have to match, so the expression 'waz{3,5}up' will match all strings with that many 'z's.


```
waz{3,5}up

```


## Zero or more repetitions: *  
 imagine that you wrote a form that has a donation field that takes a numerical value in dollars. A wealthy user may drop by and want to donate $25,000, while a normal user may want to donate $25.

One way to express such a pattern would be to use what is known as the Kleene Star and the Kleene Plus, which essentially represents either 0 or more or 1 or more of the character that it follows (it always follows a character or group)

Below are a few simple strings that you can match using both the star and plus metacharacters.

match: aaaabcc 
match: aabbbbc 
match: aacc  
skip : a 

```
aa.*
```

## One or more repetitions: + 

to match the donations above, we can use the pattern \d* to match any number of digits, but a tighter regular expression would be \d+ which ensures that the input string has at least one digit.

These quantifiers can be used with any character or special metacharacters, for example a+ (one or more a's), [abc]+ (one or more of any a, b, or c character) and .* (zero or more of any character).

Below are a few simple strings that you can match using both the star and plus metacharacters.

match: aaaabcc 
match: aabbbbc 
match: aacc  
skip : a 

- There are at least two 'a's, zero or more 'b's, and at least one 'c' in each line to match, so you can use the expression ''aa+b*c+'' to represent this exactly.

- Alternatively, an even more restrictive expression would be 'a{2,4}b{0,4}c{1,2}' which puts both an upper and lower bound on the number of each of the characters.


```
aa+b*c+
a{2,4}b{0,4}c{1,2}

```

## Optional character: ?   
Another quantifier that is really common when matching and extracting text is the ? (question mark) metacharacter which denotes optionality. This metacharacter allows you to match either zero or one of the preceding character or group. For example, the pattern ab?c will match either the strings "abc" or "ac" because the b is considered optional.

Similar to the dot metacharacter, the question mark is a special character and you will have to escape it using a slash \? to match a plain question mark character in a string.

- write a pattern that uses the optionality metacharacter to match only the lines where one or more files were found. 

match: 1 file found? 
match: 2 files found?  
match: 24 files found? 
skip : No files found. 

- We can use the meta-character '\d' to match the number of files and use the expression '\d+ files? found\?' to match all the lines where files were found.

- Note that the first question mark applies to the preceding 's' character (for plurality), and the actual question mark at the end must be escaped to match the text.

```
\d+\Wfiles?\Wfound\?

```

## Any Whitespace: \s   

The most common forms of whitespace you will use with regular expressions are the space (␣), the tab (\t), the new line (\n) and the carriage return (\r) (useful in Windows environments), and these special characters match each of their respective whitespaces. In addition, a whitespace special character \s will match any of the specific whitespaces above and is extremely useful when dealing with raw input text.

Write a pattern that can match each line regardless of how much whitespace is between the number and the content.

match: 1.   abc   
match: 2.	abc  
match: 3.           abc  
skip : 4.abc 

We have to match only the lines that have a space between the list number and 'abc'. We can do that by using the expression '\d\.\s+abc' to match the number, the actual period (which must be escaped), one or more whitespace characters then the text.

If we had used the Kleene Star instead of the plus, we would also match the fourth line, which we actually want to skip.

```
\d.\s+abc

\d.\s+.*
```

## Any Non-whitespace character:  \S    

## Starts and ends: ^…$   
One way to tighten our patterns is to define a pattern that describes both the start and the end of the line using the special ^ (hat) and $ (dollar sign) metacharacters. In the example above, we can use the pattern ^success to match only a line that begins with the word "success", but not the line "Error: unsuccessful operation". And if you combine both the hat and the dollar sign, you create a pattern that matches the whole line completely at the beginning and end.

* Note that this is different than the hat used inside a set of bracket [^...] for excluding characters, which can be confusing when reading regular expressions.

- to match each of the strings below using these new special characters.

match: Mission: successful   
skip : Last Mission: unsuccessful   
skip : Next Mission: successful upon capture of target 

- The expression 'Mission: successful' will match anywhere in the text, so we need to use the starting and ending anchors in an expression '^Mission: successful$' to only match the full string that starts with 'Mission' and ends with 'successful'.


```
^M.*:\ss.*ful$

```

## Capture Group: (…)  
This is done by defining groups of characters and capturing them using the special parentheses ( and ) metacharacters. Any subpattern inside a pair of parentheses will be captured as a group. In practice, this can be used to extract information like phone numbers or emails from all sorts of data.

Imagine for example that you had a command line tool to list all the image files you have in the cloud. You could then use a pattern such as ^(IMG\d+\.png)$ to capture and extract the full filename, but if you only wanted to capture the filename without the extension, you could use the pattern ^(IMG\d+)\.png$ which only captures the part before the period.

- to write a regular expression that matches only the filenames (not including extension) of the PDF files below.

capture: file_record_transcript.pdf               file_record_transcript 
capture: file_07241999.pdf                        file_07241999 
skip   : testfile_fake.pdf.tmp   


- We only want to capture lines that start with "file" and have the file extension ".pdf" so we can write a simple pattern that captures everything from the start of "file" to the extension, like this '^(file.+)\.pdf$'.


```
(^f.+)\.

-- very specific
(^f.+)\.pdf$

```

## Capture Sub-group: (a(bc))   
Take the example from the previous lesson, of capturing the filenames of all the image files you have in a list. If each of these image files had a sequential picture number in the filename, you could extract both the filename and the picture number using the same pattern by writing an expression like ^(IMG(\d+))\.png$ (using a nested parenthesis to capture the digits).

The nested groups are read from left to right in the pattern, with the first capture group being the contents of the first parentheses group, etc.

-write an expression that matches and captures both the full date, as well as the year of the date.

capture: Jan 1987                      Jan 1987, 1987 
capture: May 1969                      May 1969, 1969  
capture: Aug 2011 

- This expression requires capturing two parts of the data, both the year and the whole date. This requires using nested capture groups, as in the expression '(\w+ (\d+))'.

-We can alternatively use \s+ in lieu of the space, to catch any number of whitespace between the month and the year.


```
(\w+\s(\d+))

```

## Capture all: (.*)   
all the quantifiers including the star *, plus +, repetition {m,n} and the question mark ? can all be used within the capture group patterns. This is the only way to apply quantifiers on sequences of characters instead of the individual characters themselves.

For example, if I knew that a phone number may or may not contain an area code, the right pattern would test for the existence of the whole group of digits (\d{3})? and not the individual characters themselves (which would be wrong). 


capture: 1280x720                        1280 720 
capture: 1920x1600                       1920 1600 
capture: 1024x768                        1024 768   

- This one is pretty clean, we just need to capture the two groups of digits as such '(\d+)x(\d+)'.
```

(\d+)x(\d+)

```

## Matches abc or def: (abc|def)    
Specifically when using groups, you can use the | (logical OR, aka. the pipe) to denote different possible sets of characters. In the above example, I can write the pattern "Buy more (milk|bread|juice)" to match only the strings Buy more milk, Buy more bread, or Buy more juice. 

([cb]ats*|[dh]ogs?) would match either cats or bats, or, dogs or hogs. Writing patterns with many conditions can be hard to read, so you should consider making them separate patterns if they get too complex.

write a conditional pattern that matches only the lines with small fuzzy creatures below.

match: I love cats  
match: I love dogs 
skip : I love logs 
skip : I love cogs 

- By using the logical or, we can match the first two lines by using the expression 'I love (cats|dogs)'. But logs and cogs are pretty cool too.

```
.*(cats|dogs)

```
## Other special characters 
- \b: matches the boundary between a word and a non-word character
the most common metacharacters to capture digits using \d, whitespace using \s, and alphanumeric letters and digits using \w, but regular expressions also provides a way of specifying the opposite sets of each of these metacharacters by using their upper case letters. For example, \D represents any non-digit character, \S any non-whitespace character, and \W any non-alphanumeric character (such as punctuation). Depending on how you compose your regular expression, it may be easier to use one or the other.

Additionally, there is a special metacharacter \b which matches the boundary between a word and a non-word character. It's most useful in capturing entire words (for example by using the pattern \w+\b).

One concept that we will not explore in great detail in these lessons is back referencing, mostly because it varies depending on the implementation. However, many systems allow you to reference your captured groups by using \0 (usually the full matched text), \1 (group 1), \2 (group 2), etc. This is useful for example when you are in a text editor and doing a search and replace using regular expressions to swap two numbers, you can search for "(\d+)-(\d+)" and replace it with "\2-\1" to put the second captured number first, and the first captured number second for example.

- Example 1
Go ahead and write regular expressions for the following examples.

capture: <a>This is a link</a>                               a 
capture: <a href='https://regexone.com'>Link</a>             a  
capture: <div class='test_style'>Test</div>                  div  
capture: <div>Hello <span>world</span></div>  

```
- It is a best practice to use a proper library to parse html, but to find simple tag names, you can use the expression '<(\w+)'.

- You can also capture tag contents '>([\w\s]*)<', or even attribute values '='([\w://.]*)'' if desired (not the goal of this problem though).
```

- Example 2
try to capture the name of the email, excluding the filter (+ character and afterwards) and domain (@ character and afterwards).

capture: tom@hogwarts.com                            tom  
capture: tom.riddle@hogwarts.com                     tom.riddle   
capture: tom.riddle+regexone@hogwarts.com            tom.riddle   
capture: tom@hogwarts.eu.com                         tom   
capture: potter@hogwarts.com                         potter   
capture: harry@hogwarts.com                          harry   
capture: hermione+regexone@hogwarts.com              hermione   


```

To extract the beginning of each email, we can use a simple expression '^([\w\.]*)' which will match emails starting with alphanumeric characters including the period. It will match up to the point in the text where it reaches an '@' or '+'.

Again, you should probably use a framework to match emails!


```

- Example 3

write a single regular expressions that matches the number and captures the proper area code.

capture: 415-555-1234                   415   
capture: 650-555-2345                   650   
capture: (416)555-3456                  416   
capture: 202 555 4567                   202   
capture: 4035555678                     403   
capture: 1 416 555 9292                 416  


```
To grab the area code from the phone numbers, we can simply capture the first three digits, using the expression '(\d{3})'.

However, to match the full phone number as well, we can use the expression '1?[\s-]?\(?(\d{3})\)?[\s-]?\d{3}[\s-]?\d{4}'. This breaks down into the country code '1?', the captured area code '\(?(\d{3})\)?', and the rest of the digits '\d{3}' and '\d{4}' respectively. We use '[\s-]?' to catch the space or dashes between each component.



```
- Example 4

Below are a few different formats of numbers that you might encounter. Notice how you will have to match the decimal point itself and not an arbitrary character using the dot metacharacter. If you are having trouble skipping the last number, notice how that number ends the line compared to the rest.

match: 3.14529 
match: -255.34 
match: 128 
match: 1.9e10 
match: 123,340.00 
skip : 720p 


```
The expression for this can be quite complicated when you take into account fractional numbers, exponents, and more.

For the above example, the expression '^-?\d+(,\d+)*(\.\d+(e\d+)?)?$' will match a string that starts with an optional negative sign, one or more digits, optionally followed by a comma and more digits, followed by an optional fractional component which consists of a period, one or more digits, and another optional component, the exponent followed by more digits.

This is not the only solution as there can be many expressions that can match these sets of number strings.



```


- Example 5

In this simple example, extract the filenames and extension types of only image files (not including temporary files for images currently being edited). Image files are defined as .jpg,.png, and .gif.



skip    :  .bash_profile  
skip    :  workspace.doc  
capture :  img0912.jpg img0912          jpg  
capture : updated_img0912.png           updated_img0912 png  
skip    : documentation.html  
capture : favicon.gif favicon           gif  
skip    : img0912.jpg.tmp  
skip    : access.lock  


```
We are only looking for image files ending with the 'jpg', 'png' and 'gif' file extensions, so we can capture all such filenames using the expression '(\w+)\.(jpg|png|gif)$'.



```

-  Example 6
We have previously seen how to match a full line of text using the hat ^ and the dollar sign $ respectively. When used in conjunction with the whitespace \s, you can easily skip all preceding and trailing spaces.

Write a simple regular expression to capture the content of each line, without the extra whitespace.


capture: 			The quick brown fox...                      The quick brown fox...   
capture:    jumps over the lazy dog.                            jumps over the lazy dog. 


We can just skip all the starting and ending whitespace by not capturing it in a line. For example, the expression '^\s*(.*)\s*$' will catch only the content.

```

^\s*(.*)\s*$

``` 
- Example 7

Your goal is to use any regular expression techniques that we've learned so far to extract the filename, method name and line number of line of the stack trace (they follow the form "at package.class.methodname(filename:linenumber)").

skip    : W/dalvikvm( 1553): threadid=1: uncaught exception   
skip    : E/( 1553): FATAL EXCEPTION: main    
skip    : E/( 1553): java.lang.StringIndexOutOfBoundsException   
capture : E/( 1553):   at widget.List.makeView(ListView.java:1727)                          makeView ListView.java 1727    
capture : E/( 1553):   at widget.List.fillDown(ListView.java:652)                           fillDown ListView.java 652   
capture : E/( 1553):   at widget.List.fillFrom(ListView.java:709)                           fillFrom ListView.java 709  

- This one can be tricky too, but we really just want to capture the method name, filename, and line number. This can be achieved using the expression '(\w+)\(([\w\.]+):(\d+)\)' in which the first capture group is the method, followed by an escaped parenthesis, followed by the filename, a colon, and finally the line number.

```
(\w+)\(([\w\.]+):(\d+)\)

(\w+)\(([\w]+\.[\w]+):([\d]+)\)
```

- Example 8

The scheme describes the protocol to communicate with, the host and port describe the source of the resource, and the full path describes the location at the source for the resource.

In the exercise below, try to extract the protocol, host and port of the all the resources listed.

capture: ftp://file_server.com:21/top_secret/life_changing_plans.pdf                    ftp file_server.com 21     
capture: https://regexone.com/lesson/introduction#section                               https regexone.com  
capture: file://localhost:4040/zip_file                                                 file localhost 4040  
capture: https://s3cur3-server.com:9999/                                                https s3cur3-server.com 9999  
capture: market://search/angry%20birds                                                  market search  

- We have to match each of the three components: 
•the protocols in our list are all alphanumeric, so they can be matched using '(\w+)://'
•The hosts can contain non-alphanumeric characters like the dash or the period, so we will have to specifically include those characters using '://([\w\-\.]+)' 
•The port is an optional part of the URI and is preceeded with a colon and can be matched using '(:(\d+))'


To put it all together, we then have the full regular expression '(\w+)://([\w\-\.]+)(:(\d+))?' to capture all the data we are looking for.

```

(\w+)://([\w-\.]+)(:(\d+))?
```


# Matching a string in C#

Method
```
Match match = Regex.Match(InputStr, Pattern, RegexOptions)
```
Example
```
// Lets use a regular expression to match a date string.
string pattern = @"([a-zA-Z]+) (\d+)";

// The RegexOptions are optional to this call, we will go into more detail about
// them below.
Match result = Regex.Match("June 24", pattern);
if (result.Success) {
    // Indeed, the expression "([a-zA-Z]+) (\d+)" matches the date string

    // To get the indices of the match, you can read the Match object's
    // Index and Length values.
    // This will print [0, 7], since it matches at the beginning and end of the 
    // string
    Console.WriteLine("Match at index [{0}, {1})", 
        result.Index,
        result.Index + result.Length);

    // To get the fully matched text, you can read the Match object's Value
    // This will print "June 24"
    Console.WriteLine("Match: {0}", result.Value);

    // If you want to iterate over each of the matches, you can call the 
    // Match object's NextMatch() method which will return the next Match
    // object.
    // This will print out each of the matches sequentially.
    while (result.Success) {
        Console.WriteLine("Match: {0}", result.Value);
        result = result.NextMatch();
    }
}

```

# Capturing groups
If we wanted to perform a global search over the whole input string and return all the matches with their corresponding capture data, we can instead use the static method Regex.Matches() to get a MatchCollection which can be iterated over and processed as in the example above.

Method
```
MatchCollection matches = Regex.Matches(InputStr, Pattern, RegexOptions)
```

Example
```
// Lets use a regular expression to capture data from a few date strings.
string pattern = @"([a-zA-Z]+) (\d+)";
MatchCollection matches = Regex.Matches("June 24, August 9, Dec 12", pattern);

// This will print the number of matches
Console.WriteLine("{0} matches", matches.Count);

// This will print each of the matches and the index in the input string
// where the match was found:
//   June 24 at index [0, 7)
//   August 9 at index [9, 17)
//   Dec 12 at index [19, 25)
foreach (Match match in matches) {
    Console.WriteLine("Match: {0} at index [{1}, {2})", 
        match.Value, 
        match.Index, 
        match.Index + match.Length);
}

// For each match, we can extract the captured information by reading the 
// captured groups.
foreach (Match match in matches) {
    GroupCollection data = match.Groups;
    // This will print the number of captured groups in this match
    Console.WriteLine("{0} groups captured in {1}", data.Count, match.Value);

    // This will print the month and day of each match.  Remember that the
    // first group is always the whole matched text, so the month starts at
    // index 1 instead.
    Console.WriteLine("Month: " + data[1] + ", Day: " + data[2]);

    // Each Group in the collection also has an Index and Length member,
    // which stores where in the input string that the group was found.
    Console.WriteLine("Month found at[{0}, {1})", 
        data[1].Index, 
        data[1].Index + data[1].Length);
}


```

# Finding and replacing strings
Another common task is to find and replace a part of a string using regular expressions, for example, to replace all instances of an old email domain, or to swap the order of some text. You can do this in C# with the static method Regex.Replace().

Method
```
string replaced = Regex.Replace(InputStr, Pattern, ReplacementPattern, RegexOption)

```
Example
```
// Lets try and reverse the order of the day and month in a few date 
// strings. Notice how the replacement string also contains metacharacters
// (the back references to the captured groups) so we use a verbatim 
// string for that as well.
string pattern = @"([a-zA-Z]+) (\d+)";

// This will reorder the string inline and print:
//   24 of June, 9 of August, 12 of Dec
// Remember that the first group is always the full matched text, so the 
// month and day indices start from 1 instead of zero.
string replacedString = Regex.Replace("June 24, August 9, Dec 12",
    pattern, @"$2 of $1");
Console.WriteLine(replacedString);


```