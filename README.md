PyBossa demo application Flickr Person in Facebook
======================================

This application has some files:

*Normal files*
*  createTasks.py: creates the application in the PyBossa, and fills it with some tasks.
*  template.html: the view for every task. It deals with the data of the answers.
*  tutorial.html: a simple tutorial for the volunteers.
*  long_description.html: a long description of your app.

*New files*
*  static/fb-templates: templates used in the Facebook interface.
*  static/fb-templates/css: fonts used.
*  static/fb-templates/js: javascript files used.
*  static/fb-templates/img: images used in the templates.
*  static/fb-templates/index.html: base template for the Facebook application. It loads the developer defined html files: long_description, template and tutorial.
*  static/fb-templates/long_description.html: long description template of your Facebook app.
*  static/fb-templates/template.html: task viewer template of your Facebook app.
*  static/fb-templates/tutorial.html: tutorial of your Facebook app.
*  static/fb_config.json.template: setup file for the Facebook app.

- **NOTE**: the long description, tutorial and template's html can be a copy of the normal files.

![alt screenshot](http://img89.imageshack.us/img89/9881/gcjt.png)

New Pybossa and Pybossa.js
==========================
You need to install the new version of [pybossa.js](https://github.com/adabriand/pybossa.js) and the new [pybossa api](https://github.com/adabriand/pybossa) to run your app on Facebook. 
Upgrade it on your PyBossa server.

- **NOTE**: **WE DO NOT RECOMMEND TO OPEN LINKS, INSIDE YOUR FACEBOOK APP IFRAME, TO PAGES HOSTED IN PYBOSSA SITE.**

Testing the application
=======================

You need to install the pybossa-client first (use a virtualenv):

```bash
    $ pip install pybossa-client
```
Then, you can follow the next steps:

===== On Pybossa Server ================================================

1.  Create an account in the PyBossa
2.  Copy under your account profile your API-KEY
3.  Run python createTasks.py -s http://localhost/pybossa -k API-KEY -c

===== On Facebook App Dashboard ========================================

1. Create a Facebook app that will represent your app (https://developers.facebook.com/apps)
    - **NOTE**: you need be registered as a developer on Facebook to create your application on it
2. Register your app domain, for example: pybossa.socientize.eu
3. Register the URL in the app configurations pointing to the location of your app in PyBossa Server, for example:
   * http://pybossa.socientize.eu/flickrperson/
4. Register the secure URL, for example: https://pybossa.socientize.eu/flickrperson
    - **NOTE**: Both servers that host your Facebook application and the PyBossa must have an SSL module enabled. You can follow [this tutorial](https://www.digitalocean.com/community/articles/how-to-create-a-ssl-certificate-on-apache-for-ubuntu-12-04) of how to create and configure SSL certificates on Apache Server on Ubuntu.


===== Back to Pybossa Server on fb_config.json.template ===============

1.  Change the name of the file fb_config.json.template to fb_config.json
    
    ```bash
        $ mv fb_config.json.template fb_config.json
    ``` 

2.  Copy your Facebook app id, that you see in Facebook App Dashboard 
3.  Set your endpoint, used by PyBossa in this server
4.  Set your PyBossa App Shortname
5.  Set your Facebook permissions type, according to your needs and how you configured on Facebook
    - **NOTE**: types of permissions can be checked here: https://developers.facebook.com/docs/reference/login/ 
6.  Create an Alias in file the /etc/apache2/sites-available/your_pybossa_site of the Apache Server to the folder 
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


App running on Facebook
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
