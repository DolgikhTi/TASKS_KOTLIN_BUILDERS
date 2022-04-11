Function literals with receiver:

Learn about function literals with receiver.
You can declare isEven and isOdd as values that can be called as extension functions. Complete the declarations in the code.
___________________________________________________________________________________________________________________________________________________________________
String and map builders:

Function literals with receiver are very useful for creating builders, for example:
fun buildString(build: StringBuilder.() -> Unit): String {
    val stringBuilder = StringBuilder()
    stringBuilder.build()
    return stringBuilder.toString()
}
​
val s = buildString {
    this.append("Numbers: ")
    for (i in 1..3) {
        // 'this' can be omitted
        append(i)
    }
}
​
s == "Numbers: 123"
Implement the function buildMutableMap that takes a parameter (of extension function type), creates a new HashMap, builds it, and returns it as a result. Note that starting from 1.3.70, the standard library has a similiar buildMap function.
___________________________________________________________________________________________________________________________________________________________________
The function apply:

The previous examples can be rewritten using the library function apply. Write your implementation of this function named myApply.
Learn about the other scope functions and how to use them.
___________________________________________________________________________________________________________________________________________________________________
HTML builder:

1. Fill the table with proper values from the product list. The products are declared in 
 
data.kt.
 
2. Color the table like a chessboard. Use the 

getTitleColor() and getCellColor() functions. Pass a color as an argument to the functions

tr, td.  

Run the main function defined in the file 
demo.kt 
to see the rendered table.
___________________________________________________________________________________________________________________________________________________________________
Builders: how they work:

Answer the questions below
1. In the Kotlin code

tr {
    
    td {
        
        text("Product")
    }
    
    td {
        
        text("Popularity")
    }
}

td is:
a. a special built-in syntactic construct
b. a function declaration
c. a function invocation

2. In the Kotlin code

tr (color = "yellow") {
   
   td {
        
        text("Product")
    }
    
    td {
        
        text("Popularity")
    }
}

color is:
a. a new variable declaration
b. an argument name
c. an argument value

3. The block
{
    
    text("Product")
}

from the previous question is:
a. a block inside built-in syntax construction td
b. a function literal (or "lambda")
c. something mysterious

4. For the code

tr (color = "yellow") {
    
    this.td {
        
        text("Product")
    }
    
    td {
        
        text("Popularity")
    }
}
which of the following is true:
a. this code doesn't compile
b. this refers to an instance of an outer class
c. this refers to a receiver parameter TR of the function literal:

tr (color = "yellow") {
    
    this@tr.td {
        
        text("Product")
    }
}
___________________________________________________________________________________________________________________________________________________________________
Builders implementation:

Complete the implementation of a simplified DSL for HTML. Implement tr and td functions.
Learn more about type-safe builders.
