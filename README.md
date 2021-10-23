# CustonmCalculator
usingExceptionCases
package com.company;
import java.lang.Exception;
/* Exercise: Create a custom calender with following operations
1. + ->Addition
2. - ->Subtraction
3. * ->Multiplication
4. % ->Division
which throws the following exceptions;
1.Invalid input Exception ex:8&9
2.Cannot divide by 0 exception
3.Max Input exception if any of the input exception is greater than the 100000.
4.Max Multiplier Reached Exception-Don't allow any multiplication input to be greater than the 7000.
*/
class InvalidInputException extends Exception{
    @Override
    public String toString() {
        return "Cannot add 8 and 9";
    }

    @Override
    public String getMessage() {
        return "I am getMessage()";
    }
}
class CannotDivideByZeroException extends Exception{
    @Override
    public String toString()
    {
        return "Cannot divide by zero";
    }
    @Override
    public String getMessage()
    {
        return "I am getMessage()";
    }

}
class MaxInputException extends Exception{
    @Override
    public String toString() {
        return "input should not be more than 100000";
    }

    @Override
    public String getMessage() {
        return "I am getMessage()";
    }
}
class MaxMultiplierException extends Exception{
    @Override
    public String toString() {
        return "input should not be greater than 7000";
    }

    @Override
    public String getMessage() {
        return "I am getMessage()";
    }
}


    

 class CustomCalculator {
    double add(double a,double b)throws InvalidInputException,MaxInputException{
        if (a > 100000 || b > 100000) {
            throw new MaxInputException();

        }
        if(a==8||a==9)
        {
            throw new InvalidInputException();
        }
        return a + b;
    }

    double sub(double a,double b) throws MaxInputException {
        if(a>100000||b>10000)
        {
            throw new MaxInputException();
        }
        return a - b;
    }
    double mul(double a,double b)throws MaxInputException,MaxMultiplierException{
        if(a>7000||b>7000)
        {
            throw new MaxMultiplierException();
        }
        if(a>100000||b>100000)
        {
            throw new MaxInputException();
        }
        return a * b;
    }
    double divide(double a,double b) throws CannotDivideByZeroException,MaxInputException{
        if(a>100000||b>100000)
        {
            throw new MaxInputException();
        }
        if (b==0)
            throw new CannotDivideByZeroException();
        return a / b;
    }
    public static void main(String args[])throws InvalidInputException,CannotDivideByZeroException,MaxInputException,MaxMultiplierException
    {
        CustomCalculator c= new CustomCalculator();
      //  c.add(8, 9);
       // c.divide(6, 0);
        //c.divide(600000000, 40);
        c.mul(5, 9888);

    }
}
