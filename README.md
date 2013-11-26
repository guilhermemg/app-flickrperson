PyBossa demo application Flickr Person in Facebook
======================================

This application has some files:

*  createTasks.py: for creating the application in PyBossa, and fill it with some tasks.
*  template.html: the view for every task and deal with the data of the answers.
*  tutorial.html: a simple tutorial for the volunteers.
*  static/fb-templates: templates used in facebook interface
*  static/fb-templates/css: fonts used
*  static/fb-templates/js: javascript files used
*  static/fb-templates/img: images used in templates
*  static/fb-templates/index.html: template exhibit in facebook
*  static/fb_config.json.template: template of setup file to facebook interaction

NOTE: IT IS NOT POSSIBLE TO CREATE LINKS TO PAGES HOSTED IN	PYBOSSA SITE

![alt screenshot](http://i.imgur.com/63SmFEu.png)

Testing the application
=======================

You need to install the pybossa-client first (use a virtualenv):

```bash
    $ pip install pybossa-client
```
Then, you can follow the next steps:

===== On Pybossa Server ================================================

*  Create an account in PyBossa
*  Copy under your account profile your API-KEY
*  Run python createTasks.py -s http://localhost/pybossa -k API-KEY -c

===== On Facebook App Dashboard ========================================

*  Create a facebook app that will represent your app (https://developers.facebook.com/apps)
     NOTE: you need be registered as a developer on facebook to create your application on it
*  Register your app domain, for example: pybossa.socientize.eu
*  Register the URL in app configurations pointing to location of your app in Pybossa Server, for example:
 http://pybossa.socientize.eu/flickrperson/
*  Register the secure URL, for example: https://pybossa.socientize.eu/flickrperson
     NOTE: to works with secure URL you need to install a SSL certificate, for that, see this tutorial: ________


===== Back to Pybossa Server on fb_config.json.template =======

*  Change the name of the file fb_config.json.template to fb_config.json
      $ mv fb_config.json.template fb_config.json
      
*  Copy your facebook app id, that you see in Facebook App Dashboard, 
*  Set your endpoint, used by Pybossa in this server
*  Set your app Shortname
*  Set your facebook permissions type, according to your needs and how you configured on facebook
     NOTE: types of permissions can be checked here: https://developers.facebook.com/docs/reference/login/ 
*  Create an Alias in file the /etc/apache2/sites-available/<your pybossa site> of Pybossa to the folder 
fb-templates that hosts your Pybossa, for example: 
      Alias /flickrperson /home/user/app-flickrperson/static/fb-templates

===== Back to Facebook =====
*  Test the link for your application, for example: https://apps.facebook.com/flickrperson

Documentation
=============

We recommend that you read the section: [Build with PyBossa](http://docs.pybossa.com/en/latest/build_with_pybossa.html) and follow the [step by step tutorial](http://docs.pybossa.com/en/latest/user/tutorial.html).

**NOTE**: This application uses the [pybossa-client](https://pypi.python.org/pypi/pybossa-client) in order to simplify the development of the application and its usage. Check the [documentation](http://pythonhosted.org/pybossa-client/).


LICENSE
=======

Please, see the COPYING file.


Acknowledgments
===============
The thumbnail has been created using a [photo](http://www.flickr.com/photos/mcgraths/3289448299/) from Sean McGrath (license CC BY 2.0). 


**Note**: You can see the results of the CrowdCrafting app [here](http://dev.pybossa.com/app-flickrperson/results.html)
=======
