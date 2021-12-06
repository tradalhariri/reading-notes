# Django Tutorial Part 9: Working with forms

## Overview
- An HTML form is used to collect user input. The user input is most often sent to a server for processing.

- The <form> element is a container for different types of input elements, such as: text fields, checkboxes, radio buttons, submit buttons, etc.


- While we haven't created any forms in this tutorial so far, we've already encountered them in the Django Admin site — for example, the screenshot below shows a form for editing one of our Book models, comprised of a number of selection lists and text editors.

![](https://mdn.mozillademos.org/files/13979/admin_book_add.png)

- Django provides a framework that lets you define forms and their fields programmatically, and then use these objects to both generate the form HTML code and handle much of the validation and user interaction.




## Django form handling process
- Django form processing based on ： view to get the request and perform any action required ， includes reading data from the model, then generating and returning HTML page （ from the templat ）， we pass a context that contains the data to be displayed.
-  what makes things more complicated is that ， the server also needs to be able to process user-provided data and in the event of any errors ， redisplay the page.

- the following shows Django a flowchart of how to handle a form request, starting with a request for a page that contains the form （ display in green ）：

![django](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms/form_handling_-_standard.png)

- Based on the diagram above, the main things that Django's form handling does are:**

  1. Display the default form the first time.

  2. Receive data from a submit request and bind it to the form

  3. Clean and validate the data.

  4. f any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.

  5. If all data is valid, perform required actions (e.g. save the data, send an email, return the result of a search, upload a file, etc.)

  6. Once all actions are complete, redirect the user to another page.


## Declaring a Form

```python
import datetime

from django import forms

from django.core.exceptions import ValidationError
from django.utils.translation import ugettext_lazy as _

class RenewBookForm(forms.Form):
    renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")

    def clean_renewal_date(self):
        data = self.cleaned_data['renewal_date']

        # Check if a date is not in the past.
        if data < datetime.date.today():
            raise ValidationError(_('Invalid date - renewal in past'))

        # Check if a date is in the allowed range (+4 weeks from today).
        if data > datetime.date.today() + datetime.timedelta(weeks=4):
            raise ValidationError(_('Invalid date - renewal more than 4 weeks ahead'))

        # Remember to always return the cleaned data.
        return data
```

### References
[Django Forms](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms)