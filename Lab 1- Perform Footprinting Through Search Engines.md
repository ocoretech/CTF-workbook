Lab 1 - Perform footprinting through search engines

Task 1: Gather Information using Advanced Google Hacking Techniques

Advanced Google hacking refers to the art of creating complex search engine queries by employing advanced Google operators to extract sensitive or hidden information about a target company from the Google search results.


We will consider EC-Council as a target organization.


Steps: 

1. Launch any browser, in this lab, we are using Mozilla Firefox. In the address bar of the browser type https://www.google.com and hit enter.

2. Once the Google search engine appears, type the following in the search bar, intitle:login site:eccouncil.org and press Enter.

3. This search command uses intitle and site Google advanced operators, which restrict results to pages on the eccouncil.org website that contain the login pages. 

**Note:** Advanced Google Search operator can help attackers and pen testers to extract login pages of the target organization's website.

4. Now erase everything in the search bar and type the command EC-Council filetype:pdf and press enter. Here, the file type pdf is searched for the target organization EC-Council.

**Note:** The PDF and other documents from a target website may provide sensitive information about the target's products and services.

5. Now, click on any link from the results to view the pdf file. The page appears displaying the PDF file. 

6. You can also use oprators such as allinurl, cache, inurl, allintitle, etc.








Task 2: Gather Information from Video Search Engines

Here, we will perform an advanced video search and reverse image search using the YouTube search engine and YouTube Metadata tool.

Consider EC-Council as a target organization.


Steps: 

1. Launch Mozilla Firefox and type youtube.com in the search bar and hit enter. Youtube page will appear. 

2.  In the search field, search for your target organization i.e. Ec-council. You will see all the latest videos uploaded by the target organization.

3. Select any video of your choice, right-click on the video title, and click Copy Link.

4. Open a new tab in Mozilla Firefox, type https://mattw.io/youtube-metadata/ in the search bar and press Enter.

5. YouTube Metadata page appears, in the Submit a link to a video paste the copied YouTube video location and click Submit.

6. Once the search is completed scroll down and you can observe the details related to the video such as published date and time, channel Id, title, etc., in the Snippet section.

7. Scroll down to check the additional information under the sections Statistics, Geolocation, Status, etc.

8. Under the Thumbnail section you can find the reverse image search results, click on the button under any thumbnail.

9. A new tab in Google appears, and the results for the reverse image search are displayed.



Task 3: Gather Information from FTP Search Engines

File Transfer Protocol (FTP) search engines are used to search for files located on the FTP servers; these files may hold valuable information about the target organization. Many industries, institutions, companies, and universities use FTP servers to keep large file archives.

Here, we will use the NAPALM FTP indexer FTP search engine to extract critical FTP information about the target organization.


Steps:

1. Launch Mozilla Firefox and type https://www.searchftps.net/ in the search bar and press enter.

2. NAPALM FTP indexer website appears.

3. In the search bar, type microsoft and click Search.

4. You will get the search results containing critical files and documents related to the target organization. 

5. You can also use FTP search engines such as FreewareWeb FTP File Search to gather crucial information about the target organization.



Task 4: Gather Information from IoT Search Engines

IoT search engines crawl the Internet for IoT devices that are publicly accessible. These search engines provide crucial information, including control of SCADA systems, traffic control systems, CCTV cameras, etc.

We will search for information about any vulnerable IoT device in the target organization using the Shodan IoT search engine. 

Steps:

1. Launch Mozilla Firefox and type https://www.shodan.io/ in the search bar and press Enter. 

2. Shodan page appears, in the search bar, type amazon and press Enter.

3. You will obtain the search results with the details of all the vulnerable IoT devices related to amazon in various countries.










