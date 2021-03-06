## tumblr-dump

tumblr-dump is a program that crawls the content of one or more Tumblr blogs from their first to last page.
Tumblr URLs have to be provided via command line as well as the directory where all the retrieved content is stored.

Run ./tumblr-dump to see what options are available


## Installation

tumblr-dump needs wget, and relies on the following libraries:
* requests
* BeautifulSoup
* lxml


## TODO
* css has to be retrieved as well
* add warc support by default
* media content is stored in directories that are not within their respective tumblr directory. Example:
 
```
|-- 31.media.tumblr.com
|   `-- avatar_34f25f54fa03_128.png
|-- 36.media.tumblr.com
|   `-- 09c3d7c34f28f9ab3f9dcf38c39e4dbc
|       `-- tumblr_o02y3p06TR1u3pry4o1_1280.jpg
|-- 40.media.tumblr.com
|   |-- a8f10ed449a2bcc22fbe90df1f9d1af6
|   |   `-- tumblr_o042o84TmQ1u3pry4o1_1280.jpg
|   `-- befdd1cbde93b13e0619fc45b94f5be6
|       `-- tumblr_o02y4ifyhM1u3pry4o1_1280.jpg
|-- example1.tumblr.com
|   `-- page
|       |-- 1
|       `-- 2
`-- example2.tumblr.com
    `-- page
        |-- 1
        `-- 2
```

The media content retrieved by crawling example1.tumblr.com (shown in the directory tree) might share the same directories as, say, the media content retrieved while crawling example2.tumblr.com.
Their pages will still reference different media content, but the directories storing their data might overlap. A non overlapping scenario might be preferred.
