
.. i18n: .. _web_cherrypy:
.. i18n: 
.. i18n: ==================
.. i18n: What is Cherrypy ?
.. i18n: ==================
..

.. _web_cherrypy:

==================
What is Cherrypy ?
==================

.. i18n: CherryPy is a pythonic, object-oriented HTTP framework.
.. i18n:  
.. i18n: CherryPy allows developers to build web applications in much the same way they would build any other 
.. i18n: object-oriented Python program. This results in smaller source code developed in less time.
.. i18n: 	
.. i18n: ::
.. i18n: 
.. i18n: 	import cherrypy
.. i18n: 	class HelloWorld:
.. i18n: 	    def index(self):
.. i18n: 	        return "Hello World!"
.. i18n: 	    index.exposed = True
.. i18n: 	cherrypy.quickstart(HelloWorld())
..

CherryPy is a pythonic, object-oriented HTTP framework.
 
CherryPy allows developers to build web applications in much the same way they would build any other 
object-oriented Python program. This results in smaller source code developed in less time.
	
::

	import cherrypy
	class HelloWorld:
	    def index(self):
	        return "Hello World!"
	    index.exposed = True
	cherrypy.quickstart(HelloWorld())

.. i18n: Start the application at the command prompt(after navigating to its folder):
.. i18n: 	**python hello.py**
.. i18n: 		
.. i18n: Direct your browser to http://localhost:8080
..

Start the application at the command prompt(after navigating to its folder):
	**python hello.py**
		
Direct your browser to http://localhost:8080

.. i18n: The rendering:
.. i18n: 	**Hello World!**
.. i18n: 		
.. i18n: ctrl+c in command window to terminate the application
..

The rendering:
	**Hello World!**
		
ctrl+c in command window to terminate the application

.. i18n: Statement **import cherrypy** imports the main CherryPy module.
..

Statement **import cherrypy** imports the main CherryPy module.

.. i18n: An instance of class **HelloWorld** is the object that will be **published.**
..

An instance of class **HelloWorld** is the object that will be **published.**

.. i18n: Method **index()** is called when the root URL for the site(e.g., http://localhost:8080) is requested, 
.. i18n: This method returns the **contents** of the Web page(the **'Hello World!'** string)
..

Method **index()** is called when the root URL for the site(e.g., http://localhost:8080) is requested, 
This method returns the **contents** of the Web page(the **'Hello World!'** string)

.. i18n: Statement **index.exposed = True** tells CherryPy that method **index()** will be exposed
..

Statement **index.exposed = True** tells CherryPy that method **index()** will be exposed

.. i18n: -	Only exposed methods can be called to answer a request
.. i18n: -	Lets the user to select which methods of an object are Web accessible
.. i18n: -	Can also place the decoration **@cherrypy.expose** immediately before the method:
..

-	Only exposed methods can be called to answer a request
-	Lets the user to select which methods of an object are Web accessible
-	Can also place the decoration **@cherrypy.expose** immediately before the method:

.. i18n: ::
.. i18n: 
.. i18n: 	@cherrypy.expose
.. i18n: 	def index(self):
.. i18n: 	    return "Hello World!"
..

::

	@cherrypy.expose
	def index(self):
	    return "Hello World!"

.. i18n: Statement, **cherrypy.quickstart(HelloWorld())**
..

Statement, **cherrypy.quickstart(HelloWorld())**

.. i18n: 	**publishes** an instance of the HelloWorld class
.. i18n: 	
.. i18n: 	-	And it starts the embedded webserver
.. i18n: 	-	Runs until explicitly interrupted(ctrl+c)
.. i18n: 	
.. i18n: When the application is executed, the CherryPy server is started with the default configuration
.. i18n: 	
.. i18n: -	Listening on **localhost**  at port **8080**
.. i18n: -	Defaults overriden by using a configuration file or dictionary
.. i18n: 	
.. i18n: 	-	**cherrypy.config.update({'server.socket_port':8010})**
.. i18n: 	-	Now it will run on port 8010.
.. i18n: 	
.. i18n: Webserver receives the request for URL http://localhost:8080 
..

	**publishes** an instance of the HelloWorld class
	
	-	And it starts the embedded webserver
	-	Runs until explicitly interrupted(ctrl+c)
	
When the application is executed, the CherryPy server is started with the default configuration
	
-	Listening on **localhost**  at port **8080**
-	Defaults overriden by using a configuration file or dictionary
	
	-	**cherrypy.config.update({'server.socket_port':8010})**
	-	Now it will run on port 8010.
	
Webserver receives the request for URL http://localhost:8080 

.. i18n: -	Searches for the best method to handle the request,starting from the **HelloWorld** instance
.. i18n: -	CherryPy calls **HelloWorld().index()**
.. i18n: -	Result of the call is sent back to the browser as the content of the index page for the website
..

-	Searches for the best method to handle the request,starting from the **HelloWorld** instance
-	CherryPy calls **HelloWorld().index()**
-	Result of the call is sent back to the browser as the content of the index page for the website

.. i18n: Cherrypy Application Facts
.. i18n: ==========================
.. i18n: Your CherryPy powered web applications are in fact stand-alone Python applications embedding their 
.. i18n: own multi-threaded web server. You can deploy them anywhere you can run Python applications. 
.. i18n: Apache is not required, but it's possible to run a CherryPy application behind it (or lighttpd, or IIS). 
.. i18n: CherryPy applications run on Windows, Linux, Mac OS X and any other platform supporting Python. 
..

Cherrypy Application Facts
==========================
Your CherryPy powered web applications are in fact stand-alone Python applications embedding their 
own multi-threaded web server. You can deploy them anywhere you can run Python applications. 
Apache is not required, but it's possible to run a CherryPy application behind it (or lighttpd, or IIS). 
CherryPy applications run on Windows, Linux, Mac OS X and any other platform supporting Python. 

.. i18n: Beyond this functionality, CherryPy pretty much stays out of your way. You are free to use any kind of templating, 
.. i18n: data access etc. technology you want. CherryPy can also handle sessions, static files, cookies, file uploads and 
.. i18n: everything you would expect from a decent web framework. 
..

Beyond this functionality, CherryPy pretty much stays out of your way. You are free to use any kind of templating, 
data access etc. technology you want. CherryPy can also handle sessions, static files, cookies, file uploads and 
everything you would expect from a decent web framework. 

.. i18n: Features
.. i18n: ========
.. i18n: -	A **fast**, HTTP/1.1-compliant, WSGI thread-pooled webserver. Typically, CherryPy itself takes only 1-2ms per page!
.. i18n: -	Support for any other WSGI-enabled webserver or adapter, including Apache, IIS, lighttpd, mod_python, FastCGI, SCGI, and mod_wsgi 
.. i18n: -	Easy to run multiple HTTP servers (e.g. on multiple ports) at once
.. i18n: -	A powerful configuration system for developers and deployers alike
.. i18n: -	A flexible plugin system
.. i18n: -	Built-in tools for caching, encoding, sessions, authorization, static content, and many more
.. i18n: -	A native mod_python adapter 
.. i18n: -	A complete test suite 
.. i18n: -	Swappable and customisable... everything.
.. i18n: -	Built-in profiling, coverage, and testing support.
..

Features
========
-	A **fast**, HTTP/1.1-compliant, WSGI thread-pooled webserver. Typically, CherryPy itself takes only 1-2ms per page!
-	Support for any other WSGI-enabled webserver or adapter, including Apache, IIS, lighttpd, mod_python, FastCGI, SCGI, and mod_wsgi 
-	Easy to run multiple HTTP servers (e.g. on multiple ports) at once
-	A powerful configuration system for developers and deployers alike
-	A flexible plugin system
-	Built-in tools for caching, encoding, sessions, authorization, static content, and many more
-	A native mod_python adapter 
-	A complete test suite 
-	Swappable and customisable... everything.
-	Built-in profiling, coverage, and testing support.

.. i18n: Consider these examples (**root** is conceptual, referring to the root of the document tree),
.. i18n: 	**root = HelloWorld()**
.. i18n: 	
.. i18n: 	**root.onepage = OnePage()**
.. i18n: 	
.. i18n: 	**root.otherpage = OtherPage()**
..

Consider these examples (**root** is conceptual, referring to the root of the document tree),
	**root = HelloWorld()**
	
	**root.onepage = OnePage()**
	
	**root.otherpage = OtherPage()**

.. i18n: URL http://localhost:8080/onepage points at the 1st object,
..

URL http://localhost:8080/onepage points at the 1st object,

.. i18n: URL http://localhost:8080/otherpage points at the 2nd.
..

URL http://localhost:8080/otherpage points at the 2nd.

.. i18n: Consider,
.. i18n: 	**root.some = Page()**
.. i18n: 	
.. i18n: 	**root.some.page = Page()** 
..

Consider,
	**root.some = Page()**
	
	**root.some.page = Page()** 

.. i18n: URL http://localhost:8080/some/page  is mapped to the **root.some.page** object. 
.. i18n: If this object is exposed (or its **index** method is), it’s called for that URL
..

URL http://localhost:8080/some/page  is mapped to the **root.some.page** object. 
If this object is exposed (or its **index** method is), it’s called for that URL

.. i18n: In our HelloWorld example, adding the http://.../onepage to OnePage() mapping could be done as:
..

In our HelloWorld example, adding the http://.../onepage to OnePage() mapping could be done as:

.. i18n: ::
.. i18n: 
.. i18n: 	class OnePage():
.. i18n: 	    def index(self):
.. i18n: 	        return "one page!"
.. i18n: 	    index.exposed = True
.. i18n: 	class HelloWorld(object):
.. i18n: 	    onepage = OnePage()
.. i18n: 	    def index(self):
.. i18n: 	        return "hello world"
.. i18n: 	    index.exposed = True
.. i18n: 	cherrypy.quickstart(HelloWorld())
..

::

	class OnePage():
	    def index(self):
	        return "one page!"
	    index.exposed = True
	class HelloWorld(object):
	    onepage = OnePage()
	    def index(self):
	        return "hello world"
	    index.exposed = True
	cherrypy.quickstart(HelloWorld())

.. i18n: In the address bar of the browser, put http://localhost:8080/onepage 
..

In the address bar of the browser, put http://localhost:8080/onepage 

.. i18n: The Index Method
.. i18n: ================
.. i18n: -	Method **index()**, like the **index.html** file, is the default page for any internal node in the object tree
.. i18n: -	Can take additional keyword arguments, mapped to the form variables as sent via its GET or POST methods
.. i18n: -	It’s only called for a full match on the URL
..

The Index Method
================
-	Method **index()**, like the **index.html** file, is the default page for any internal node in the object tree
-	Can take additional keyword arguments, mapped to the form variables as sent via its GET or POST methods
-	It’s only called for a full match on the URL

.. i18n: Calling Other Methods
.. i18n: =====================
.. i18n: CherryPy can also directly call methods in the published objects if it receives a URL that is directly mapped to them—e.g.,
..

Calling Other Methods
=====================
CherryPy can also directly call methods in the published objects if it receives a URL that is directly mapped to them—e.g.,

.. i18n: ::
.. i18n: 
.. i18n: 	class HelloWorld():
.. i18n: 	    def index(self):
.. i18n: 	        return "Hello World!"
.. i18n: 	    index.exposed = True
.. i18n: 
.. i18n: 	    @cherrypy.expose
.. i18n: 	    def test(self):
.. i18n: 	        return "Test Controller"
.. i18n: 	cherrypy.quickstart(HelloWorld())
..

::

	class HelloWorld():
	    def index(self):
	        return "Hello World!"
	    index.exposed = True

	    @cherrypy.expose
	    def test(self):
	        return "Test Controller"
	cherrypy.quickstart(HelloWorld())

.. i18n: Then request http://localhost:8080/test 
..

Then request http://localhost:8080/test 

.. i18n: When CherryPy receives a request for the /**test** URL, it calls the test() function.
..

When CherryPy receives a request for the /**test** URL, it calls the test() function.

.. i18n: -	It can be a plain function, or a method of any object—any callable will do.
..

-	It can be a plain function, or a method of any object—any callable will do.

.. i18n: If CherryPy finds a full match and the last object in the match is a **callable**.
..

If CherryPy finds a full match and the last object in the match is a **callable**.

.. i18n: -	A method, function, or any other Python object that supports the **__call__** method and the callable doesn't contain a valid **index()** method.
..

-	A method, function, or any other Python object that supports the **__call__** method and the callable doesn't contain a valid **index()** method.

.. i18n: Then the object itself is called.
..

Then the object itself is called.

.. i18n: These rules are needed because classes in Python are callables (for producing instances).
..

These rules are needed because classes in Python are callables (for producing instances).

.. i18n: CherryPy supports both the GET and POST method for forms.
..

CherryPy supports both the GET and POST method for forms.
