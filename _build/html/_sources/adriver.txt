.. probtn documentation master file, created by
   sphinx-quickstart on Mon Nov  2 12:32:08 2015.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.
 
.. _adriver:
 
Integrtion with AdRiver
==================================

Integrtion with AdRiver (modificated code)
----------------------------------
You need to make this steps:

Step0
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Create a campaign (or an app with the necessary domain, real or a domain identifier)
 
.. image:: images/adriver/adriver1_step0.png

Step1
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Create a page available at the address on the same domain where the button is to be displayed.

On the page, add showinparent_concat.js 

``<script src="//cdn.probtn.com/showinparent_concat.js"></script>``

For example:
 
.. code-block:: html

	<!DOCTYPE html>
	<html>
	<head lang="en">
			<meta charset="utf-8">
			<meta name="viewport" content="width=device-width, initial-scale=1">
			<title>probtn (hackpad)</title>
	</head>
	<body>
			<script src="//cdn.probtn.com/showinparent_concat.js"></script>
	</body>
	</html>
 
Step2
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Create an AjaxJS (Generic AjaxJS) banner

.. image:: images/adriver/adriver2_step1.png

Step3
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Upload a code for the banner (click on “Upload banner”)

.. image:: images/adriver/adriver2_step3.png

Code example for "generic ajax" banner

https://www.dropbox.com/s/vo4deq8g9e9yynp/generic_ajaxjs.zip?dl=0

.. image:: images/adriver/adriver2_step3_1.png

Step 4
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Change the path from index.html to showinparent.html (example in the archive) (created in Step1)

``<iframe style="border: 0px; width: 0px; height: 0px; display: none;" src="http://example.com/showinparent.html?domain=nessasary_example_app_domain.test"></iframe>``

Url ``//example.com/showinparent.html?domain=nessasary_example_app_domain.test`` is an example, use your own path (до страницы созданной на шаге 1)

Also value of GET param domain (for example) ``nessasary_example_app_domain.test`` should be replaced on nessesary  (id), used in nessesary app in admin.probtn.com
 
Set campaign (optional)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

