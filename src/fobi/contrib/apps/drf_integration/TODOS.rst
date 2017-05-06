TODOS
=====
Based on MoSCoW principle.

Must haves
----------
+ Correct OPTIONS call.
+ Add custom field instance handler for handling data of the custom field
  instances. Do it this way and not the other way, since things get
  complicated when we start to deal with wizards.
+ Find out how to handle further the submitted data? It should be in
  accordance with fobi concepts of loosely couple parts. After successful
  submission, the fobi form callbacks, handlers and that kind of things
  should be fired for the given form entry. Thus, it should likely be the
  same in this case. Probably each CustomFieldInstancePlugin should get
  a method ``drf_submit_plugin_form_data``, which should mimic the
  ``submit_plugin_form_data` of the ``fobi.base``. It should also contain
  code for ``drf_fire_form_callbacks`` (mimic ``fire_form_callbacks``).
+ Find out why setting initial values for integer field breaks.
+ Write some basic tests for DRF integration.
+ Finish existing core fields (without relation- and presentational- fields
  yet).
+ Add `mail` and `http_repost` DRF handler plugins.
- Add/finish documentation.
- Add permission checks in the DRF view. If form is not public and user
  isn't author of the form, he shouldn't be able to view it.
- In DRF listing view, if user isn't authenticated, show only public forms.

Should haves
------------
- Find why HiddenInput tests fail.
- Add custom field instance callback for handling data of the custom field
  instances. Do it this way and not the other way, since things get
  complicated when we start to deal with wizards.
- Add more fields (relation- and presentational- fields).
- Think of what to do with presentational fields (perhaps just display?)
- Somehow, the `file` plugin data, when submitted, isn't shown properly in the
  posted data (by DRF), although is posted 100% correctly.
- In the API form view, use memoize technique or cache the value somehow to
  reduce the number of queries.

Could haves
-----------
- Finally implement DRF integration for form-wizards as well.

Would haves
-----------
- Remove codebin.py at the end.