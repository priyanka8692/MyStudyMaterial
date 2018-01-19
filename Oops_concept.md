## Polymorphism:

	-It is concept by which we can perform single action in  different ways.
	-Poly means many and morphs means forms so polymorphism means many forms.
	-Only methods are overriden not the data members.
	-Run time polymorphism(Dynamic method dispatch):
		* Process in which call to overidden method is resolved at run-time rather than compile time.
		* Upcasting : When the reference variable of the Parent class refer to the object of
		Child class,it is known as Upcasting.

		Example:
			class Animal{
				void eat() {
					System.out.println("eating.....");
				}
			}

			class Cow extends Animal{
				void eat() {
					System.out.println("eats grass");
				}
			}

			class Dog extends Animal{
				void eat() {
					System.out.println("eats bone");
				}
			}
			public class RunTimePolymorphism {

				
				public static void main(String[] args) {
					// TODO Auto-generated method stub
					Animal obj = new Dog();
					obj.eat();
					Animal obj1 = new Cow();
					obj1.eat();

				}

			}

			Output:
			eats bone
			eats grass

## Inheritance : Inheritance is a mechanism by which one object acquire all the properties and behaviour of the Parent object.

	-Need of Inheritance:
	1)for method overriding(achieving runtime polymorphism)
	2)for code reusability

	Example:
		class Animal{  
		void eat(){System.out.println("eating...");}  
		}  

		class Dog extends Animal{  
		void bark(){System.out.println("barking...");}  
		}  

		class Cat extends Animal{  
		void meow(){System.out.println("meowing...");}  
		}  

		class TestInheritance3{  
		public static void main(String args[]){  
		Cat c=new Cat();  
		c.meow();  
		c.eat();  
		 
		}}  

		Output:
		meowing...
		eating...

## Encapsulation:
	-Wrapping data(variable) and the code acting as data(method) into single unit is called Encapsulation.

	-How to achieve Encapsulation :
		* Declare the variable of the class as private
		* Provide public setter and getter methods to modify and view the variable values.

		Example:
		public class EncapTest {
		   private String name;
		   private String idNum;
		   private int age;

		   public int getAge() {
		      return age;
		   }

		   public String getName() {
		      return name;
		   }

		   public String getIdNum() {
		      return idNum;
		   }

		   public void setAge( int newAge) {
		      age = newAge;
		   }

		   public void setName(String newName) {
		      name = newName;
		   }

		   public void setIdNum( String newId) {
		      idNum = newId;
		   }
		}