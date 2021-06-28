## Domain Modeling

* domain modeling is the proccess of solving the problem programmarly.we convert each entity and its properties and behaviours into a model.


## Chapter 3 - Functions, Methods, and Objects (pp.106-144)

* WHAT IS AN OBJECT? you can say that an object is a thought of a real world model . It groups a sety of variables(in object we called them properities) and a set of functions(in object we called them methods).example

    ```js
    var hotel = {
    name: 'Quay',
    rooms : 40,
    booked: 25,
    checkAvailability: function() {
    return this.rooms - this.booked;
    }
    } ;
    ```

* in an object the properities and functions have a name and value . we call the name key in object.
* **Creating an object using literal notation** : we can create an object by declaring the name of that object followed by equal sign and curly braces and inside curly braces we assign the properties and methods.
* each property or method has a key followed by colon and then the value.
* we can access the object properties and methods by writing the name of the object then dot notation followed by the property or method of that object.
* we can also access the object properties and not object methods by the name of the object then square bracket and inside square bracket we insert the property key.
  
* **Creating an object using Constructor notation** : 
* we can build a model or a tepmlate to create objects as many as we need.
* building objects in this way help the developers to to avoid duplicated code and make the code more organized and more readable.

* ```js
    function Hotel (name, rooms, booked) {
    this.name = name;
    this.rooms = rooms;
    this.booked = booked;
    this.checkAvailability = function(){
    return this.rooms - this.booked;
    }
    } ;
    var quayHotel = new Hotel('Quay', 40, 25;
    var parkHotel = new Hotel( ' Park', 120, 77);
    ```

* in the code above we create a Hotel  function which you can say it is a model for all the hotels and all the hotels shares the same properties and same methods.
* there are three groups of built-in objects:
   1. Browser Object Model.
   2. Document Object Model.
   3. Global Javascript Objects.

## Chapter 6 - Tables (pp.126-145)

* What's a Table? table is a grid format of information.
* Basic Table Structure :

```html
    <table>
    <tr>
    <td>15</td>
    <td>15</td>
    <td>30</td>
    </tr>
    <tr>
    <td>45</td>
    <td>60</td>
    <td>45</td>
    </tr>
    <tr>
    <td>60</td>
    <td>90</td>
    <td>90</td>
    </tr>
    </table>
```

* to creat a table we used table tag and between opening and closing tags we insert many `tr`(table row) tag and between `tr` we insert `td` table data

* `<th>` is used like `td` and the purpose of it, it is to represent heading for clomn or row.

* we use `rowspan` and `colspan` attributes to skip specified numbner of rows or columns

* we use use the following three elements when we have a long table to distinguish between content and header and footer

     1. `<thead>`The headings of the table should
    sit inside the `<thead>` element.
     1. `<tbody>` The body should sit inside the `<tbody>` element.
     2. `<tfoot>` The footer belongs inside the `<tfoot>` element.
