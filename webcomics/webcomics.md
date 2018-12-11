# Webcomics tracking!
## Plugging together web services because you're too lazy to use bookmarks
Dan Conley

October 2017



## I like webcomics
* (which are comic strips posted on the internet)
* But if you don't keep up with them it can be hard to remember where you left off
* If only there was a way to keep track...


## Dan, this is a solved problem. RSS.
* Some comics don't use rss because it subverts ad revenue
* Some aggregators only store a certain number of entries
* It's great for tracking *new* entries, but not reading through a backlog from the start
* RSS stresses me out because oh no I'm so far behind and it's a responsibility to read them and and and


## Let's be honest
I'm also a giant nerd who enjoys hacking things together for their own use

(Plus I get a DevTricks presentation out of it!)



## Ideas I had in the past
* iframe wrapper? (Can't control cross-domain from parent window)
* Some sort of service to store comics and last read in a database? (Didn't have time)
* ewastl has something that might work, maybe?



## Define requirements
* I don't need to store new updates
* All I *really* need is something to store the *last viewed page* of a site


## graphviz!
![a flow diagram: trigger->service->data store](flow1.png)


## Just use a bookmark jfc
![a flow diagram: user click->bookmark service->bookmark data store](flow2.png)

But I'm lazy and robots exist. Let's automate that.



## "Send update on page load"
* That sounds like JavaScript...
* If only I could inject my own JS onto a page
* Tampermonkey!


![a flow diagram: Tampermonkey->service?->data store?](flow3.png)



## Store latest entry
* Could do some sort of database integration
* But [Minimum Viable Prospit](https://media.giphy.com/media/KUpKdZyxyPl16/giphy.gif)...
* This is a row in a spreadsheet
* To Google Sheets!


## oauth is hard, let's go shopping
* Sure I *could* write an interface between Tampermonkey and Google Sheets, but that takes effort
* IFTTT has a "webhook" trigger and Sheets integration
* One POST and I'm done


## The final solution
![a flow diagram: Tampermonkey->IFTTT->Google Sheets](flow4.png)



![live demo!](livedemo.gif)
