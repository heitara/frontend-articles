# [Rust](https://www.youtube.com/watch?v=5C_HPTJg5ek)
> Rust is fast and memory-efficient static compiled language with rich type system and ownership model. It can be used to power preformance critical services while guaranteeing memory and thread safety, empowering developers to debug at compile-time.

- Memory managment in Rust:
 1. Rust has fine-grain memory managment but is automatically managed once created.
 2. When we allocate memory we can decide when to free it.
 3. Each variable has a scope it is valid for and if it gets out of scope, it gets automatically deallocated.
 4. Each program is allocated memory from the operating system.
 5. Rust has shared memory where we can have a reference piece of data.

- Memory types:
  - Heap memory -> All the dynamic data is stored at this place.
  - Stack memory -> All values are allocated on the stack and includes structures and pointers to dynamic data.
#

**Concept of Ownership** -> When you own something you can decide to pass it to someone else.
<br>**Concept of Borrowing** -> Owned values can be borrowed to allow usage for certain period of time. The `&` sign represent the borrowed reference. Borrowed values have a lifetime and are valid for that time only.<br> While there is an active `borrow` we cannot transfer ownership! 

#
**Advantages when using rust:**
- Quick debugging and testing.
- Support of more complex code as comapred to other languages.
- Enabled corss-patform development.
- Ease of integration.
- Rust is safer tha other programming languages.
