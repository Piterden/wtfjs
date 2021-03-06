This is another case of an accidental global:

<pre lang="javascript">
    var a = 1
        b = 1;

    (function(){
        var a = 2
            b = 2;
    }())

    console.log(a); // prints 1
    console.log(b); // prints 2
</pre>

While debugging, one might be looking only at the “b” statements, but the
problem is the missing comma after “a”. Since JavaScript has “automatic
semicolon insertion” for some statements like “var”, a semicolon gets inserted
after “a = 2”, and variable “b” gets declared as a global!

— [@jfparadis](http://twitter.com/jfparadis)!
