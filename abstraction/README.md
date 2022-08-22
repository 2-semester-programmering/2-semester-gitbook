# Abstraction

### Abstraction in Java

**Abstraction** is a process of hiding the implementation details and showing only functionality to the user.

Another way, it shows only essential things to the user and hides the internal details, for example, sending SMS where you type the text and send the message. You don't know the internal processing about the message delivery.

Another example is the break pedal of a Car. If an animal jumps in front of your car you hit the break pedal, and you do not have to think about how the computer in the car interpret your push to the pedal and after that activates the breakpads on the wheels.&#x20;

The pedal is an abstraction, it hides the technical details and gives us a simple an easy to use interface to the cars breaking system.&#x20;

Abstraction lets you focus on **what the object does** instead of **how it does it**.

#### Ways to achieve Abstraction in Java

There are two ways to achieve abstraction in java

1. Abstract class (0 to 100%)
2. **Interface (100%) - the one we will focus on**

## Client code / Library Code

When we work with the concept of abstraction it is good to think of the code you are writing as either Client code or Library Code.  In relation to the examples above, **Client code** would be the break pedal or the SMS interface. It is easy and simple to use, and we dont need to know how it is programmed. **Library code** is then the actual code with the details.&#x20;

A little naive but descriptive example could look like this:

<pre class="language-java"><code class="lang-java">// Library Code
<strong>class Car {
</strong>    private int speed;
    public void accelerator(int speed){
        this.speed = speed;
    }
    public void breakPedal(){
        this.speed = speed;
    }
}</code></pre>

```java
// Client Code
class Main{
    public static void main(String[] args) {
        Car bmw = new Car();
        bmw.accelerator(100);  // Speed up car
        bmw.breakPedal();  // stop car
    }
}
```
