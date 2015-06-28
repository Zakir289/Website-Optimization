### Website optimization Technique

Basically I am Back end developer, But for the last few months I was working more with front end. These are few of my experiences that i come across

**Performace of a site mostly depends on**

- while hitting the DB(Nearly 80% of the time)
- loading the images on the browser,
- loading external libraries
- Not using the proxy servers when required.....

Back end code execution will have a minor effect on the performance of a page. Ruby  is so popular even though the execution time for Ruby is more when compared with Java.



**The main aim of every site/tool is to fascinate the User/Customer to come to their site repeatedly:**

#### 1. Prioritize the visible content 
- User/Customer prefer to visit sites which loads faster, i.e responsive


- Every day we come across many websites, Websites that load faster are as large as sites that loads slower But they had just prioritize the fold content so that site appears Responsive.


- If we hit any url of top ecommerce sites the content above the fold will load so fast and then render the content below the fold.


- By using inline js and css upto that particular content that is visible to the user will make the site load faster. 


- We prefer to load the CSS for a page at the starting of the page so that we can avoid redrawing of the elements, But for the home page Loading CSS next to the fold content will reduce the delay time of showing the home page to the user. I came across few tools which loads CSS for **ATF(After the fold)**

#### 2. Image Optimization
	
- Loading the Images will takes more than 80% of the website rendering time.


- It will be nice, if we can eleminate unnecessery images from the site.


- Now It's time to compress the image(preferably lossless). There are many tools which will compress the image.


- Serve the images from **CDN**. Content delivery networks will serve the data based on the user location. If the user is in Australia the data will be served from the server close to that location. The data loads faster if the data is served from different servers, So loading images from CDN will allow the browser to load the data parallely.



#### 3. Compression

- When user hits an url, Next to DNS lookup the website waits for the server to provide the requested files.


- As the size of the file is more, the time taken to load the file is also more


- Tools like Gzip will compress the data before sending to the browser, This will save the time, bandwidth,...



#### 4. Page Size and HTML Complexity

- Page size plays a crucial role in web page performace and it should be as low as possible.


- Unnecessery nesting of HTML elements should be avoided to reduce the HTML complexity


- Custom elements should be avoided if it can be achieved by HTML standard tags.


- Large no of Dom elements leads to slow processing of elements


#### 5.Caching static resources

- Loading the resources/data from the server for and every visit is expensive and increases the traffic and wastage of user bandwidth


- If there is delay in the response from the server, It blocks the page rendering


- If we can cache the static resources on the browser it can used in subsequent visits



#### 6. Lazy loading

- There wil be large no of images in a web page but all of them won't be on the view port. No need to load the images which are not on the view port rather we can load them when the user scroll's the page.

- you can find few jquery plugins which provide this feature

- Plugins on specific events take value of data-original and put in src , i.e when image will load.(ex: <img class="lazy" data-original="img/example.jpg/>")



To test the page speed and few other userful links

Pagespeed Insights by Google.

- https://developers.google.com/speed/pagespeed/
- YSlow by Yahoo. 
- https://developer.yahoo.com/yslow/
- Other Useful sites
- http://www.webpagetest.org/
- http://www.woorank.com/
- http://gtmetrix.com/








##### 1. Client side rendering v/s Server side Rendering in terms of performace?

The Main focus of the question is where to generate the HTML views, Whether to generate at client side or server side?

###### Client side rendering
 
- Client-side rendering has the disadvantage that the initial page load takes a long time but once all the resources are loaded the user can navigate the site seamlessly without page. You might want to minimize the number of Ajax calls and/or use a client-side cache (e.g. cache data in the Angular.js controller).


-  Sites where you mostly navigate and view static content can get away with mostly server-side rendering, but I can't think of any website that doesn't do any client-side rendering.  Any portion of a page that's **animated or highly interactive (a draggable slider, a sortable table, a dropdown menu) almost certainly uses client-side rendering.**


- Lower bandwidth usage, It will helpful for the people who have limited browsing plans mostly on mobiles.


- Slower initial page render. May not even be noticeable in modern desktop browsers. If you need to support IE6-7, or many mobile browsers (mobile webkit is not bad) you may encounter bottlenecks.


- Building API-first means the client can just as easily be an proprietary app, thin client, another web service, etc.


- At most times its faster to develop the app, If we go with client side rendering. For few web frameworks(exludeing Ruby on Rails,...) writing server side code forces you to restart the server to see the change. By doing it client side you can get rid of this extra burden.

- Some times it becomes harder to debug client side code.


- You may come across cross browser compatiblity issues due to client side rendering which won't happen frequently, if we can use Jquery,... or any other framework which take care of cross browser compatability.


- Taking advantage of caching-proxies and CDNs for HTML-templates and JS code;

###### Server side rendering

- Server-side rendering provides a fast initial page load and is good for SEO but every time the user navigates, the whole page goes blank for a second while it loads the new URL.

- Page caching is possible as a quick-and-dirty performance boost

- Depending upon the requirement, Some times its faster to develop.

- For "standard" apps, many UI features are pre-built


- Sometimes considered more stable because components are usually subject to compile-time validation

- When UI requirements fit the framework well.


- Its easy to debug the code, By using IDE's like Intellij idea you can debug the JSP's too.


- Your content is visible to search engines like Google.





###### when to use what(server side rendering v/s client side rendering)?
I am not a front end geek rather i am a pure back end developer, But here goes my observation which one to use:
So it all depends on whether you want a fast initial page load but don't expect the users to stay that long (then use server-side rendering) **or** it's not that important that the page loads fast (as in Gmail) but users will navigate around for a long time (then use client-side rendering).	


##### If we go through few major sites and check which one they took among client and server,
For websites that blend static, navigable content and app-like interactivity (or for companies that seek to provide an added measure of sanity for their engineers and designers), this divide becomes a huge pain.  This is why **Google Plus** does all rendering on the client.  **Quora** cleverly does almost all rendering on the server (including when you, say, click a "Follow" button), but only the updated parts are sent to the client.  (Particular widgets like the editor and "Promote" slider that provide instant feedback are clearly client-side.)  In an effort to increase responsiveness and flexibility, many sites now render **Ruby templates on the server and Backbone templates on the client** for different parts of the same user interface. 




