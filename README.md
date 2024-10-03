# Typescript-Interview-questions

# TypeScript Interview Questions and Answers

1. **What is TypeScript?**
   - TypeScript is a strongly typed programming language that builds on JavaScript by adding static types. It compiles down to plain JavaScript and provides tools for catching errors early in development.

2. **How does TypeScript differ from JavaScript?**
   - TypeScript adds static typing, interfaces, and additional features not present in JavaScript. JavaScript is dynamically typed, while TypeScript allows developers to specify types for variables, functions, and objects to catch errors before runtime.

3. **What are the advantages of using TypeScript?**
   - The main advantages include early error detection through static typing, enhanced code readability, better tooling (like autocompletion and refactoring), and more maintainable code in large projects.

4. **What is type inference in TypeScript?**
   - Type inference is when TypeScript automatically determines the type of a variable based on its initial value. For example, if you declare `let count = 5`, TypeScript will infer that `count` is of type `number` without needing an explicit type annotation.

5. **Explain the concept of "interfaces" in TypeScript.**
   - Interfaces define the shape or structure of an object. They specify what properties and methods an object should have, along with their types, but they do not implement any functionality. This helps ensure consistency across different objects.

6. **How do you define a union type in TypeScript?**
   - A union type allows a variable to hold one of multiple types. You define it using the pipe (`|`) symbol, like `let value: string | number`. Here, `value` can be either a string or a number.

7. **What is an enum in TypeScript?**
   - An `enum` is a way to define a set of named constants, which can be either numeric or string values. It helps in making the code more readable and allows you to refer to values using descriptive names instead of numbers or strings.

     ```typescript
     enum Color { Red, Green, Blue }
     let c: Color = Color.Green; // c is now 1

 8. **How do you define optional properties in TypeScript?**  
    - Optional properties are defined using a ? after the property name in an interface. This indicates that the property is not required, and the object can be created without it.
   
      ```typescript
      interface Person {
       name: string;
       age?: number; // optional
      }

9. **What is the difference between interface and type in TypeScript?**
   - Both interface and type are used to define the shape of data. However, interface is used primarily for object structures, and it can be extended or implemented in classes. type can be used for creating more complex types like unions, intersections, or primitives, but it cannot be implemented by classes.

10. **How does TypeScript handle `null` and `undefined`?**

   - TypeScript treats `null` and `undefined` as distinct types. When the `strictNullChecks` option is enabled, `null` and `undefined` must be explicitly handled. This means they cannot be automatically assigned to other types like `string` or `number`. For example, a variable declared as `string` cannot hold a `null` or `undefined` value unless explicitly allowed.
   
        ```typescript
        let name: string = "John";
        name = null; // Error when `strictNullChecks` is enabled.

11.  **What is the difference between `interface` and `type` in TypeScript?**

     - Both `interface` and `type` are used to define the shape of data. However, `interface` is used primarily for object structures, and it can be extended or implemented in classes. `type` can be used for creating more complex types like unions, intersections, or primitives, but it cannot be implemented by classes.

12.  **What are generics in TypeScript?**

     -   Generics allow you to create reusable components, functions, or classes that work with different data types while maintaining type safety. They act as placeholders for types, which are determined when the component is used.

          ```typescript

         function identity<T>(arg: T): T {
          return arg;
          }

13.  **How do you create a custom type in TypeScript?**

     -   You use the `type` keyword to define custom types. This can be useful for creating type aliases for more complex types or unions.

      ```typescript

      type Point = { x: number, y: number };

14.  **Explain the `any` type in TypeScript.**

     -   The `any` type can hold any kind of value, effectively opting out of type checking. While it provides flexibility, using `any` removes the benefits of static typing and should be avoided in favor of more specific types whenever possible.
15.  **What is the `never` type in TypeScript?**

     -   The `never` type represents values that never occur, such as functions that never return (like those that throw errors or run indefinitely). It indicates unreachable code paths.

       ```typescript
        
       function error(message: string): never {
         throw new Error(message);
       }

16.  **How can you extend interfaces in TypeScript?**

     -   You can use the `extends` keyword to create a new interface that builds on an existing one. This allows you to add or modify properties without repeating the entire structure.

       ```typescript

       interface Animal {
         name: string;
        }

        interface Dog extends Animal {
         breed: string;
        }

17.  **What is `readonly` in TypeScript?**

     -   The `readonly` modifier makes a property immutable, meaning it can be assigned only once (at the time of initialization) and cannot be changed afterward. It's useful for defining constants within objects.

     ```typescript
 
     interface Car {
      readonly make: string;
      }

18.  **How do you declare a tuple in TypeScript?**

     -   A tuple is an array with a fixed number of elements, where each element can have a different type. You declare it by specifying the types of each element in the array.

     ```typescript

      let tuple: [string, number];
       tuple = ["hello", 10];

29. **What are decorators in TypeScript?**

    -   Decorators are special functions that can be attached to classes, methods, properties, or parameters to modify their behavior. They are typically used in frameworks like Angular for dependency injection and metadata annotations.
       
20. **How do you define default parameters in TypeScript?**

    -   Default parameters in functions are defined by providing a default value in the function signature. If no argument is passed for that parameter, the default value will be used.

    ```typescript

    function greet(name: string = "Guest") {
      return `Hello, ${name}`;
     }

21. **How does TypeScript support modules and namespaces?**

    -   TypeScript supports ES6-style modules using `import` and `export` to organize code into reusable pieces. Additionally, namespaces are used to group related code together, which is helpful for avoiding name collisions.

    ```typescript

    // file.ts
    export const pi = 3.14;

    // main.ts
    import { pi } from './file';
