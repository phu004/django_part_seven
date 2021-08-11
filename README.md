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
## 2. Use bootstrap to style the buttons in the item listing page
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
