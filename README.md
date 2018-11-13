# sciter-tiscript-intellisense
Set your ide to detect tiscript as typescript and stick the stubs file somewhere in your repo.

Note that methods/properties which return multiple values are not 100% accurate as typescript doesn't support that. In those places I have it typehinted to return: MultipleReturnValue

If you're using Intellij Idea Ultimate (which supports typescript) it's helpful to empty the lib.es6.d.ts definition file in C:\Program Files\JetBrains\IntelliJ IDEA 2018.1.6\plugins\JavaScriptLanguage\jsLanguageServicesImpl\external\lib.es6.d.ts
This way you won't have any es6/typescript intellisense confusing you.
You can also get <script type="text/tiscript"> defined as typescript in intellij by following: https://intellij-support.jetbrains.com/hc/en-us/community/posts/207004385-How-do-I-highlight-my-inline-script-with-type-text-javascript-lazy-as-if-it-were-javascript-

Notes:

I haven't added stubs for the following (feel free to add a PR):
- Behavior
- Graphics
- Image
- Sciter
- DataSocket
- WebSocket
- Tokenizer

tiscript class inheritance and function declaration breaks typescript syntax, so you won't get intellisense on any custom classes you create

Try to use typescript compatible functions E.G.
```
    self.select() instead of self.$()
    self.ready = function() {} instead of function self.ready() {}
    dip(100) instead of 100dip
    function hashType(type) {return eval(type);} hashType("#view") instead of #view
    etc
```
