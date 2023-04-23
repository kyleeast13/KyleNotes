# Clean Architecture

One of my biggest issues is knowing how to organize a project. Coming from more of a scientific background, I'm very good at creating classes, making/optimizing methods, managing data/IO, etc. But one of the issues that I always have problems with is how do I organize my projects? I'm very used to the Python model where you can create classes with methods in separate files and then call them into the main file. But I usually am only creating 2-5 classes for a majority of my uses. But not that I'm looking to expand from Python into more complex languages, I find myself having issues organizing my work.

Because of this, I've been focusing on learning how to organize my projects, and one of my favorite architectures so far has been clean architecture. Clean architecture organizes classes and methods based on their level of abstraction. This organization makes development much easier (and cleaner...) but also allows for expandability and evolution as you develop your code.

Clean architecture is layered from most abstract (most self-consistent) to least abstract in the following way:
![Clean Architecture diagram from http://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html](assets/What is Clean Architecture1.png)
1. Entity (Domain) - This is the base layer, it contains all of the general entities and interfaces that require NO dependencies to any of the other layers.
2. Use Cases (Application) - This layer only has dependencies on the Entity layer. This layer includes all of the logic that applies manpulating data. This layer does NOT include the logic for accessing either the UI or the database. It only knows how different abstract classes interact with eachother.
3. Controllers (Interface) - This layer has dependencies on the Application Layer. And manages the interactions between the Application layer and the external dependencies, including external APIs, the UI, and databases/file system. This is generally the RESTful API.
4. External Interface (UI) - This layer is the front-end layer and has dependencies on both the Allication and Interface layers. This is generally the MVC front-end layer
