#Build a Music Discovery API
By Dan Zeitman

In this Step-By-Step Guide we'll show you how to build an API wrapper for multiple web services in order to create a music discovery service backend.

We're going to build a series of api endpoints that will be hosted on Auth0's Webtask.  The design pattern is based off Express so it will be familiar to many.


> Setup:  [Signup for Auth0's Webtask service](https://webtask.io/make)

Once you've logged in create an empty task and run it to get familiar with the  platform and editor.

Create a new task called: 
> sxsw-music-discovery-service


[Copy the source code of our Music Discovery Service API](https://github.com/cloudinary-developers/sxsw-hackathon/blob/master/sxsw-music-discovery-service.js)

###Add The Secrets
###Add the NPM Modules

###Test The service:
(your-cloud-url)/music-discovery-service/(api-end-point)/(params)

#APIS:
###Browse 
####/browse/(letter)
####Returns artists id.
https://evangelism.cloudinary.auth0-extend.com/sxsw-music-discovery-service/browse/b



###Search: (name)
####/search/(name)
####Returns Artist Info:
https://evangelism.cloudinary.auth0-extend.com/sxsw-music-discovery-service/search/Cyndi%20Lauper



###Releases  
####/releases/(artistid)
####Returns  releases by that Artist.
https://evangelism.cloudinary.auth0-extend.com/sxsw-music-discovery-service/releases/11319



###tracks   
####/tracks/(released)
####Returns all the tracks for that release:
https://evangelism.cloudinary.auth0-extend.com/sxsw-music-discovery-service/tracks/5514991



###Lyrics 
####/lyrics/(ssrc)
####Returns lyrics and a NLP reduced keyword list
https://evangelism.cloudinary.auth0-extend.com/sxsw-music-discovery-service/lyrics/USCJ81000500




