# pug style guide

## ids before classes
```
// suggested
span#identifier.className

// avoid
span.className#identifier
```

## attributes
```
-- if multiple lines, closing parenthesis should be on own line, indented to match element indentation.
-- attributes should be alphabetized. special character order follows keyboard pattern
-- ~!@#$%^&*()[],0-9,a-z

// suggested
input(
    #reference,
    *ngIf="condition",
    (event)="handler",
    [bind]="variable",
    name="sample",
    type="text"
)

// avoid
input([bind]="variable",
    (event)="handler",
    name="sample, type="text")
```

## unnecessary divs, nesting
```
-- do not declare div elements if possible, use id or class notation instead
-- try to use block expansion (https://pugjs.org/language/tags.html#block-expansion) when possible
 
// suggested
.classDiv
    section
        p foo
        span bar
    section: p: span something inside
    
// avoid
div.classDiv
    section
        p
            span something something
