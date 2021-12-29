# Detection Of Phishing Website
## Step -1 : Data preprocessing
- This dataset contains few website links (Some of them are legitimate websites and a few are fake websites)
- Pre-Processing the data before building a model and also Extracting the features from the data based on certain conditions

 ![Alt Text](https://github.com/omkara18/Detection-Phishing-Website-Using-MI/blob/master/Detection_Phishing%20Website_V1.0/photos/preprocessing.png)


## Split the Data
- We need to split the data according to parts of the URL
- A typical URL could have the form http://www.example.com/index.html, which indicates a protocol (http), a hostname (www.example.com), and a file name (index.html).
> Here we divided the protocol from the entire URL. 
> but need it to be divided it seperate column
![Alt Text](https://github.com/omkara18/Detection-Phishing-Website-Using-MI/blob/master/Detection_Phishing%20Website_V1.0/photos/separation.png)

# Feature Extraction
## Feature-1:Long URL to Hide the Suspicious Part
- If the length of the URL is greater than or equal 54 characters then the URL classified as phishing
```sh
 0 ---> indicates legitimate
 1 ---> indicates Phishing
 2 ---> indicates Suspicious
 ```
 ![Alt Text](https://github.com/omkara18/Detection-Phishing-Website-Using-MI/blob/master/Detection_Phishing%20Website_V1.0/photos/long-url.png)
## Feature-2:URL’s having “@” Symbol
- Using “@” symbol in the URL leads the browser to ignore everything preceding the “@” symbol and the real address often follows the “@” symbol.
- IF {Url Having @ Symbol→ `Phishing` Otherwise→ `Legitimate`}
```sh
0 ---> indicates legitimate
1 ---> indicates Phishing 
```
![Alt Text](https://github.com/omkara18/Detection-Phishing-Website-Using-MI/blob/master/Detection_Phishing%20Website_V1.0/photos/symbol.png)
## Feature-3:Redirecting using “//”
- The existence of “//” within the URL path means that the user will be redirected to another website. An example of such URL’s is: “http://www.legitimate.com//http://www.phishing.com”. We examine the location where the “//” appears. We find that if the URL starts with “HTTP”, that means the “//” should appear in the sixth position. However, if the URL employs “HTTPS” then the “//” should appear in seventh position.
- IF {ThePosition of the Last Occurrence of "//" in the URL > 7→ `Phishing` Otherwise→ `Legitimate`}
```sh
0 ---> indicates legitimate
1 ---> indicates Phishing 
```
![Alt Text](https://github.com/omkara18/Detection-Phishing-Website-Using-MI/blob/master/Detection_Phishing%20Website_V1.0/photos/redirection.png)

## Feature-4:Adding Prefix or Suffix Separated by (-) to the Domain
- The dash symbol is rarely used in legitimate URLs. Phishers tend to add prefixes or suffixes separated by (-) to the domain name so that users feel that they are dealing with a legitimate webpage.
- For example http://www.Confirme-paypal.com/.
- IF {Domain Name Part Includes (−) Symbol → `Phishing` Otherwise → `Legitimate`}
```sh
1 --> indicates phishing
0 --> indicates legitimate
```
![Alt Text](https://github.com/omkara18/Detection-Phishing-Website-Using-MI/blob/master/Detection_Phishing%20Website_V1.0/photos/prefix_suffix.png)

## Feature-5:Sub-Domain and Multi Sub-Domains
- The legitimate URL link has two dots in the URL since we can ignore typing “www.”. 
- If the number of dots is equal to three then the URL is classified as “Suspicious” since it has one sub-domain. 
- However, if the dots are greater than three it is classified as “Phishy” since it will have multiple sub-domains
```sh
0 ---> indicates legitimate
1 ---> indicates Phishing
2 ---> indicates Suspicious
```
![Alt Text](https://github.com/omkara18/Detection-Phishing-Website-Using-MI/blob/master/Detection_Phishing%20Website_V1.0/photos/subdomain.png)


