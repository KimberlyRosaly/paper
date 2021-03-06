# TITLE: Code Challenge Nostalgia with Regex
DATE: 4.29.2022

While I was working through the Flatiron boot-camp, I got quite familiar with the feeling of being overwhelmed when facing something for the first time. Code can be intimidating, for me, often terrifying, but genuinely always rewarding to embrace. 

Trying to stay up-to-date in my brain while venturing into the world of software engineering as a professional, oftentimes shows me how memory can be a tricky thing. All these concepts and challenging fundamentals can slip through the sieve of our minds because we're faced with so many technologies, so many rule-sets, so many patterns of implementation, on such a regular basis. We have to get comfortable with the idea that it's okay if we forget, as long as we know where to go when we sincerely do need the answers.

::whispers:: Plus, I heard this *dark* rumor, that even experienced coders forget things, including the basics, and refer to search engines all the time. I HEARD THIS THROUGH THE GRAPEVINE - it's a secret! Shhh!

Reading and research is a lot of fun for me because I enjoy dissecting things and categorizing, making analogous contrasts and comparisons, turning simple things into stories. It's just how I function as a human. Exploration and documentation is my home, regardless of any trepidation. I have a need to understand *things* so documentation becomes my ally and steady at my side.


Recently, I ran through some code challenges on codewars.com that really took me back in time to a place where people groan in agony and yet I can shine with a smile; I MADE NOTES to help guide my mind and fall in love with it..

# REGEX
*:cue screaming:*

---
## THE CODEWARS KATA
**DESCRIPTION :**

Return the number (count) of vowels in the given string.

We will consider a, e, i, o, u as vowels for this Kata (but not y).

The input string will only consist of lower case letters and/or spaces.

---
**MY SOLUTION :**
```
function getCount(str) {
  
  let regex = /[aeiou]/g
  let found = str.match(regex)
  let vowelsCount = found.length
  return vowelsCount
  
}
```
---
"First of all, what is 'Regex?'"

"Regex" or "regexp" is short for "regular expression," or "rational expression," and is a sequence of characters specified to search a pattern in text.**


"Okay, yeah, but what does the code mean?"

So, this function takes in an argument of a string. 
I declare a line that constructs a regular expression, specific characters listed within the brackets, and end it with a modifier that will grab all matches, rather than just the first it finds.
Then, the actual matching function is called on the string with my predefined regex tossed in as its parameter.
Since the challenge is asking for a count to be returned of all vowel matches in the string, I simply call the 'length' function on the returned array of matches and it tosses me back a number.
We did it! \o/

---
**MY NOTES :**
```
REGEX ] ]

		REGULAR EXPRESSIONS
		akaTEXT - MATCHING

	series of codes used to define what text you are looking for
	search through strings and blocks of text for specific patterns
	useful for:
	-data validation -searching  -mass file renaming  -finding records in a database
	conditionals are explicitly defined

	RUBULAR.com
	a Ruby regular expression editor
	test reg ex as you write them

	REGEXONE.COM/LESSON
	tutorials through RegEx

		*BEST PRACTICE to write as SPECIFIC
		       regular expressions as possible
		to ensure against false positives



METACHARACTERS
allow you to use a pre-defined shorthand to match specific characters
\d <---match any digit in your text
\w <---match any word character(letters, numbers, underscores)
\W  <--match the non-word characters in your text

/your regex/
in Ruby, regular expressions are generally written between forward slashes
this is the LITERAL alternative to creating
 a regular expression object with: 
Regexp.new('your regex')

/[abc]/
SPECIFIC CHARACTERS
matches any single characters within brackets

/[a-j]/
RANGES

/aa|ee|ii|ae/<----better written as: /[aeiou][aeiou]/   <--better written as: /[aeiou]{2}/
DOUBLES
curly braces surrounding - pattern or character directly preceding it must repeat that number of times

a{1,3}
matches the "a" character no less than 1 time and no more than 3 times

/regexp/g
"g" modifier specifies a global match : global match finds ALL matches (compared to only the first)

\.
to specifically match a period.
escape the dot (dot: wildcard that will match any single character (letter, digit, whitespace, etc)

[^g]rab <---matches crab but not grab
^ (hat) denotes INVERSE expression when inside brackets

\d
digit- any whole number

\D
anything OTHER than a digit/number

\s
space

\S
anything OTHER than a space

\w
any alphanumeric character

\W
anything OTHER than an alphanumeric character

\b
a space that precedes a whole word, the special metacharacter which matches the boundary between a word and a non-word character, useful in capturing entire words (\w+\b)

.
anything other than a line break
 
KLEENE STAR
*
represents 0 or more of the character that precedes it

KLEENE PLUS
+
represents 1 or more of the character that precedes it

?
denotes OPTIONALITY, allows you to match either zero or one of the preceding character or group

\?
to specifically match a question mark (escape usage of the metacharacter)

		WHITE SPACE CHARACTERS \s
_ (not underscore, actual space)
space

\t
tab

\n
new line

\r
carriage return
_____________________________________________________________________________

^pattern
match only a line that begins with the pattern

^pattern$
create a pattern that matches the whole line completely at the beginning and end

TO EXTRACT INFORMATION FOR FURTHER PROCESSING
define groups of characters within parenthesis
^(IMG\d+)\.png$

|
When using groups, logical OR, aka the pipe - denotes different possible sets of characters
(cat|dog|human)

\1   <-- or \0 \2 \3 etc.
back referencing
reference captured groups, useful when doing a search and replace
```
---
**RESOURCES :**

**    https://en.wikipedia.org/wiki/Regular_expression

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions

https://www.w3schools.com/jsref/jsref_regexp_g.asp
