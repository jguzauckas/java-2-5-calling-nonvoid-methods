# Calling a Non-`void` Method

We now know how to use `void` methods with or without parameters, but this is a small subset of the possible behaviors objects could have. The overwhelming majority of methods `return` information, whereas `void` explicitly return nothing. Let's investigate what this means.

---

## `return`

While our `void` methods would change the control flow of our program by moving elsewhere in the code, and then returning to where they started, non-`void` methods will move the control flow and transmit information back to where they started. Here is an example from `Person.java` of a `void` and non-`void` method:

```java
public void sayAge(){
    System.out.println(age);
}

public int getAge(){
    return age;
}
```

The first method here we should be familiar with from previous sections; when we call `sayAge` it just prints out the age of the `Person` object we call it from. The second method has a couple of key differences. In the method signature, the keyword `void` has been replaced with the data type `int`, meaning that this function intends on sending an `int`-type value back when it is done. In order to send a value back, our method has to use the keyword `return`, followed by the value to send back, which in this case is the value of the `age` variable. It is critical that the value you return matches the type of the method signature, in this case the value of `age` is an `int`, so we are all set.

This is a classic example of a **getter** method, where we just want to know a specific piece of information of an object. Just like our parameters for methods, this works by **call by value**, where the return statement sends a copy of the value, not the original value, which in this case keeps our age variable safe from any changes.

We can also have non-`void` methods that take parameters as well, giving us a lot more options. Here is an example from the `Person.java` class:

```java
public int numYearsUntil(int y){
    return y - age;
}
```

This method takes a number of years as a parameter and returns the number of years until the `Person` object is that age. Now that we know what these methods look like, let's learn how to use them.

---

## Calling a Non-`void` Method

While not explicitly more useful, we can call non-`void` methods exactly the way we would call `void` methods. Here is an example from `NotesMethodCall1.java`:

```java
Person person1 = new Person(25);
person1.getAge();
person1.numYearsUntil(30);
```

This program produces no warnings or errors and can be run just fine, producing nothing as its output. The issue here is that we aren't utilizing the fact that these methods are returning information to us to use. This is the equivalent of writing in a value or creating an object and not saving them to a variable to use later on. We can easily remedy this by at least putting them in `print` statements, like we do here in `NotesMethodCall2.java`:

```java
Person person1 = new Person(25);
System.out.println(person1.getAge());
System.out.println(person1.numYearsUntil(30));
```

When we run this program, we get a much more interesting output:

```
25
5
```

So for our purposes, we can envision that each of these non-`void` method calls can be replaced with the value sent back. We can do anything we want with these values: save them to variables, print them out, do operations on them, etc.

---

## Setter Methods

Earlier we looked at the idea of a **getter** method, which gives us access to the variables an object has. To match that, we will often have **setter** methods, which allow us to modify the value of those same variables. The names of the methods will often have `get` and `set` in them to help differentiate. Here is an example pair for the `age` variable in the `Person.java` file:

```java
public int getAge(){
    return age;
}

public void setAge(int a){
    age = a;
}
```

Between these two, we can really accomplish anything we need, hence why they are paired together!

---

## Assignment

Now that you have gone through the notes for this section, you can check out the `Try.md` and `Try.java` files to try a short assignment using this material.
