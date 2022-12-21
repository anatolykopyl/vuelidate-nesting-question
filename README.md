# Vuelidate Nesting Question

How do you make a validator for a data structure with a field that has nested fields?

`App.vue` has a form with a Vuelidate validator. 
It consists of a name, an address and an optional second Address. 
Problem is that `useVuelidate` throws a typescript error on it's second 
parameter `userForm`.

```
Argument of type 'Ref<{ name: string; address: { city: string; street: string; }; secondAddress?: { city: string; street: string; } | undefined; }>' is not assignable to parameter of type '{ name: any; address: any; secondAddress: any; } | Ref<{ name: any; address: any; secondAddress: any; }> | ToRefs<{ name: any; address: any; secondAddress: any; }>'.
  Type 'Ref<{ name: string; address: { city: string; street: string; }; secondAddress?: { city: string; street: string; } | undefined; }>' is not assignable to type 'Ref<{ name: any; address: any; secondAddress: any; }>'.
```

This happens because the interface `UserForm` has `secondAddress` marked as 
optional.

## Question

How do you write the rules in this case, where the field with children is optional?
