---
layout: post
title: "It's all about complexity"
date: 2026-07-25
categories: software-engineering
---

Ever since software was first written, the biggest problem that engineers are facing is **complexity**, leading to both developer and user frustration due to an insane amount of bugs, managers going crazy over users leaving their platform, and so on.

## But what is complexity?

According to John Ousterhout in *A Philosophy of Software Design*, complexity is **anything related to a software that makes its structure hard to understand and modify**. Complexity manifests itself in three different ways:
* **Change amplification**: A seemingly simple change requires code modification in many different places (often unrelated).
* **Cognitive load**: How much the engineer must know before doing their task (if the user must navigate through all the codebase to change something the system is complex).
* **Unknown unknowns**: If it's not crystal clear what do you need to do to complete the task.

## Fighting complexity

Since we've been writing code, some people are trying to create techniques to do it. Some of them include:

1. Writing clean names: your modules must have clean names. Example: `num_days` is way better than `n`. Don't hold back on typing.
2. Building deep modules: your interface must hide the complexity of implementation of that module.
3. Building general purpose modules: build modules that solve multiple related problems without adding interface complexity.
4. Do common uses default: if your module is always used with some parameter, make it default so the caller doesn't need to worry about that.
5. Avoid pass through values: if you're passing a value through your modules that won't be used, except on the final "cascade", you must find a way to deal with that. Some of them are [Dependency Injection][dependency-injec], [Global Shared State][current-attributes].

> **What is a module?** 
> A module is any unit of code with an interface and an implementation—it can be a class, a function, a struct, or a system package/module.

## Conclusion

Unfortunately, complexity is inevitable. Most of the things we build are complex by nature, but we need to try to make it as simple as possible. Otherwise, we're getting trapped by its effects. 

Complexity is incremental, it means that small mistakes that you make every day will come back to haunt you in the future, like a frog in the boiling water.

You must be thinking about your code all the time, asking yourself questions like "Can't I make it simple?", "What if I merge these two related functions into one?", "Is this function parameter really necessary or should I omit it?". 

Remember: your written code is not written on rocks, so if you see an opportunity of improvement, do it!

#### References

* *A Philosophy of Software Design* by John Ousterhout
* *Pragmatic Programmer* by Andy Hunt and Dave Thomas

[dependency-injec]: https://en.wikipedia.org/wiki/Dependency_injection
[current-attributes]: https://api.rubyonrails.org/classes/ActiveSupport/CurrentAttributes.html