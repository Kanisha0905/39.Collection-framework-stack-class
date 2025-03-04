# 39.Collection-framework-stack-class
COLLECTION FRAMEWORK CLASS STACK 

import java.util.Stack;

public class VerySimpleCalculator {
    public static int evaluateExpression(String expression) {
        Stack<Integer> stack = new Stack<>();

        for (char ch : expression.toCharArray()) {
            if (Character.isDigit(ch)) {
                // If the character is a digit, push the corresponding integer to the stack
                stack.push(Character.getNumericValue(ch));
            } else if (ch == '+') {
                // If the character is '+', pop two operands, add them, and push the result back to the stack
                int operand2 = stack.pop();
                int operand1 = stack.pop();
                stack.push(operand1 + operand2);
            } else if (ch == '-') {
                // If the character is '-', pop two operands, subtract them, and push the result back to the stack
                int operand2 = stack.pop();
                int operand1 = stack.pop();
                stack.push(operand1 - operand2);
            }
        }

        // The result should be the only element left in the stack
        return stack.pop();
    }

    public static void main(String[] args) {
        String expression = "3 + 4 - 2";
        int result = evaluateExpression(expression);
        System.out.println("Result of the expression '" + expression + "': " + result);
    }
}

OUTPUT:
Result of the expression '3 + 4 - 2': 5
