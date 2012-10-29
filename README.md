pithy is:  

	1. concise and forcefully expressive, or
	2. containing much pith

code should be 1, not 2.  

sometimes you want to share code and see what it does on the same page.  sometimes you want to do this for python with scientific computing.  enter pithy.  

pithy has code on the left, and output on the right.  all changes are saved, and the url is freely shareable.  pithy has been tested against sophomores and juniors in chemical engineering successfully.  

pithy is python for sharing plot and numerical output.  pithy runs arbitrary python on your machine and send the output back to the browser in a fairly clear manner.  this is convenient, this is also potentially SUPER DANGEROUS.  thus far there is an attempt at code scrubbing to stop people from writing local files, reading local files and rm -rfing your stuff, but it is most definitely not sandboxed nor bullet proof.  Thus, pithy should be run on a server 

1. that is routinely backed up (like all good servers should be)
2. has nothing that you don't want the world to see that is not encrypted (ditto)
3. that can suffer some downtime if someone does something stupid

because pithy just runs from a directory, standard http authentication can be applied to make stuff safe.

###pithy requires 

1. a fairly up to date (not 3.0 though) python installation
2. [node.js](http://nodejs.org/)   
3. science stuff! I like to to use [EPD](http://www.enthought.com/products/epd_free.php), but scipy, numpy and matplotlib should be sufficient 

###installation/usage

1. clone repository to where you want stuff
2. cd to that directory
3. run "node index.js <port number>" where port number is something like 8000 or 80 or whatever
4. navigate to http://localhost:<port number>  (or wherever you put stuff).  you should see a page, and the URL should have a random string of characters appened.  try some python.
5.  now add whatever name you want to the URL (numbers,letters and (-,_) only.  Run some code here.  Share the url if you're running on an accessisible server.  repeat.  now you're pithy.


###example

pithy tries to plot things nicely, and in order.  best to learn by example here:

paste this into your pithy page to generate a graph


    a = linspace(0,1,100)
    b = sqrt(a)
    c = a**2

    plot(a,b,'k')
    plot(a,c,'k')
    showme()
    clf()

    plot(a,b,'k')
    plot(a,c,'k')
    xlabel("x")
    ylabel("y")
    title("Now With Labels")
    showme() 

everything here is pure [pylab]() except for showme(), which does some behind the scenes magic to generate a plot and save the figure.  