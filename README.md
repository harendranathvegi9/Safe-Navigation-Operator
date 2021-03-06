# Safe Navigation Operator

This blog demonstrates the use of Safe Navigation Operator(?.)

**Safe Navigation Operator(?.)** is already present in other scripting languages i.e. `Groovy` and there it is known as
**Null-Safe Dereference**. First let us understand the scenario where it is useful.

We face a common error(`Cannot read property 'propertyName' of undefined`) a lot in **JavaScript**, if we try to
read property on a undefined object. i.e.

```JavaScript
var user;
console.log(user.name); // Uncaught TypeError: Cannot read property 'name' of undefined
```

To handle this error, we add check for **user** object, if user is defined then only we read the name i.e.:

```JavaScript
var user;
if (user) {
    console.log(user.name); // Uncaught TypeError: Cannot read property 'name' of undefined
}
```

In **AngularJS**, we write **JavaScript** into **HTML/View**. And in **AngularJS 1.X**, it silently fails, if user 
object is not defined and does not display anything.

```HTML
<div>
    User Details:
    Name: {{user.name}}
    Age: {{user.age}}
</div>  
```

But in **Angular2**, it will throw an error `Uncaught TypeError: Cannot read property 'name' of undefined`. So we have
to add extra check before reading the property from object:

```HTML
<div>
    User Details:
    Name: {{user && user.name}}
    Age: {{user && user.age}}
</div> 
```

So to facilitate this extra check **Angular2** has introduced **Safe Navigation Operator(?.)**. With (?.) our code will be smaller and
readable:

```HTML
<div>
    User Details:
    Name: {{user?.name}}
    Age: {{user?.age}}
</div>  
```

> `Safe Navigation Operator(?.)` is used to avoid error `Cannot read property 'propertyName' of undefined`. Typically 
when we have a reference of an object and we might need to verify that it is not **undefined** before accessing the 
property the object.


Follow Me
---
[Github](https://github.com/AmitThakkar)

[Twitter](https://twitter.com/amit_thakkar01)

[LinkedIn](https://in.linkedin.com/in/amitthakkar01)

[More Blogs By Me](http://amitthakkar.github.io/)