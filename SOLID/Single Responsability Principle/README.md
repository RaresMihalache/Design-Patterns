# Violation of SRP (Single Responsability Principle): 👎

![Screenshot_17](https://github.com/RaresMihalache/Design-Patterns/assets/31708451/dc3f51a1-d792-488d-90a5-90a5d9d19b0c)

In the above example, our `UserController` class is doing multiple things:
* it is getting the request and `creating a User object` from that request.
* it is `validating` the object.
* it is `storing` the object in a HashMap.

This is **BAD**, because there are multiple reasons for this `UserController` class to change.
1. If we put a new field in the `User` class, we have to change `UserController` because the validation needs to change too.
2. If the way we store our `User` object changes (Eg: we start using an actual DB), our `UserController` needs to change too.

And so on...

# Refactoring: 👍

We have to identify which are the responsabilities that our class shall not have and delegate those responsabilities to other classes. For example, `validation` is a responsability that `UserController` class shall not handle. To solve this issue we can create a new `UserValidator` class

Also we need to have a different class for managing the persistence. We will create a new `UserPersistenceService` class to do this.

![Screenshot_18](https://github.com/RaresMihalache/Design-Patterns/assets/31708451/c0fa7db7-67aa-4cdf-af23-839d1298e852)
