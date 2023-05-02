Download Link: https://assignmentchef.com/product/solved-comp3220-assignment3-ruby-parser-part1
<br>
For this assignment, we will be wri7ng a parser that is able to parse an input file wri:en in our “<strong>Tiny</strong>” grammar. You should finish wri7ng the “<strong>Parser</strong>” class that I’ve provided. Your Parser class should <strong><u>print</u></strong>:

<ul>

 <li>Each 7me it enters or leaves a rule and what the rule is:</li>

</ul>

<em>Entering <strong>[RULE_NAME]</strong> Rule </em>

<em>Exi-ng <strong>[RULE_NAME] </strong>Rule </em>

There are two excep7ons: the <strong>ID</strong> and the <strong>INT</strong> rules. In this grammar, <strong>ID</strong> and <strong>INT</strong> are also Token names, so we will not print when we are “entering” or “exi7ng” those rules since we can just check the token type. <em> </em>

<ul>

 <li>Each 7me it recognizes a token and what the token was:</li>

</ul>

<em>Found <strong>[TOKEN_TYPE]</strong> Token: <strong>[LEXEME]</strong></em>

For rules with Epsilon defini7ons, you should also indicate if that defini7on was chosen: <em>Did not find <strong>[TOKEN_TYPE]</strong> or <strong>[TOKEN_TYPE]</strong> Token, choosing EPSILON produc-on </em>

<ul>

 <li>Something, every7me it catches an error: <em>Expected <strong>[TOKEN_TYPE]</strong> found <strong>[LEXEME]</strong> </em></li>

</ul>

When the error could have been mul7ple things, separate the token types with the word <strong><u>or</u></strong> <em>Expected <strong>[TOKEN_TYPE]</strong> or <strong>[TOKEN_TYPE]</strong> or <strong>[TOKEN_TYPE]</strong>  found <strong>[LEXEME]</strong> </em>

<ul>

 <li>How many parse errors were found <em>There were <strong>[X]</strong> parse errors found.</em></li>

</ul>

<strong>Parser.rb</strong> extends <strong>Scanner.rb </strong>(The lexer that you wrote for your last assignment) and provides a framework for a topdown, recursive-descent parser of the <strong>TINY</strong> language. The parser stays one token ahead in the Token stream

<strong>(@lookahead</strong>) and uses the Token to predict how to con7nue parsing the current instruc7on and which method to call next.

The <strong>consume()</strong> method calls <strong>nextToken()</strong> in the scanner. The current <strong>@lookahead</strong> Token is discarded, and the next Token in the stream is retrieved. Whitespace Tokens are discarded.

The <strong>match(dtype)</strong> method tries to match the <strong>@lookahead</strong> Token with the provided type (<strong>dtype</strong>). If a match is found, <strong>consume()</strong> is called to retrieve the next Token. Otherwise an error message is displayed and then <strong>consume()</strong> is called to retrieve the next token.

The <strong>program()</strong> method is first called to parse a <strong>TINY</strong> program. Since a <strong>TINY</strong> program consists of a sequence of statements, <strong>program()</strong> calls <strong>statement()</strong> repeatedly un7l it encounters the <strong>EOF</strong> token.

Complete the parser by providing methods for the appropriate BNF rules in <strong>TINY</strong>.

I have given you my <strong>lexer</strong> and <strong>token</strong> ruby classes. I have also par7ally wri:en the <strong>parser</strong> for you and have wri:en a <strong>main.rb</strong> file that can run your ruby parser. Your assignment is to <strong><u>FINISH WRITING THE PARSER</u></strong> (parser.rb). I have also included 5 sample input files that you can use to test your program once you’ve finished wri7ng it.  <strong>input[1-3].txt</strong> should complete with no parse errors.  <strong>input[4-5].txt</strong> should have parse errors.

Below are screenshots of what your output should look like, based on the input files I’ve provided.





