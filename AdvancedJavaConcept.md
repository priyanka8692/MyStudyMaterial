## Exceptions
   Uwanted or unexpected event that happens during the ececution of program that is run-time
   that disrupts the normal flow of the program.


## throw
   It is used to throw the Exception.It is used in method implementation.We can throw only one Exception at a time.

## throws
   It is used to declare exception.This is done with method's signature.Multiple exceptions can be declared using throws.

## catch
   Catch is used to catch the exception which is thrown in our program.
   -Every try should have either catch or finally block after it. 
   -One try can have multiple catch also.
   -Order for catch:
      * First subclass Exception block should come and then the super class exception block.
      * Different child not belonging to the same parent exception class can come in any order.

      Example:

   public class CatchDemo {
      

      public static void main(String[] args) {
         // TODO Auto-generated method stub
         
         int[] arr = new int[4];
         try {
            int i = arr[4];
            System.out.println("Inside try block");
         }
         catch(ArrayIndexOutOfBoundsException e) {
            System.out.println("array index out....");
         }
         catch(ArithmeticException e) {
            System.out.println("error");
         }
      }
   }
   Output:
   array index out....

## how to create exception
## how to create error


## diff between exception and error
   ERROR
   -Error is a serious problem that application should not try to catch.
   -Error along with RunTimeException and their subclasses are the unchecked exception.

   EXCEPTION
   -There are the situation which be handled using try and catch 
   
## handled exception vs unhandled exception
   -These are the checked and unchecked Exception

## Checked expcetion, unchecked exception Difference
   -Checked Exception are the one which occur at compile time
   -If any method throw checked exception then method must either handle it or must specify using throws keyword.

## how to create checked exception

   -Examples:
      * IOException
      * SQLException
      * ClassNotFoundException

      Example:
      import java.io.FileInputStream;
      import java.io.IOException;

      public class CheckedException {

         public static void main(String[] args) throws IOException{
            // TODO Auto-generated method stub
            FileInputStream dis = null;
            dis = new FileInputStream("d:/dkkdk.txt");
            int k ;
            while((k=dis.read())!=-1) {
               System.out.println((char)k);
            }
         }
      }

      Output:
      File Content displayed on the screen.

## how to create unchecked exception

   -Unchecked Exception are the one which occur at runtime.
   -Even if you do not declare them it would not give any compilation error.
   -Example:
      * ArrayIndexOutOfBoundsException
      * NullPointerException
      * IllegalArgumentException
      * ArithmeticException

      Example:
      class Example {  
         public static void main(String args[])
         {
         int num1=10;
         int num2=0;
         /*Since I'm dividing an integer with 0
          * it should throw ArithmeticException
               */
         int res=num1/num2;
         System.out.println(res);
         }
      }

      The above program would give any compilation errror when you will compile. It will give error at run time.