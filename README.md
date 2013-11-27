PyBossa demo application Flickr Person in Facebook
======================================

This application has some files:

*Normal files*
*  createTasks.py: for creating the application in PyBossa, and fill it with some tasks.
*  template.html: the view for every task and deal with the data of the answers.
*  tutorial.html: a simple tutorial for the volunteers.
*  long_description.html: long description of your app

*New files*
*  static/fb-templates: templates used in facebook interface
*  static/fb-templates/css: fonts used
*  static/fb-templates/js: javascript files used
*  static/fb-templates/img: images used in templates
*  static/fb-templates/index.html: template exhibit in facebook
*  static/fb-templates/long_description.html: long description template of your app
*  static/fb-templates/template.html: template of your app
*  static/fb-templates/tutorial.html: tutorial of your app
*  static/fb_config.json.template: template of setup file to facebook interaction

- **NOTE**: the long description, tutorial and template html's can be a copy of the normal files

![alt screenshot](http://apps.facebook.com/flickrperson/img/flickrperson_screenshot.png)

New Pybossa and Pybossa.js
==========================
You need install the new version of [pybossa.js](https://github.com/adabriand/pybossa.js) and the new [pybossa api](https://github.com/adabriand/pybossa) to run your app on facebook. 
Upgrade it on your pybossa server.

- **NOTE**: **IT IS NOT POSSIBLE TO CREATE LINKS TO PAGES HOSTED IN	PYBOSSA SITE**

Testing the application
=======================

You need to install the pybossa-client first (use a virtualenv):

```bash
    $ pip install pybossa-client
```
Then, you can follow the next steps:

===== On Pybossa Server ================================================

1.  Create an account in PyBossa
2.  Copy under your account profile your API-KEY
3.  Run python createTasks.py -s http://localhost/pybossa -k API-KEY -c

===== On Facebook App Dashboard ========================================

1. Create a facebook app that will represent your app (https://developers.facebook.com/apps)
    - **NOTE**: you need be registered as a developer on facebook to create your application on it
2. Register your app domain, for example: pybossa.socientize.eu
3. Register the URL in app configurations pointing to location of your app in Pybossa Server, for example:
   * http://pybossa.socientize.eu/flickrperson/
4. Register the secure URL, for example: https://pybossa.socientize.eu/flickrperson
    - **NOTE**: to works with secure URL you need to install a SSL certificate, for that, see this tutorial: ________


===== Back to Pybossa Server on fb_config.json.template ===============

1.  Change the name of the file fb_config.json.template to fb_config.json
    
    ```bash
        $ mv fb_config.json.template fb_config.json
    ``` 

2.  Copy your facebook app id, that you see in Facebook App Dashboard 
3.  Set your endpoint, used by Pybossa in this server
4.  Set your app Shortname
5.  Set your facebook permissions type, according to your needs and how you configured on facebook
    - **NOTE**: types of permissions can be checked here: https://developers.facebook.com/docs/reference/login/ 
6.  Create an Alias in file the /etc/apache2/sites-available/your_pybossa_site of Apache Server to the folder 
fb-templates of your application, for example: 
     * Alias /flickrperson /home/user/app-flickrperson/static/fb-templates

===== Back to Facebook ================================================
*  Test the link for your application, for example: https://apps.facebook.com/flickrperson


Repositories
============
*New Pybossa.js*
* https://github.com/adabriand/pybossa.js

*New Pybossa (pybossa.api)*
* https://github.com/adabriand/pybossa

*App-flickrperson to Facebook* 
* https://github.com/guilhermemg/app-flickrperson


App running on facebook
=======================
* http://apps.facebook.com/flickrperson/


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
