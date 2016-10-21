#MVP

MVP(Model-view-presenter) is an architecture pattern used in mobile development for...

###Short introduction
MVP is an architectural pattern widely used for developers when working on user interfaces. Its main concept resides in separating all the logic in three components:
- _Model_, wich represents the data to be displayed
- _View_, who acts as a mediator between the user and the app
- _Presenter_, who retrieves the model from the storage and prepares to display it in the view

###Why are we doing this?
Having an architecture is a common practice when working on teams. It usually eases the understanding when swithching projects as the dev is expecting the same style between them. We know that there are more architectures, like MVC or MVVM, but we chose MVP. Why? Because we are google fanboys. In the google repositories, they have example apps based on MVP to show how to solve many development problems that leads to inconsistent name classes, unmantainable code, difficult testing and extensibility. And we want that for our code. We want our projects to be as flexible as posible so us (the developers) don't go crazy trying to understand another dev's code.



##Our implementation
###Model
Here, we have to take a wide look to what is considered _model_. Maybe your first thought was "model are data bag classes", but model is much more. We consider inside model to:
- API clients
- SDKs and other content providers
- Request and response POJOs
- Entities

####Entities
First of all, let's talk about the last item. For us, the real model will be all the classes named *entities*. These classes will fulfill the contract of an _item_ (see [Design by Contract](http://www.google.com)) and their instances are the objects that we should shove around the entire app. They won't know anything about the DB or the server requests or responses, but they know how to create themselves with a response and how to create a request by themselves.

####API clients
It's almost guaranteed that this will be a [Retrofit REST client](http://square.github.io/retrofit/). This should be classes who are responsible to make the requests to the servers and retrieve the information as a java object. We usually code them as [singletons](https://en.wikipedia.org/wiki/Singleton_pattern), it's better if you see this for yourself in the DemoApp or AndroidTraining.

####Request and response POJOs
