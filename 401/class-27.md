# Django Tutorial Part 3: Using models

## Overview
> Django web applications access and manage data through Python objects referred to as models. Models define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc. The definition of the model is independent of the underlying database — you can choose one of several as part of your project settings.
Once you've chosen what database you want to use, you don't need to talk to it directly at all — you just write your model structure and other code, and Django handles all the dirty work of communicating with the database for you.

## Designing the LocalLibrary models

- The following is UML diagram for designing LocalLibrary database models.

![](https://mdn.mozillademos.org/files/16479/local_library_model_uml.png)



### Model definition

- Models are usually defined in an application's models.py file.
-  They are implemented as subclasses of django.db.models.Model, and can include fields, methods and metadata.

- The code fragment below shows a `typical` model, named MyModelName:

> from django.db import models
class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""
    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...
    # Metadata
    class Meta:
        ordering = ['-my_field_name']
    # Methods
    def get_absolute_url(self):
        """Returns the url to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])
    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name



### Models consist of :
1. Fields : A model can have an arbitrary number of fields, of any type — each one represents a column of data that we want to store in one of our database tables.
   *  Each database record (row) will consist of one of each field value.

   >`my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')`

2. Metadata: 
   - One of the most useful features of this metadata is to control the default ordering of records returned when you query the model type.

    >class Meta:
        ordering = ['-my_field_name']
    - adding `-` before field name means the order will be in reverse.

3. Methods:
   - Atleast, in every model you should define the standard Python class method __str__() to return a human-readable string for each object.
   -  Another common method to include in Django models is get_absolute_url(), which returns a URL for displaying individual model records on the website 

    >def get_absolute_url(self):
        """Returns the url to access a particular instance of the model."""
        return reverse('model-detail-view', args=[str(self.id)])

# Django admin site

## Overview
- The Django admin application uses models to automatically build tables corresponding to each models.
- you can then create super account to mangage the content of your website.
- but you need first to register your models.


## Creating a superuser
- using `manage.py` you can create super account that has all permissions on all tables in the database.
-  >`python3 manage.py createsuperuser`
-  then enter all the required info (name,email,password)
- >`python3 manage.py runserver`
- then go ahead to the  '/admin' to see the admins panel
  ![](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site/admin_home.png)

### References
[Django Using models](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)
<br>
[Django admin site](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)