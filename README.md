# week3flutter

// Abstraction
abstract class Animal {
  void makeSound(); // Abstract method
}

// Encapsulation
class Dog extends Animal {
  // Private variable
  String _name;

  // Constructor
  Dog(this._name);

  // Accessor for the private variable
  String get name => _name;

  @override
  void makeSound() {
    print("Woof! My name is $_name.");
  }
}

class Cat extends Animal {
  String _name;

  Cat(this._name);

  @override
  void makeSound() {
    print("Meow! My name is $_name.");
  }
}

// Inheritance and Polymorphism
class PetOwner {
  void introducePet(Animal pet) {
    pet.makeSound(); // Polymorphism: calling the same method on different subclasses
  }
}

void main() {
  // Creating instances of Dog and Cat
  Dog myDog = Dog("Buddy");
  Cat myCat = Cat("Whiskers");

  // Creating a PetOwner
  PetOwner owner = PetOwner();

  // Introduce pets
  owner.introducePet(myDog); // Outputs: Woof! My name is Buddy.
  owner.introducePet(myCat); // Outputs: Meow! My name is Whiskers.
}
