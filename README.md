# Protected Variability
Protected Variability is a design principle in GRASP (General Responsibility Assignment Software Patterns) that aims to encapsulate and protect areas of variability in a software system.


# Purpose: 
The primary purpose of Protected Variability is to:


1. Isolate changes: Minimize the impact of changes on other parts of the system.
2. Improve maintainability: Make it easier to modify or extend the system.
3. Reduce coupling: Decrease dependencies between classes.

# Key Elements:


1. Variation Point: Identify areas of variability in the system.
2. Protection Mechanism: Introduce a protection mechanism (e.g., interface, abstract class) to encapsulate variability.


# Benefits:


1. Improved maintainability: Changes are localized, reducing the risk of ripple effects.
2. Increased flexibility: New variations can be added without modifying existing code.
3. Reduced coupling: Classes are decoupled, making it easier to modify or replace individual components.

# Without Protected Variability:



public class PaymentGateway {
    public void processPayment(String paymentMethod, double amount) {
    
        if (paymentMethod.equals("creditCard")) {
            // Credit card-specific logic
        } else if (paymentMethod.equals("paypal")) {
        
            // PayPal-specific logic
        } else {
            // Bank transfer-specific logic
        }
    }
}



# With Protected Variability:
check code and run
# Explanation Of Code

without Protected Variability, the PaymentProcessor class has a complex conditional statement to handle different payment gateways. This makes it difficult to add new gateways without modifying existing code.


 By applying Protected Variability, we:


1. Introduced an abstract PaymentProcessor class with an abstract processPayment method.
2. Created concrete processor classes (e.g., PayPalProcessor, StripeProcessor) that implement the processPayment method.
3. Introduced a PaymentGateway class that delegates payment processing to the concrete processor classes.

 Benefits:


1. Encapsulated variability: Payment gateway-specific logic is isolated in separate classes.
2. Improved maintainability: Adding new payment gateways requires only creating a new concrete processor class.
3. Reduced coupling: PaymentGateway class is decoupled from payment gateway-specific logic.




