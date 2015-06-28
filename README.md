### Website optimization Technique


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




