Title: Script Python convert string in base64 to hex
Date: 2013-04-19 10:59
Author: ramborg
Category: Programming
Tags: python, script
Slug: script-python-convert-string-in-base64-to-hex

[code language="python"]  
:::python
<
import sys  
import base64  
\#import binascii\</code\>

\#Controlamos que tenga argumento  
if(len(sys.argv)!=2):  
print 'usage: convert\_base64\_to\_hex.py &lt;DigestValue&gt;'  
sys.exit(2)

base64string = sys.argv[1]

print base64.decodestring(base64string).encode('hex')  
\#print binascii.a2b\_base64(base64string).encode('hex')  
>
[/code]

The commented is an alternative way for conversion. I add link to gist
[snippet][]

  [snippet]: https://gist.github.com/ramsys/5419469
