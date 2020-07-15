As a starter to learn about webpage performance, first we would like to know what are happening through the process. In this article,
 we are going to grab a glimpse into the stages when loading a webpage.

### What do users experience on entering the webpage?
In this section, we describe the scenarios from a perspective of a user who is actually viewing the webpage, in order to know what happen
 to them and what metrics we apply to these periods.

So the user has clicked a link to open the webpage served by our service, the window opened and it's a blank page. In a fraction of time,
 the user saw some text displaying on the page, which makes them feel that "Right, my network is working" (belive it or not, a great many
 people use simple webpages to test whether or not they are connected to network) or "OK, the webpage is loading". 

This period is so called `FCP`, `First Contentful Paint`, which refers to the period between clicking a link, which set up an idea in the
 user's mind - "Let's open the page!", and the first element of the page, be it a text or anything visible, being displayed, giving the
 user a feeling that the page is not stuck.  

As you can see, FCP is a significant point for the user to grab a sense of whether the page is alive. Should it take a long time that all
 you see is a blank page, you might even want to swing your monitor during the waiting period.

So the page is loading, but I still have no idea what I can do in this webpage, because there are barely nothing but a loading status
 animation, oh wait, here we go, I can see the content and figure out what to do with the page.

This is an excited moment for the user to finally think "wow this is a gorgeous page!" or "what the hell is this?" It also contributes
 largely to user experience, as it presents an overview of the page to the user. 

Metrics used for the period are captured in different ways, given to the tricky definition of meaningful content in different websites.
 Here we are going to use `LCP`, `Large Contentful Paint`. Other metrics such as `FMP`, [First Meaningful Paint](https://web.dev/first-meaningful-paint/)
 or `SI`, [Speed Index](https://sites.google.com/a/webpagetest.org/docs/using-webpagetest/metrics/speed-index) and so on are also
 used in some company. Considering the complexity and acurracy, it's recommended to use LCP.


### Webpage 
> To sound professional is not easy, unless you use a lot of terminologies in your speech. 

