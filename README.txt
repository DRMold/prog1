Project 1
README.txt

TEAM MEMBERS:
Ritchie Hofmann
Sarah Baldwin

CSC 4351-001
Dr. Baumgartner
Spring 2016
Due February 4th, 2016


HOW PROGRAM WAS DESIGNED & WHAT WORKS/WHAT DOESN'T:

- Lexical Analyzer




IMPLEMENTATION:

First, we implemented the identifiers and special characters using <YYINITIAL> which was pretty straight forward after seeing the reference to the Jlex and studying its syntax. We just had to make each word and special character return the corresponding token.

Next, we worked on implementing the Comments which had to be a "initialized" with the <YYINITIAL> which then directed it to functions marked with <COMMENT> to handle reading in the symbols that represent a comment and the string of characters between the symbols to make sure it ignored it and wouldn't treat it like a function. We had to add a custom newline for <COMMENT> or when we first tested it, it didn't recognize the newline as being appropriate for comments.

Afterwards, the focus was on implementing Strings with <STRING> & <ESCAPESTRING> and therefore making sure the analyzer recognizes the end of a line, tab, control key character (\^c), single character with ASCII code (\ddd), double quote, backslash, and sequence of formatting characters (\f__f\) including space, tab, newline, formfeed. This was the hardest part of the project, namely the implementation of \ddd, \^c, \f__f\ but \f__f\ ended up being one line of Jlex code. \^c was delegating ASCII code to appropriate digits, and lastly the \ddd which needed a string buffer to capture all three digits [0-9] to make sure it accounts for three digits at a time to get the corresponding ASCII character.

TESTING:

We tested after each part that was implemented above, and a final one was done when completed, with a test.tig file which contained all tokens and possible input, as well as, some incorrect input to check for errors and exception handling.

ISSUES: There should be NO issues with the Lexical Analyzer. Everything should be implemented and functioning properly.