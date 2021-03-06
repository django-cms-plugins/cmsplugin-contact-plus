# About cmsplugin_contact_plus

[cmsplugin_contact_plus](https://github.com/arteria/cmsplugin-contact-plus/) lets your build forms for your django CMS project 
with exactly the fields you want in the order you want with a minimal effort. 

Beside the regular input fields, there are "auto" fields, for example to submit the referral page or additional, hidden values. 
The form will be submitted to a per form defined email address. This allows to cover a lot of 
use cases with a single and simple cmsplugin. 

cmsplugin_contact_plus is licensed under The MIT License.

## Quickstart

1. To install from PyPi, in your virtualenv run

	```
	pip install cmsplugin_contact_plus
	```
	
	or to get the latest commit from GitHub
	 
	```
	pip install -e git+git://github.com/arteria/cmsplugin-contact-plus.git#egg=cmsplugin_contact_plus
	```
	

2. Put ``cmsplugin_contact_plus`` in your INSTALLED_APPS settings.py section and verify that [ADMINS](https://docs.djangoproject.com/en/dev/ref/settings/#admins) is defined as well.

3. Don't forget to syncdb your database.

## Templates

Do not forget to add ``'django.template.loaders.app_directories.Loader'`` to ``TEMPLATE_LOADERS`` in your settings.py.   


## TODO and planned features
- Save send data to a NoSQL database (eg. MongoDB).
- Trigger a signal when a message was send successfully
- and track the current status in each message record for further interaction (new, in progress, closed). 
- Add/Update dependencies to setup.py.
- Widget support for each field.  
- Provide examples and real life case studies
- Multiple template support /custom templates
- Formatted email messages, HTML?

## Changelog
### development 
Please have a look at the latest commits for the work-in-progress-development version.

### 1.1.4
- Packaging was modified for PyPI.
- Upload script for PyPI. Just execute ``./upload-to-pypi.sh``.

### 1.1.3
- Better readability in email.

### 1.1.2
- Patch version for PyPI with corrected Manifest.in, see issue #4.

### 1.1.1
- Added include for templates im Manifest.in, fixes issue #4.

### 1.1.0
- Generic Query parameter (GET key) to hidden field. Use this in attach additional hidden data to the form. The slugified label is used for key lookup in the GET parameters. Eg.:  
label is 'Favorite Color', than the lookup in the URL is done based on 'favorite-color', in www.example.com?favorite-color=blue will pass {..., u'favorite-color':'blue', ...}  to the email.


### 1.0.4
- Fixed default "from email address" in case ``ADMINS`` is not defined in ``settings.py``. (Issue #2)
- Fixed typos and added translation markers.

### 1.0.3
- Improoved Documentation
- Added ``auto_TextArea`` shortcut to create a TextArea. Note: Currently the widget definde in the plugins are ignored. 
- Hidden "referral page" field. Reads referral from request.
- Generic Hidden fields. Use this in combination with JavaScript/jQuery to attach additional data to the form sent by email.

For exmple, the field lable for the 'CharField as HiddenInput' is named to "Object description". 
Using the lable name, the ID for the input field will be 'id_object-description', the name 'object-description'.

Store data is dead easy using jQuery.

	
	$('#id_object-description').val('Hello Hidden World'); // The string 'Hello Hidden World' will be send by email as well.
	


### 1.0.2
Fixed indentation /EOF in setup.py


### 1.0.1
Fixed IndentationError in setup.py

### 1.0.0
[arteria](https://github.com/arteria/) open sourced cmsplugin_contact_plus unter the MIT License. This plugin was build on a fork of [cmsplugin_contact](https://github.com/rtpm/cmsplugin_contact). Kudos! 
