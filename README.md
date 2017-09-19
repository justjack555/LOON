# LOON
Language of Object Notation. A language designed specifically for constructing and working with JSON data.

With the increasing popularity of JSON as a format for application data transfers, LOON
can be seen as the ultimate tool for developers to take large data sets and craft them
into JSON without the need for standard libraries and clunky string conversions. The 
language will be the ultimate power tool for fast, simple modification of data sets.

One thing to note: we can ALWAYS add things on top/remove some elements of what I've 
described below - this is just a working outline!


LOON has the following types:
`\n
int;
double;
char;
string;
bool;
object; //Container holding several key-value pairs
list; //Array with flexible length`

`
pair; //Key-value pair where value can be any of the above types \n
JSON; //Wrapper type that consists of a collection of pairs concatenated
      //Note: This type may not be necessary but may prove convenient`
      
Language characteristics:
*Strongly typed
*Should have input/output capabilities that it can:
    1.) Read in any type of file - this gives developers flexibility with what they want
    to mold into JSON
    2.) Writes JSON
        -- We could let it write different types (i.e. You just want to write one string value), up for discussion 
*Concatenating a variable of type JSON with a variable of type pair will yield type JSON
    i.e: 
        `JSON firstJSON = {"name": "Just Jack"}
         pair agePair = <"age", 20>;
         JSON secondJSON = firstJSON + agePair;
         //secondJSON == {"name": "Just Jack", "age": 20}`
*Values of data fields can be accessed through dot notation - just like regular JSON!
    i.e.: `//from the above
         string jacksName = firstJSON.name;
         //jacksName == "Just Jack"`                      
*We can implement a standard library of whatever size we like - however, I think the 
types themselves should be able to handle most operations that developers want to perform
on them

Discussion Points:
*We can also add many more operations to the JSON type than just the concatenation operation
*We may want to implement pointers into this language or we may not
*Allocation of storage for each of the types is another discussion
*Handling terminal arguments
*What the main() method looks like/what the program does first upon execution
*Many more!

Three Address Code:
*I can add some tomorrow, but this language is very simple to C or Java so it should
end up looking similar to the C function that we saw broken down into Three Address 
code as part of the second set of lecture notes  

Sample program - very simple, like the above code:
    
    int main(){
        JSON firstJSON = {"name": "Just Jack"}
        pair agePair = <"age", 20>;
        JSON secondJSON = firstJSON + agePair;
        //secondJSON == {"name": "Just Jack", "age": 20}
        
        //Outputs JSON to screen
        printJSON(secondJSON);
        return 0;
    }
   