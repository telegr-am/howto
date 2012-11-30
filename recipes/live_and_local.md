## How to view changes locally

Sometimes it's useful to see the changes to your
site locally before you push the site live. Telegram
(via [Hoisted](http://hoisted.org)) now allows you
to view your site on your local machine before pushing
your changes to Telegram.

* To view the changes locally, you must install [Java](http://www.oracle.com/technetwork/java/index.html)
version 1.6 or higher.
* Download [Hoisted](/download/hoisted.jar) and put it in a well known place (e.g. `~/bin/hoisted.jar` if
  you're on a Unix-style OS [Linux, OS X, etc.])
* Spark up a terminal window and type: `java -jar path_to_hoisted_jar -server path_to_your_site`  
  This might look like `java -jar ~/bin/hoisted.jar -server ~/proj/dpp-blog`
* Point your browser to [http://localhost:8080](http://localhost:8080) and voilá, your Telegram web site, live and local

