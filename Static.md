## Static:
-Static is a non-access modifier.
-It is used for memory management.
-It is applicable for :
	1)variable 
	2)method
	3)block
	4)class

## Static variable:
	-It is common to all instance of class
	-It is class level variable
	-Only one single copy of static variable is created and shared among all instance
	 of the class
	-Memory allocation of such variable happens at the time of class loading.
	-Static variable are initialized before the initialization of the instance variable.

	public class StaticVariableDemo {
	  	  	static int count = 0;// static variable
		  	//int count = 0;
		  	public int increment(){
			  count++;
			  return count;
		 	}
		    
		    public static void main(String[] args) {
			StaticVariable obj1 = new StaticVariable();
			StaticVariable obj2 = new StaticVariable();
			obj1.increment();
			obj2.increment();
			System.out.println(obj1.count);
			System.out.println(obj2.count);
		} 
	}

	- If variable is static value is shared among objects .
	Firstly value of the count on calling obj1.increment will become 1 
	and on calling obj2.increment count value changes and becomes 2 .
	As count is shared among both object we het out put 2.

	- If it is instance variable then each object will have copy of 
	instance variable.So in this case the on calling obj1.increment 
	value of count(its own copy) sofor obj1 becomes 1 and for object 
	it incrmenet value in its own copy so it become 1 for it .

### When to use static variable:
Use static variable when the property is common to all the object.
Example name of the college for all the student in student class can 
be made static.



## Static Method:
	-Static methods are associated with the class itself
	-They are called without using object.
	-They are shared among all object of the class.
	-They cannot be overriden as they are associated with the class not with the object.
	-But yes they can be over loaded as they can be resolved at compile time.
	-Ther cannot be refered to this or super in any way.
	-They can directly access the static data.
	-NOTE: 
		* cannot make static reference to non-static variable that is we cannot use non-static variable in static method.
		* cannot call non-static method in static method.

	Example:

	public class StaticMethodDemo {
		static int number = 20;
		int numberTwo = 25;
		static void m1() {
			number=21;
			//cannot make static refernce to non-static variable
			//System.out.println(numberTwo);
			
			System.out.println(number);
			
			//cannot make static refernce to non-static method
			//m2();
		}
		void m2() {
			System.out.println("welcome");
		}
		public static void main(String[] args) {
			// TODO Auto-generated method stub
			m1();
		}

	}

	Output: 21
	static method can change value odf static varivle .

### When to use Static method
	-If the method is not using any instance variable.
	-If any operation is not dependent on instance creation.
	-If you are sure that code would not be changed or overriden.
	(A ststic method cannot be overriden).


### Static block:
	-Code in static block is executed only ones.
	-It is used to initialize static variable.
	-It execute when first time you make object of that class or
	first time you access static member  of that class.
	-Static blocks are executed before the constructor.
	-They are executed before main method at the time of class loading.

	Example:

	public class StaticBlockDemo {
		static int i;
		static {
			i=10;
			System.out.println("static block demo");
			
		}
		public static void main(String[] args) {
			// TODO Auto-generated method stub
			System.out.println(StaticBlockDemo.i);
			

		}

	}

	Output:
	static block demo
	10

### Static Class:

	- Only nested class in Java can be static.
	- Main points for static nested class and non-static nested class
		* Nested static class does not need reference of the outer class but non-static nested class need reference to the outer class

		* Non-static nested class can access both static and non-static members of the outer class but static class can access only static members of the Outer class.

		*********************************

		Behavior in thread???????????//

### Static in Polymorphsim
	
	1-In overriding concept : As static method is not associated with object of the class. It is associated with the class itself .So static methods cannot be overriden.

	Example :
	class Parent{
		static void m1() {
			System.out.println("m1 called from Parent");
		}
		public void m2() {
			System.out.println("m2 called from Parent");
		}
	
	}
	class child extends Parent{
		static void m1() {
			System.out.println("m1 called from Child");
		}
		public void m2() {
			System.out.println("m2 called from Child");
		}
	}
	public class OverrideStaticDemo {
		public static void main(String[] args) {
			Parent obj = new child();
			obj.m1();
			obj.m2();
		}
	}

		Output:

		m1 called from Parent
		m2 called from Child

	2-Overloading Concept:

	Yes static methods can be overloaded because static is related to class. They are resolved at compile time not run time.Overloading happens at compile time,so the static methods can be overloaded.

	Example:

	public class StaticOverloadDemo {

		
		static void m1() {
			System.out.println("m1() without parameter");
		}
		
		static void m1(String a) {
			System.out.println("m1() with parameter "+a);
		}
		public static void main(String[] args) {
			// TODO Auto-generated method stub
			m1();
			m1("Priyanka");
			

		}

	}

	Output:
	m1() without parameter
	m1() with parameter Priyanka

### Static in encapsulation:

	- making variable as static violets the encapsulation because then u can use the vaiable without using getters and setters.

	

