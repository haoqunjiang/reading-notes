- aliases & shorthands

        CoffeeScript    Equivalent
        ==              ===
        is              ===
        !=              !==
        isnt            !==
        not             !
        unless          if not
        until           while not
        and             &&
        or              ||
        true, yes, on   true
        false, no, off  false
        @, this         this
        ::              prototype

- comments

    + `# a comment`
    + `###`  
    `multiline comment`  
    `###`

- existential operator

    + `?`
    + `?=` equals to `||=` except that `?=` only checks `undefined` and `null`

- functions

    + `->`
    + `=>` always bind `this` to local context
    + `(arg1, arg2="default value", other...) ->`
    + `do ->` immediate function

- function call

    + `alert a`
    + `alert inspect(a)`
    + `noargument()`

- object literals

    + `obj1 = { one: 1, two: 2}`
    + `obj2 = one: 1, two: 2`
    + 
            obj3 =
                one:1
                two:2 

- arrays

    + `array1 = [1, 2, 3]`
    + 

            array2 = [
              1
              2
              3
            ]

    + `array3 = [1,2,3,]`

- if/else

    + `mood = greatlyImproved if singing`
    + `date = if friday then sue else jill`
    + `alert "It's cold!" if heat < 5`

- swicth

    + `switch... when... when... else...`
    + no fall-through
    + can also be used without a control expression (as a cleaner alternative to if/else chains)

- loops and comprehensions

    + `for element, index in array` not fit for strings (still need indexOf function)
    + `for key, value of object`
    + `for own key, value of object`
    + `when`
            foods = ['broccoli', 'spinach', 'chocolate']
            eat food for food in foods when food isnt 'chocolate'

- ranges

    + `[0..10]` inclusive
    + `[0...10]` exclusive
    + ranges with prefixes will be sliced (also fit for strings)

            numbers = [0..9]
            numbers[3..5] = [3, 4, 5]

- classes

    + `constructor`
    + 
            class Animal
                constructor: (name) ->
                @name = name
        
        equals to

            class Animal
                constructor: (@name) ->

    + static methods
        * `this.methodName = (args) ->`
        * `@methodName: (args) ->`
    + `extends`
    + `super()`

- destructuring assignment

    + `[theBait, theSwitch] = [theSwitch, theBait]`
    + `can be used with any depth of array and object nesting`

- chained comparison

    + `200 > cholesterol > 60`

- strings

    + interpolation for double quoted strings only, using `#{ ... }`
    + multiline strings are allowed
    + block strings quoted by `"""` or `'''`, the former one allows interpolation,
    and indentation level is maintained throughout.

- block regular expression

    + ignore internal whitespace and can contain comments and interpolation.
    + delimited by `///`
    + 
            OPERATOR = /// ^ (
                ?: [-=]>            # function
                | [-+*/%<>&|^!?=]=  # compound assign / compare
                | >>>=?             # zero-fill right shift
                | ([-+:])\1         # doubles
                | ([&|<>])\2=?      # logic / shift
                | \?\.              # soak access
                | \.{2,3}           # range or splat
            ) ///