1. Install Docker 
2. Pull the nginx image 
`docker pull nginx`
3. Run a container based on this image, while mounting a directory with a file in it 
`docker run -it --rm -d -p 9080:80 --name web -v %userprofile%/source/dockerFiles/HelloWorldWebPage:/usr/share/nginx/html nginx`
	- Basically this is: 
		- Run a docker image 
		- Attached to a terminal 
		- Remove the image when the container shuts down 
		- make it run in the background (as a daemon) 
		- Map host port 9080 to container port 80 
		- Give the container a name 
		- Mount a host volume (C:\users\3056\source\dockerFiles\HelloworldWebPageWusr/shareinginx/html) to a container dir (/usr/share/nginx/html). This is because nginx will check that dir by default for an index.html. So, presumably you have a valid index.html in that host directory 
		- Base this all on the nginx image 

There are alternative methods: e.g. set up a dockerfile that does this, then do a docker build and docker run to run the image as above, but instead of nginx use your image. 
