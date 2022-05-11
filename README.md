## Exploring XXE - XML ​​External Entity and Tips

<h3>First of all, what is XXE ?</h3>

It is basically an application layer attack, where the attacker injects malicious XML code that will be processed through the DTD (Document Type Definition), creating an external entity and calling it to execute commands.

<h3>Let's get to know the structure of XML:
</h3>
To understand better, we first need to know the DTD (Document Type Definition). It will define the type of document, and whether or not it will be accepted in the XML structure, as the DTD will process the XML information and will also be responsible for exchanging data between the two different technologies.
<br>
As you can see below, the syntax is divided into tags, and the main tag is the one that contains the others, for example in our case it is the John tag, it is called the root tag and what is contained in it are the attributes from prok3z.<br>
<img src="https://user-images.githubusercontent.com/43358190/167747285-05943069-98a1-415c-88e7-c99f501fd5c6.png">
<br>
Considering that the vulnerability consists of creating an external entity to send malicious commands that will be called within a tag contained in the root tag, I will start to put this into practice in the postswuigger lab and show better examples
