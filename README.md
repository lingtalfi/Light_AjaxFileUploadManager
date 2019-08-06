Light_AjaxFileUploadManager
===========
2019-08-01




A centralized ajax file upload manager for your [Light](https://github.com/lingtalfi/Light) application.


This is a [Light framework plugin](https://github.com/lingtalfi/Light/blob/master/doc/pages/plugin.md).


This is part of the [universe framework](https://github.com/karayabin/universe-snapshot).


Install
==========
Using the [uni](https://github.com/lingtalfi/universe-naive-importer) command.
```bash
uni import Ling/Light_AjaxFileUploadManager
```

Or just download it and place it where you want otherwise.






Summary
===========
- [Light_AjaxFileUploadManager api](https://github.com/lingtalfi/Light_AjaxFileUploadManager/blob/master/doc/api/Ling/Light_AjaxFileUploadManager.md) (generated with [DocTools](https://github.com/lingtalfi/DocTools))
- [Services](#services)
    - [How does it work?](#how-does-it-work)
- Auxiliary documents
    - [Action lists](https://github.com/lingtalfi/Light_AjaxFileUploadManager/blob/master/doc/pages/action-list.md)
    - [Validation rules](https://github.com/lingtalfi/Light_AjaxFileUploadManager/blob/master/doc/pages/validation-rules.md)





Services
=========


This plugin provides the following services:

- ajax_file_upload_manager


The **ajax_file_upload_manager** service is the centralized manager for all the ajax upload files of your Light applications. 



Here is the content of the service configuration file:

```yaml
ajax_file_upload_manager:
    instance: Ling\Light_AjaxFileUploadManager\Service\LightAjaxFileUploadManagerService
    methods:
        setApplicationDir:
            dir: ${app_dir}
    methods_collection: []
#        -
#            method: addActionLists
#            args:
#                actionLists:
#                    lka_user_profile:
#                        -
#                            storeDir: www/uploads/test
#                            returnUrlDir: /uploads/test
#                            imageTransformer: resize(200)
#        -
#            method: addValidationRules
#            args:
#                validationRules:
#                    id_one: []




```


How does it work?
--------------

This plugin defines the [ajax file upload protocol](https://github.com/lingtalfi/Light_AjaxFileUploadManager/blob/master/doc/pages/ajax-file-upload-protocol.md),
and provides tools for implementing it.

The backend implementation is covered entirely by this plugin.

For the js client implementation, we recommend using the [js file uploader](https://github.com/lingtalfi/jsFileUploader) client,
as this plugin has helper methods that facilitate the implementation of the gui side with the **js file uploader**.


Please refer to the protocol and the auxiliary documents referenced in the summary to get started.

Basically what you want to do is create a profile for each ajax upload field that you want, and that's it.

The profile is created by calling the addActionLists (and addValidationRules if you need some validation rules) methods.

I recommend to use CSRF protection all the time. This is explained in the aforementioned documents. 










History Log
=============

- 1.0.0 -- 2019-08-06

    - initial commit