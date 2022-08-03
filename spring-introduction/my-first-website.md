---
description: Exercise in using Spring Boot MVC
---

# My First Website

After creating an empty new Spring project in IntelliJ through the _Spring Initializer Template,_ you should now create your first _Hello World Website_.

_Remember that this is a step by step instruction. It does not explain all the concepts in details. This explanation you will get from your teacher in class._

You should now have a folder and file structure that looks something like this:

![](<../.gitbook/assets/Screen Shot 2017-11-17 at 10.58.46.png>)

If you open your _**src**_ folder you will see a _**main**_ and a _**test**_ folder.\
Delete the:

* _**test**_ folder\
  And delete the:
* _**mvnw**_ and the _**mvnw.cmd**_ files.

(you could leave them in the project, but since we are not going to use them we delete them for a better overview)

![](<../.gitbook/assets/Screen Shot 2017-11-17 at 11.06.38.png>)

Now you have a project structure that looks like this:

![](<../.gitbook/assets/Screen Shot 2017-11-17 at 11.13.55.png>)

### Create a normal java class file

In the demo folder create a class and call it HomeController.java.\


* Right click the "demo" folder
* chose: New -> Java Class
* Name: HomeController
* Kind: Class

![](<../.gitbook/assets/Screen Shot 2017-11-17 at 23.12.13.png>)

#### Create an index method in the class

Create a public method called index with a return type of String, and return the string "Hello World".

![](<../.gitbook/assets/Screenshot 2022-08-03 at 21.12.59.png>)

Add _**@RestController**_ above the class definition and _**@GetMapping("/")**_ above the method definition. As a return value you could write "Hello World" or something else of your own choice.&#x20;

![](<../.gitbook/assets/Screenshot 2022-08-03 at 21.08.28.png>)

Run the application

push the green start button in the upper right corner.

![](<../.gitbook/assets/Screen Shot 2017-11-17 at 23.49.09 (1).png>)

Open your browser and type http://localhost:8080

![](<../.gitbook/assets/Screenshot 2022-08-03 at 21.07.41.png>)

_© clbo@kea.dk_
