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

class operations():
  def multiplication(self,a,b):
    answer = a*b
    return answer

  def addition(self,a,b):
    answer = a+b
    return answer

#implementation from here
from abc import ABC,abstractmethod


class addition(ABC):
  @abstractmethod

  def multiplication(self,a,b):
    return a*b

class multiplication(ABC):
  @abstractmethod

  def multiplication(aelf,a,b):
    return a*b

class operation(addition,multiplication):
  

  def multiplication(self,a,b):
    print(a*b) 


  def addition(aelf,a,b):
    print(a+b)




#Liskov Substitution Principle

#The main idea behind Liskov Subtitution Principle is that, for any class, a client should be able to use any of its subtypes indistinguishably, without even noticing, and therefore without compromising the expected behavior at runtime.


# in this example we are having a set of oprations to be perfromed on diffrent vehicles like car truck and jeep.

class operations():
  def start_engine():
    pass

  def stop_engine():
    pass

  def acclerate():
    pass

class Car(operations):
  def start_engine():
    # coding to start engine
  def stop_engine():
    #coding to stop engine
  def acclerate():
    #coding to accelerate 



class bikewithconstantspeed(operations):
  def start_engine():
    # coding to start engine
  def stop_engine():
    #coding to stop engine
  

#here in the above class we have a bike not requiring to accelerate, that's why we dont need accelerate() in the above class, but this violates the liskoff usbstitution principle thus the correct approach would be as follows ::



class operations():
  def start_engine():
    pass

  def stop_engine():
    pass


class Operartion_acceleration(operations):
  def acclerate():
    pass

class Car(Operartion_acceleration):
  def start_engine():
    # coding to start engine
  def stop_engine():
    #coding to stop engine
  def acclerate():
    #coding to accelerate 



class bikewithconstantspeed(operations):
  def start_engine():
    # coding to start engine
  def stop_engine():
    #coding to stop engine



#Interface Segregation Principle
#In the contest of classes, an interface is considered, all the methods and properties “exposed”, thus, everything that a user can interact with that belongs to that class.

#on implementing the same we get as:



from abc import ABC,abstractmethod


class start_engine(ABC):
  @abstractmethod
  
  def self_start(self):
    pass

  def manual_start(self):
    pass


class stop_engine(ABC):
  @abstractmetohd

  def self_stop(self):
    pass

  def manual_stop(self):
    pass


class transmission_engine(ABC):
  @abstractmetohd

  def automatictransmission(self):
    pass

  def manualtransmission(self):
    pass



class car(start_engine,stop_engine,transmisson_engine):
  def self_start(self):
    #code satisfying required functionality

  def manual_start(self):
    #code satisfying required functionality
  
  def self_stop(self):
    #code satisfying required functionality

  def manual_stop(self):
    pass
  
  def automatictransmission(self):
    pass
    
  def manualtransmission(self):
    pass


class bike(start_engine,stop_engine):
  def self_start(self):
    #code satisfying required functionality

  def manual_start(self):
    #code satisfying required functionality
  
  def self_stop(self):
    #code satisfying required functionality

  def manual_stop(self):
    pass
  
''''
The Dependency Inversion Principle (DIP)
“Abstractions should not depend on details. Details should depend on abstraction. High-level modules should not depend on low-level modules. Both should depend on abstractions”
So, that abstractions (e.g., the interface, as seen above) should not be dependent on low-level methods but both should depend on a third interface.
'''

from abc import ABC, abstractmethod

class engine_starting(ABC):
  @abstractmethod 
  def turn_on(self):
    pass
  
  @abstractmethod
  def turn_off(self):
    pass


class sedan_car(engine_starting):

  def turn_on(self):
    print("Engine turned on")
  
  
  def turn_off(self):
    print("Engine  turned off")



class Truck:
  def __init__(self,c:engine_starting):
    self.client = c
    self.on = False


  def press(self):
    if self.on:
    self.client.turn_off()
    self.on = False

    else:
      self.client.turn_on()
      self.on = True


''''
here the diffrent cars are depending on the concept
of engine starting without the concept itself 
present inside the modules here modules being diffrent 
cars.The "engine starting" itslef has been derived from
abstract base class. If we want we can add more modules like jeep,tractor etc and implement "engine starting "
in it
'''






