WallpaparsApp
=============

Building a free wallpapers app using Picasa Web Albums API


Google’s Picasa Web Albums API
The major and difficult task in this app is building the server side components like an admin panel to manage your wallpaper data by providing file upload option and other things. For this you should also able to code in other technologies like HTML, CSS, JSP, PHP or MySQL which is again a difficult task for android beginners.

So I selected Picasa Web Albums as a robust solution for this. Picasa web albums is free of cost and importantly it exposes an API (json and xml) for developers. You can go through Picasa Web Albums Data API to know more about the API’s exposed.

We are specifically interested in following API calls for this app which doesn’t require any authentication as we perform read operations only on public albums.

1. Request a list of albums
(username should be replaced with your Google username)
https://picasaweb.google.com/data/feed/api/user/username?kind=album&alt=json

2. List photos recently uploaded
(username should be replaced with your Google username)
https://picasaweb.google.com/data/feed/api/user/username?kind=photo&alt=json

3. List photos in album
(albumid should be replaced with actual album id which can find in albums response)
https://picasaweb.google.com/data/feed/api/user/username/albumid/albumid?alt=json

If you want to provide more options like providing user to comment, edit or delete options you need to implement authentication as mentioned in the document.

Hint: alt parameter decides the type of response we are expecting either json or xml. Pass alt=json in the url to get the response in JSON format.

Adding wallpapers in Picasa Web Albums
Before starting the app, we’ll add few wallpapers in Picasa albums for testing. You can login into Picasa using your Google account. Follow below steps to create albums and wallpapers in Picasa web albums.

1. Login into Picasa.
(If you are redirected to your Google+ account, click on Click here to go back to Picasa Web Albums to navigate back to Picasa Web or go with Google+ if you are comfortable)

2. Click on upload and enter your album name. These albums act as wallpaper categories in our app which will be listed in navigation drawer menu. Example: Animals, Cars, Food, Movies, Vintage etc.,

3. Once you created the album, upload few wallpapers to the album. Make sure that you are uploading the wallpapers with good high resolution.

4. Now make the album visibility as Public by clicking on Edit link displayed on the right. Note: If you don’t make your album as public, it will not be accessible via your android app. In other words you can’t see the album in the json response.

5. Follow 2nd, 3rd and 4th steps to create few more albums and wallpapers.

Designing The App
The design of this app is very minimalistic with very few color combinations. Overall it contains following components.

1. Navigation drawer (Slider Menu) to display wallpaper categories.
2. Grid view screen to display the thumbnail of wallpapers under a category.
3. Full screen view of wallpaper with Set As Wallpaper and Download Wallpaper options.
4. Settings screen to configure Picasa username, number of columns in grid and gallery image directory.

Downloading Volley Library (volley.jar)
To make calls to Picasa API we are going to use Volley Library instead of using the java library mentioned in the documentation. I already published an article about Volley Library explaining about the advantages of choosing volley. In this project it plays a major role in caching the images.

Download the precompiled volley.jar


If you are succeeded all the steps until now, you just create a fully fledged wallpapers app which has good potential go into market right away. But before that I would like to address few important points to you.
This app is doesn’t supports older versions < 4.0. For that you need to use Android Support Library to provide backward compatibility.

> Even though we are using Google+ / Picasa web services to provide wallpapers, in real scenario we should have a server side technology to detect the mobile device and respond the wallpapers depending on mobile configuration like screen dimensions.





