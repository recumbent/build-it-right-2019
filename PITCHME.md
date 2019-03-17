# Why Elm Makes me Happy!

---

## What is Elm?

"A delightful language for reliable webapps."

Notes:
- First things first, what is Elm?
- Elm describes itself as "A delightful language for reliable webapps" - well beging delighted and producing reliable code are grounds for happiness, but even given my time limit I think its worth going a bit deeper, so why does it make me happy

---

## Its Not JAVASCRIPT

Notes:
- Because its not Javascript...
- Actually that's too easy - and its not really helpful. Javascript is an immensley capable language and its ubiquity makes something like elm possible - it would be better to talk about what elm is rather than what its not, so elm is three things

---

## Elm Language:

* Strictly Typed
* Functional
* Only supports Pure Functions
    * NO SIDE EFFECTS!

Notes:

- The first thing Elm is is a language
- Its Strictly typed - this makes the compiler your friend and there is sufficent depth in the Elm type system to be interesting (?? pick this up where) withou being overwhelming
- Only supports pure functions - by which we mean that for any given input a function will always return the same output and there are _no side effects_ - this makes functions very testable and helps in reasoning about them
- At this point you may have notice a small problem - user interaction, rendering HTML etc is a side effect and user input is non deterministic, if all our functions are pure how do we create a user interface?
- For this we need

---

* TEA - Image of Tea Service

Notes:
- TEA!

---

**T**he
**E**lm
**A**rchitecture

* Model -> View -> Update

Notes:
- In this case The Elm Architecture, which is the Model, View, Update pattern - which evolved in Elm and is the inspiration for Redux and by extension a lot of contemporary thinking
- Pragmatically this provides a framework in which Elm runs your pure functions and handles the messy bits

---

* Model
* View: `view : Model -> Html Msg`
* Update: `update : Msg -> Model -> (Model, Cmd Msg)`


Notes:

- In a bit more detail, the model defines the current state
- view is a function that takes the model and translates it into the HTML to be displayed
- update is a function that takes a message - which is an algebraic data type (Elm name here) that is defined as part of the application and specfies all the events that can occur in the application - and the model and returns not only the model after the action required by the message has been applied but also a command - which might be none or might be say an http request along with the message (from our defined list) to return when that request completes
- And this is how we square the circle of no side effects - the code I write is pure, I can reason about it, I can test it. External events - things that are non-deterministic - are handled by the runtime framework.

---

# So what's the third thing?

Notes:

- You may recall that I said Elm was 3 things - I've described the first two, the Language and the Framework the third is

---

# Philosophy

Notes:

- Philosophy
- It seems to me that the creator of the language and the community growing around Elm have a philosophy that defines the approach both to creating the language and to writing applications, this starts with the notion that there should be one way to do things and so long as that works well there's no need to add more. That the type system and the compiler should make adding to or refactoring your application an easy and comfortable experience. And extends to the functional programming ideal of making invalid states unrepresentable in your model (which sits nicely with making changes to your code safe and easy).

