# solidcodinginpython


I have made an attempt to demonstrate SOLID coding techniques in Python.I have used Repl to make the python file.

The first example of SOLID coding techniques is 

#Single Responsibility Principle

according to it a class should have only one job. So if a class or function has more than one responsibility, it becomes coupled. A change to one responsibility results to modification of the other responsibility.

so as i have mentioned in my example I HAVE USED OPERATIONS function as the main function and broke it down to further smaller functions named as 

addition,substration,division and  multiplication 

instead of operations function doing all the job



#2 Open-Closed Principle
#Software entities(Classes, modules, functions) should be open for extension, not modification.





Liskov Substitution Principle

The main idea behind Liskov Subtitution Principle is that, for any class, a client should be able to use any of its subtypes indistinguishably, without even noticing, and therefore without compromising the expected behavior at runtime.


 in this example we are having a set of oprations to be perfromed on diffrent vehicles like car truck and jeep.


  

here in the above class we have a bike not requiring to accelerate, that's why we dont need accelerate() in the above class, but this violates the liskoff usbstitution principle 



Interface Segregation Principle
In the contest of classes, an interface is considered, all the methods and properties “exposed”, thus, everything that a user can interact with that belongs to that class.


  
  

The Dependency Inversion Principle (DIP)
“Abstractions should not depend on details. Details should depend on abstraction. High-level modules should not depend on low-level modules. Both should depend on abstractions”
So, that abstractions (e.g., the interface, as seen above) should not be dependent on low-level methods but both should depend on a third interface.



here the diffrent cars are depending on the concept
of engine starting without the concept itself 
present inside the modules here modules being diffrent 
cars.The "engine starting" itslef has been derived from
abstract base class. If we want we can add more modules like jeep,tractor etc and implement "engine starting "
in it







