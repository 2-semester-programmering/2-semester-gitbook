---
description: Exercise in using Spring Boot MVC
---

# My First Website

After creating an empty new Spring project in IntelliJ through the _Spring Initializer Template_: [#3 Hello Spring](https://github.com/StudentsAdministration/03\_hello\_spring), you should now create your first _Hello World Website_.

_Remember that this is a step by step instruction. It does not explain all the concepts in details. This explanaition you will get from your teacher in class._

You should now have a folder and file structure that looks something like this:

![](https://github.com/clbokea/spring\_getting\_started/blob/master/img/Screen%20Shot%202017-11-17%20at%2010.58.46.png)

If you open your _**src**_ folder you will see a _**main**_ and a _**test**_ folder.\
Delete the:

* _**test**_ folder\
  And delete the:
* _**mvnw**_ and the _**mvnw.cmd**_ files.

(you could leave them in the project, but since we are not going to use them we delete them for a better overview)

![](https://github.com/clbokea/spring\_getting\_started/blob/master/img/Screen%20Shot%202017-11-17%20at%2011.06.38.png)

Now you have a project structure that looks like this:

![](https://github.com/clbokea/spring\_getting\_started/blob/master/img/Screen%20Shot%202017-11-17%20at%2011.13.55.png)

### Create a normal java class file

In the demo folder create a class and call it HomeController.java.\


* Right click the "demo" folder
* chose: New -> Java Class
* Name: HomeController
* Kind: Class

![](https://github.com/clbokea/spring\_getting\_started/blob/master/img/Screen%20Shot%202017-11-17%20at%2023.12.13.png)

#### Create an index method in the class

Create a public method called index with a return type of String, and return the string "index".

![](https://github.com/clbokea/spring\_getting\_started/blob/master/img/Screen%20Shot%202017-11-17%20at%2023.19.40.png)

Add _**@Controller**_ above the class definition and _**@GetMapping("/")**_ above the method definition.

![](https://github.com/clbokea/spring\_getting\_started/blob/master/img/Screen%20Shot%202017-11-17%20at%2023.30.50.png)

### Create an index.html file

* right click _**resource -> template**_ folder
* Choose: _**New -> html file**_
* Name: index
* Kind: Html 5 file
* Delete the `<meta charset="UTF-8">` tag
* Add `xmlns:th="http://www.thymeleaf.org"`  to the `<html lang="en">` tag

![](https://github.com/StudentsAdministration/03\_my\_first\_website/blob/master/img/newHtml.png)

Make your code look like the image above. (do your best :))

#### Run the application

push the green start button in the upper right corner.

![](https://github.com/clbokea/spring\_getting\_started/blob/master/img/Screen%20Shot%202017-11-17%20at%2023.49.09.png)

Open your browser and type http://localhost:8080

![](https://github.com/clbokea/spring\_getting\_started/blob/master/img/Screen%20Shot%202017-11-17%20at%2023.53.41.png)_© clbo@kea.dk_
