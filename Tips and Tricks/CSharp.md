
# How to use Voice tag properly?

Tags for modifying how the voice says text can be used in one of two ways.  
* The first is by inserting the tags and the text they surround into the say as text, using AddText.

* The second is to append them on as children TwiML using Append.

Which method you should use depends on the vocie you are using.  If the voice is an Amazon Polly voice, then use Append.  Otherwise, use AddText.  

Using the incorrect method can cause things like the tag being read out literally by the voice, or cause a Gather's time out to be ignored (Which can happen when you Append a Pause to a Say in a Gather).

# What happens when the text that is surrounded by a tag is empty?

If that is the case, it may just read out the tags literally.

# How to keep track of call information without putting it in the URI?

Since all calls have a call sid, we can store information to a call in a static dictionary or concurrent dictionary, using the call sid as the key.  This will let you store data that would be too difficult to put into the URI.  Just make sure to remove an entry for a call sid once the call is completed.  Also, you may want to record that data onto a file for debugging purposes, along with the call sid, just in case something went wrong.

#  Did you know you can make your own TwiML?

I was surprised too.  TwiML is not a sealed class, so you can make classes that inherit from it.  Now, what Twilio does with these custom classes is beyond our control, but you might be able to find some use for them on your side of your project.
