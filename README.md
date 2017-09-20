# LOON
Language of Object Notation. A language designed specifically for constructing and working with JSON data.

With the increasing popularity of JSON as a format for application data transfers, LOON
can be seen as the ultimate tool for developers to take large data sets and craft them
into JSON without the need for standard libraries and clunky string conversions. The 
language will be the ultimate power tool for fast, simple modification of data sets.

Consider LOON to be the ideal hybrid between programming with JavaScript objects and maintaining
JSON format. The programmer can manipulate the JSON data as he or she likes, without ever needing to 
break its JSON format. 

**For example**, a Java program might take the following steps to work with JSON data:

1.) Read in the JSON as a string

2.) Import a library to recognize the string's JSON encoding and Map it to a defined Java object/a combination
of Maps and ArrayLists

3.) Manipulate the objects using native operations that can be performed on Java objects

4.) Use the imported library to map the Java object back to valid JSON data

LOON will eliminate the JSON-to-Native Object-to-JSON conversion process by allowing developers
to always be operating on valid JSON at all points in the programming cycle. This can be of great 
benefits to developers, who will be able to log their output at any given point of their code and
see if the JSON is being formatted properly.

One thing to note: we can ALWAYS add things on top/remove some elements of what I've 
described below - this is just a working outline!


LOON has the following **types**:


`int;`

`double;`

`char;`

`string;`

`bool;`

`object; //Container holding several key-value pairs`

`list; //Array with flexible length`

`pair; /*Key-value pair where value can be any of the above types. The key in a pair is always a string, LOON will handle the type conversion if it is not */`

`JSON; //Wrapper type that consists of a collection of pairs concatenated
      //Note: This type may not be necessary but may prove convenient`
      
      
**Language characteristics:**

*Strongly typed

*Should have input/output capabilities that it can:

    1.) Read in any type of file - this gives developers flexibility with what they want
    to mold into JSON
    
    2.) Writes JSON
        -- We could let it write different types (i.e. You just want to write one string value), up for discussion 


*Concatenating a variable of type JSON with a variable of type pair will yield type JSON
    i.e: 
    
        `JSON firstJSON = {"name": "Just Jack"}
        
        //pairs can either be declared...
        pair lName = <string, string>;
        
        //or defined and initialized
         pair agePair = <"age", 20>;
         
         //Concatenation
         JSON secondJSON = firstJSON + agePair;
         //secondJSON == {"name": "Just Jack", "age": 20}`
         
         
*Values of data fields can be accessed through dot notation - just like regular JSON!
    i.e.:
     
     `   //from the above
         string jacksName = firstJSON.name;
         //jacksName == "Just Jack"`    
                           
*We can implement a standard library of whatever size we like - however, I think the 
types themselves should be able to handle most operations that developers want to perform
on them


**Discussion Points:**

*We can also add many more operations to the JSON type than just the concatenation operation

*We may want to implement pointers into this language or we may not

*Allocation of storage for each of the types is another discussion

*Handling terminal arguments

*What the main() method looks like/what the program does first upon execution

*Many more!


**Three Address Code:**
*I can add some tomorrow, but this language is very simple to C or Java so it should
end up looking similar to the C function that we saw broken down into Three Address 
code as part of the second set of lecture notes  

**Sample program** - very simple, like the above code:
    
    int main(){
        JSON firstJSON = {"name": "Just Jack"}
        pair agePair = <"age", 20>;
        JSON secondJSON = firstJSON + agePair;
        //secondJSON == {"name": "Just Jack", "age": 20}
        
        //Outputs JSON to screen
        printJSON(secondJSON);
        return 0;
    }
   