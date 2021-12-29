# Phishing D
## Step -1 : Data preprocessing
- This dataset contains few website links (Some of them are legitimate websites and a few are fake websites)
- Pre-Processing the data before building a model and also Extracting the features from the data based on certain conditions

## Split the Data
- We need to split the data according to parts of the URL
- A typical URL could have the form http://www.example.com/index.html, which indicates a protocol (http), a hostname (www.example.com), and a file name (index.html).
- Domain name column can be further sub divided into domain_names as well as sub_domain_names
- Similarly, address column can also be further sub divided into path,query_string,file..................

# Feature Extraction
- Feature-1
  1.Long URL to Hide the Suspicious Part
  If the length of the URL is greater than or equal 54 characters then the URL classified as phishing
  0 --- indicates legitimate
  1 --- indicates Phishing
  2 --- indicates Suspicious




