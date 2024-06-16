SOLUTIION TO 0x03. Log Parsing
BY EKENG


7. Input and Output
There are several ways to present the output of a program; data can be printed in a human-readable form, or written to a file for future use. This chapter will discuss some of the possibilities.

7.1. Fancier Output Formatting
So far we’ve encountered two ways of writing values: expression statements and the print() function. (A third way is using the write() method of file objects; the standard output file can be referenced as sys.stdout. See the Library Reference for more information on this.)

Often you’ll want more control over the formatting of your output than simply printing space-separated values. There are several ways to format output.

To use formatted string literals, begin a string with f or F before the opening quotation mark or triple quotation mark. Inside this string, you can write a Python expression between { and } characters that can refer to variables or literal values.

>>>
year = 2016
event = 'Referendum'
f'Results of the {year} {event}'
'Results of the 2016 Referendum'
The str.format() method of strings requires more manual effort. You’ll still use { and } to mark where a variable will be substituted and can provide detailed formatting directives, but you’ll also need to provide the information to be formatted. In the following code block there are two examples of how to format variables:

>>>
yes_votes = 42_572_654
total_votes = 85_705_149
percentage = yes_votes / total_votes
'{:-9} YES votes  {:2.2%}'.format(yes_votes, percentage)
' 42572654 YES votes  49.67%'
Notice how the yes_votes are padded with spaces and a negative sign only for negative numbers. The example also prints percentage multiplied by 100, with 2 decimal places and followed by a percent sign (see Format Specification Mini-Language for details).

Finally, you can do all the string handling yourself by using string slicing and concatenation operations to create any layout you can imagine. The string type has some methods that perform useful operations for padding strings to a given column width.

When you don’t need fancy output but just want a quick display of some variables for debugging purposes, you can convert any value to a string with the repr() or str() functions.

The str() function is meant to return representations of values which are fairly human-readable, while repr() is meant to generate representations which can be read by the interpreter (or will force a SyntaxError if there is no equivalent syntax). For objects which don’t have a particular representation for human consumption, str() will return the same value as repr(). Many values, such as numbers or structures like lists and dictionaries, have the same representation using either function. Strings, in particular, have two distinct representations.


