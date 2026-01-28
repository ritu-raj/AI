This file's code shall help user in finding important details of Sellers who sell any product in any city which can be downloaded in excel format. 

Important Seller details that shall be provided include -

Seller Entity Name
Address
Phone Number
Annual Turnover (in Crores)
GST
Google Rating
Rating Count
& so on.

Code-details: Python and ADK has been used. A master agent (root_agent) orchestrates the workflow of fetching Seller-details by calling sub-agents which are mentioned in below steps:

Step1: 'SerpAPI_Seller_Agent' tool for getting a clean VALID JSON LIST of objects where each object (Seller entity data) contains:
       seller_entity_name, address, phone_number,
       annual_turnover_cr, gst, google_rating,
       rating_count, matched_product, city.

Step2: 'search_agent' tool to update the above step's structured JSON list of objects with 'GST' & 'Annual Turnover' values for each Seller. In case values are not found, they are populated as NA.
       
Step3: 'summarizer_agent' tool to provide a summary based on the relevant information of Step2

The final results from Step 2 and Step 3 are then published.


P.S. Although prompt-based solutions might seem to work (e.g. Google's AI mode, ChatGPT etc.), there is a problem with scale (i.e., the number of results from prompts will be limited - e.g. AI Mode did not
publish answer after 25 responses for a query - "Find seller details (Entity Name, GST, Annual Turnover, Google Rating) who sell TMT Bars in Chennai".
