#MVP

MVP(Model-view-presenter) is an architecture pattern used in mobile development for...

####Short introduction
MVP is an architectural pattern widely used for developers when working on user interfaces. Its main concept resides in separating all the logic in three components:
- _Model_, wich represents the data to be displayed
- _View_, who acts as a mediator between the user and the app
- _Presenter_, who retrieves the model from the storage and prepares to display it in the view

####Why are we doing this?
Having an architecture is a common practice when working on teams. It usually eases the understanding when swithching projects as the dev is expecting the same style between them. We know that there are more architectures, like MVC or MVVM, but we chose MVP. Why? Because we are google fanboys. In the google repositories, they have example apps based on MVP to show how to solve many development problems that leads to inconsistent name classes, unmantainable code, difficult testing and extensibility. And we want that for our code. We want our projects to be as flexible as posible so us (the developers) don't go crazy trying to understand another dev's code.



##Our implementation (Android)
####Model
For us, the model will be all the classes named *entities*. These classes will fulfill the contract of an _item_ (see [Design by Contract](http://www.google.com)) and their instances are the objects that we should shove around the entire app.