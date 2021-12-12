# DRF Permissions

## Permissions

- Together with authentication and throttling, permissions determine whether a request should be granted or denied access.

- Permission checks are always run at the very start of the view, before any other code is allowed to proceed.

- Permission checks will typically use the authentication information in the `request.user` and `request.auth` properties to determine if the incoming request should be permitted.


## How permissions are determined

- Permissions in REST framework are always defined as a list of permission classes.
- Before running the main body of the view each permission in the list is checked.
- If any permission check fails an `exceptions.PermissionDenied`or `exceptions.NotAuthenticated` exception will be raised, and the main body of the view will not run.
- When the permissions checks fail either a "`403 Forbidden`" or a "`401 Unauthorized`" response will be returned, according to the following rules:
  - The request was successfully authenticated, but permission was denied. An `HTTP 403 Forbidden` response will be returned.
  - The request was not successfully authenticated, and the highest priority authentication class does not use WWW-Authenticate headers. An `HTTP 403 Forbidden` response will be returned.
  - The request was not successfully authenticated, and the highest priority authentication class does use WWW-Authenticate headers. An `HTTP 401 Unauthorized` response, with an appropriate WWW-Authenticate header will be returned.

## Object level permissions

1. REST framework permissions also support object-level permissioning.
2. Object level permissions are used to determine if a user should be allowed to act on a particular object, which will typically be a model instance.
3. Object level permissions are run by REST framework's generic views when `.get_object()` is called
4. As with view level permissions, an `exceptions.PermissionDenied` exception will be raised if the user is not allowed to act on the given object.
5. If you're writing your own views and want to enforce object level permissions, or if you override the `get_object` method on a generic view, then you'll need to explicitly call the `.check_object_permissions(request, obj)` method on the view at the point at which you've retrieved the object.


## Setting the permission policy

- The default permission policy may be set globally, using the `DEFAULT_PERMISSION_CLASSES` setting.
```python
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```
- If not specified, this setting defaults to allowing unrestricted access:
```python
'DEFAULT_PERMISSION_CLASSES': [
   'rest_framework.permissions.AllowAny',
]
```

- You can also set the authentication policy on a per-view, or per-viewset basis, using the `APIView` class-based views.
```python
from rest_framework.permissions import IsAuthenticated
from rest_framework.response import Response
from rest_framework.views import APIView

class ExampleView(APIView):
    permission_classes = [IsAuthenticated]

    def get(self, request, format=None):
        content = {
            'status': 'request was permitted'
        }
        return Response(content)
```


## API Reference


1. AllowAny : The `AllowAny` permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.
2. IsAuthenticated : The `IsAuthenticated` permission class will deny permission to any unauthenticated user, and allow permission otherwise.
3. IsAdminUser : The `IsAdminUser` permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.
4. IsAuthenticatedOrReadOnly : the `IsAuthenticatedOrReadOnly` will allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is one of the "safe" methods; `GET`, `HEAD` or `OPTIONS`.
5. DjangoModelPermissions : This permission class ties into Django's standard `django.contrib.auth` model permissions.This permission must only be applied to views that have a `.queryset` property or `get_queryset()` method.Authorization will only be granted if the user is authenticated and has the relevant model permissions assigned.

- `POST` requests require the user to have the add permission on the model.
- `PUT` and PATCH requests require the user to have the change permission on the model.
- `DELETE` requests require the user to have the delete permission on the mode.

> The default behaviour can also be overridden to support custom model permissions.

6. DjangoModelPermissionsOrAnonReadOnly : Similar to `DjangoModelPermissions`, but also allows unauthenticated users to have read-only access to the API.
7. DjangoObjectPermissions : This permission class ties into Django's standard object permissions framework that allows per-object permissions on models. In order to use this permission class, you'll also need to add a permission backend that supports object-level permissions, such as django-guardian. As with `DjangoModelPermissions`, this permission must only be applied to views that have a .queryset property or .get_queryset() method. Authorization will only be granted if the user is authenticated and has the relevant per-object permissions and relevant model permissions assigned.



## Custom permissions


- To implement a custom permission, override `BasePermission` and implement either, or both, of the following methods:
  - `.has_permission(self, request, view)`
  - `.has_object_permission(self, request, view, obj)`

- The methods should return `True` if the request should be granted access, and `False` otherwise.
- If you need to test if a request is a read operation or a write operation, you should check the request method against the constant `SAFE_METHODS`, which is a tuple containing '`GET`', '`OPTIONS`' and '`HEAD`'.

```python
if request.method in permissions.SAFE_METHODS:
    # Check permissions for read-only request
else:
    # Check permissions for write request
```


## Third party packages

1. DRF - Access Policy
2. Composed Permissions
3. REST Condition
4. DRY Rest Permissions
5. Django Rest Framework Roles
6. Django REST Framework API Key
7. Django Rest Framework Role Filters
8. Django Rest Framework PSQ

### References 
[DRF Permissions](https://www.django-rest-framework.org/api-guide/permissions/)