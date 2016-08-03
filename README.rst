.. See file COPYING distributed with hypothesis-widget for 
   copyright and license.

=================
Hypothesis widget
=================

Hypothesis widget allows you to put a feed of Hypothesis_ annotations on a 
web page.

.. _Hypothesis: http://hypothes.is

Usage
=====

For an example, see example.html, which shows the latest Hypothesis 
annotations with the tag "cats".  (What can you count on finding on the 
Internet if not cats?)

Include the JavaScript code in the page head with:

::

    <script type="text/javascript" src="hypothesis.js">
    </script>

Include in the page body a div of class ``hypothesis-feed`` to contain the feed.  Specify the annotation tag of interest with the ``data-hypothesis-tag`` attribute:

::

    <div class="hypothesis-feed" data-hypothesis-tag="cats">Default text</div>

Activate the widgets by including at the bottom of the page body:

::

    <script type="text/javascript">
    h_activate_feeds();
    </script>

The widget replaces the content of the div with the five most recent annotations with the given tag.  Since the default text in the div is left in place if the widget fails to load or if the client is not running JavaScript, it's a good idea to put some default text that will make sense to these users and clients.

The following attributes can be specified in the div element:

- ``data-hypothesis-tag``: The Hypothesis annotation tag of interest.  Required; no default.
- ``data-hypothesis-loading``: The text to display while the annotations are loading.  Optional; defaults to "Loading..."
- ``data-hypothesis-none``: The text to display if no annotations are found.  Optional; defaults to "No annotations found."
- ``data-hypothesis-error``: The text to display if there is an error getting the annotations.  Optional; defaults to "Error loading annotations."

Note that ``data-*`` attributes are only supported in HTML5; their use in other doctypes may result in validation errors.

The resulting HTML will take this form:

::

    <div class="hypothesis-feed" ...>  <!-- the original div -->

        <div class="item">
            <div class="date">
                <!-- annotation date -->
            </div>
            <div class="text">
                <!-- annotation contents -->
            </div>
        </div>

        <div class="item">
            ...
        </div>

        ...

    </div>

See hypothesis.css for sample styling.
