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
<br>
<img src="https://user-images.githubusercontent.com/43358190/167747562-72934730-82da-4ad1-9e88-d12e48b4f784.png">
<h4>here we will choose any of these products to start exploiting the xxe vulnerability</h4><br>
<img src="https://user-images.githubusercontent.com/43358190/167747936-86774e82-d355-4870-a2f7-60a681baf422.png"><br>
As you can see, we have the option to check the stocks, and we will check the stock of this product<br>
now we should think about the following, how is this inventory checking happening on the backend side<br>
and then we start to analyze the behavior of the application
now we will get the request that it sends to the server
<br>
<img src="https://user-images.githubusercontent.com/43358190/167750068-e535a5f1-7363-4474-86e2-ab7c9ee08c20.png">
take a look at payload<br>
is an xml structure<br>
now we will copy this code<br>
now we will use curl to send our post request<br>
and throw it to a file called xml.txt<br>
first of all, I wanted to remind you that for us to solve this lab we will have to see the passwd file of the target<br>
<img src="https://user-images.githubusercontent.com/43358190/167751762-df320058-94dc-4945-a13c-3d3ef3112b00.png"><br>
let's get this url and using curl we will play our payload
<img src="https://user-images.githubusercontent.com/43358190/167751486-5b37050e-9e3b-4cc5-a81b-2e5ee2e92037.png"><br>
after copying the url
<img src="https://user-images.githubusercontent.com/43358190/167751691-f60d3a05-7a9e-49a4-b038-4c076c6de8c9.png">
and that's it, we were able to send the payload and it returned the /etc/passwd from the lab.

## Lab
https://portswigger.net/web-security/xxe/lab-exploiting-xxe-to-retrieve-files

## References
https://owasp.org/www-community/vulnerabilities/XML_External_Entity_(XXE)_Processing
