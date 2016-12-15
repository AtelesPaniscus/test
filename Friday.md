I do not like this web interface.  Odd, because while I generally dislike GUIs, I generally like WUIs.

This is a paragraph that contain a list:
  * one
  * two
  * three
but this is not interpreted as I would expect.

I have tried converting such lists to html using:

  * python-markdown
  * pandoc
  
These worthy Mardown to html converters do not recognise the list without the blank lines.

Although the Mardown documentation (I've read several sources) says that a blank line starts a new paragraph,
both of the programs mentioned generate lists, they don't generate lists within paragraphs.
Perhaps they are forced to do this because markdown talks about paragraphs within lists.

That would be a real problem for crib tutor:
  * paragraphs equate to questions:  a list must fall within a paragraph to be considered a question
  * paragraphs within lists might 'work' but would not be considered questions in their own right.

I tried a script that uses the GitHub API directly but my OS is too old for the old Ruby dependency.
That is my fault.  I'm still trying to find the original Perl Mardown interpreter.

One thing is clear on GitHub is that the blank line is required at the end of a paragraph
and may be required at the beginning too.

I'm thinking of hacking it as follows: <p>

  * one
  * two
  * three
  
</p> will be interpreted as a stand-alone list.

But:

  * one
  * two
  * three
  
will not.
  
The workaround is to merge the list with paragraphs either side.
