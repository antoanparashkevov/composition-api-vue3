# composition-api-vue3
Replacing Options API with Composition API


The Composition API gives us a different way of building our components.

The JavaScript code that is written changes in the Composition API comparing with the Options API.

We might face two main issuies when building bigger Vue Apps with Options API.
- Code that belongs together logically is split up across multiple options ( data(), methods:{}, computed:{}, watch:{} )
- Re-using logic across components can be tricky.

With the Composition API, we bundle our logic in a setup() method.
