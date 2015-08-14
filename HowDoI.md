Herein are workarounds and hacks that other developers use to get around things that are either not yet available as an API in WebKit Gtk or workaround to bugs, defects, etc...

Note that the author names here are their Google Code login names.


  * **Get the HTML content of a document**
> Author: jhuangjiahua, Ref: http://code.google.com/p/pywebkitgtk/issues/detail?id=4&can=1

```
class WebView(webkit.WebView):
    def get_html(self):
        self.execute_script('oldtitle=document.title;document.title=document.documentElement.innerHTML;')
        html = self.get_main_frame().get_title()
        self.execute_script('document.title=oldtitle;')
        return html
```


  * **Handling custom URLs**
> Author: mbull.personal, Ref: http://code.google.com/p/pywebkitgtk/issues/detail?id=2

```
# its a bit of a hack but you can do this by adding a handler for the
# navigation-requested event on the WebView....

def _navigation_requested_cb(view, frame, networkRequest):
    # get uri from request object
    uri=networkRequest.get_uri()
    print "request to go to %s" % uri
    # load the page somehow.....
    page=urllib.urlopen(networkRequest.get_uri())
    # load into associated view, passing in uri
    view.load_string(page.read(), "text/html", "iso-8859-15", uri)
    # return 1 to stop any other handlers running
    # eg. the default uri handler...
    return 1

# this would be pretty easy to pick out the desired protocols and return False for the
# rest (leaving the default behaviour)
```


**DISCLAIMER**: I haven't tested these personally so don't blame me if it doesn't work =).