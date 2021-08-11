# Django Workshop Exercise 7

In this exercise we will use bootstrap and some javascript to style the page which is repsonsible for listing items in a ToDoList.
<br/><br/>
## 1. Prepare for the coding environment  

SSH into the test machine. The password is 123456.
```sh
ssh your_upi@130.216.39.213
```
Once you are in, activate the python virtual environment and cd into the project folder
```sh
workon dj && cd mysite
```
<br/><br/>
## 2. Style the buttons in the item listing page
From the app's home page, if you click on any of the ToDoList it will take you to the "item listing" page. The template for rendering this page is located at "main/templates/main/list.html". Open this file and apply styling to the buttons inside the form so they resemble the image below:

![alt text](https://github.com/phu004/django_part_seven/blob/main/workshop7a.png)

<details>
  <summary>Click for solution</summary>
  
```sh
  <!-- ToDo: Apply styles to the buttons so they resemble the image from the exercise slides  -->
  <!-- Hint: Have a look at how style is applyed to buttons in create.html -->
  <br>
  <div class="input-group mb-3">
      <button type="submit" name="newItem" value="newItem" class="btn btn-success">Add Item</button>
      <input type="text" name="new">
  </div>
  <button type="submit" name="save" value="save" class="btn btn-success">Save</button>
```
</details>

<br/><br/>
## 3. Use javascript to style the item list
The next thing to do is to apply styling to the item list itself. However since the item list is represented by a Django form object, and we do not have direct access to the html element, that's where javascript comes in handy. Take a look at the page source, notice how list element that is generated by Django form:
```sh
<ul id="id_items">
    <li><label for="id_items_0"><input type="checkbox" name="items" value="2" id="id_items_0" checked>First Item</label></li>
    <li><label for="id_items_1"><input type="checkbox" name="items" value="3" id="id_items_1" checked>Second Item</label></li>
    <li><label for="id_items_2"><input type="checkbox" name="items" value="4" id="id_items_2">Third Item</label></li>
</ul>
```

The goal is to apply the bootstrap style class "list-group list-group-flush" to "ul" and then apply the style class "list-group-item" to all the child "li" elements. We use javascript to dynamically apply any style class to any element using the following syntax: 

```sh
  myElement.className = 'my-css-class'
```

Complete the javascript section in "main/templates/main/list.html" so out item listing page resembles the image below:

![alt text](https://github.com/phu004/django_part_seven/blob/main/workshop7b.png)

<details>
  <summary>Click for solution</summary>
  
```sh
$('document').ready(function(){
    //ToDo: change the class for the ul element (with id="id_items") to 'list-group list-group-flush'.
    //Then change all its child li element's class to "list-group-item"
    var my_ul = document.getElementById("id_items");
    my_ul.className  = 'list-group list-group-flush';
    my_lis =  my_ul.getElementsByTagName("li");
    for(var i = 0; i < my_lis.length; i++)
        my_lis[i].classList.add("list-group-item");
 });
```
</details>
