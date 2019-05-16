# Blog

![Me in front of a lake](/wp-content/uploads/2017/10/IMG_20161210_134256-e1507672696125-888x550.jpg)

Discover it: https://morikko.github.io/travel-blog/

This blog is about my trip to South America. I describe the places I discovered, the culture I met and the activities I did.

All the articles are attached to many beautiful pictures from South America.

Enjoy :)

# About the technology

## Wordpress
The blog is based on Wordpress. During my road trip, the blog was online on a server. Thus, I was able to write my articles while traveling. When I came back home, I decided to switch it off as it cost me money. However, I downloaded a back up I put offline on my computer.

## Headless
As now, I am no more contributing to this blog, the wordpress features are useless. Thus, I decided to switch it to a static website I could again present. I used this amazing extension called [Simply Static](https://wordpress.org/plugins/simply-static/).

## Step to create this static blog

### Generate the static website
1. Install the extension
2. Set the plugin settings (you might use a subdomain, here: `/travel-blog`)
3. Generate the static website
4. If the zip download link didn't work, fetch the result directly from the plugin 'wp-content' folder

### Current problems
The plugin is mainly working well but a few glitches remain. The next changes have always to be done everywhere in the code.

#### Category
When a category has more than 1 page, the first page is a redirection one pointing to the same page (infinite redirection). I had to copy the HTML source directly from the local server.

In the copied HTML:
1. Replace "/20%" with "/"
2. Replace "http://localhost/travel/" with "/travel-blog"

#### Files architecture for posts
For an unknown reason, a %20 is added in each post URL. Nevertheless, %20 is a space in HTML format, so it is impossible to fetch the URL.

The solution is to change the %20 name with content.
1. Rename the "%20" folders with "content" with `find . -type d -name "%20" -exec sh -c 'f="{}"; mv -- "$f" "${f%/%20}/content"' \;`
2. Replace "/%20/" with "/content/"
3. Replace '/%20"' with '/"' 
4. Replace "/%20'" with "/'" 

#### Others
Probably a mistake when I put the back up offline locally.
- Replace the historical domain "http://travel.emasseran.org" with "/" (Example: the Home link)

For a library to be well fetched:
-  Replace "\/wp-includes\/js\/wp-emoji-release.min.js" with "\/<subdomain>\/wp-includes\/js\/wp-emoji-release.min.js"

## About the map
The API key is outdated and thus Google Maps is complaining but you can use the map.
In order to fix the article links and image previews:
-  Replace "https:\/\/travel.emasseran.org" with "\/travel-blog"

![In front of the Perito Moreno](/wp-content/uploads/2017/01/IMG_20161208_142910-1024x758.jpg)

I hope you will enjoy my blog as much as I loved my trip! :)
