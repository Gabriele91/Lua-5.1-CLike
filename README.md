Lua-5.1-CLike
=============
 This is a modified version of lua with a C-like syntax, I made some little changes to the parser.

* New if statement:

  ```BNF
  'if' '(' <bool exp> ')' '{' <statements> '}' {'elif' '{' <statements> '}' } ['else' '{' <statements> '}']
  ```

* New for statement:
  ```BNF
  'for' .... '{' <statements> '}'
  ```

* New while statement:

  ```BNF
  'while' '(' <bool exp> ')' '{' <statements> '}'
  ```

* New function statement:

  ```BNF
  'def' [name] '(' <args> ')'  '{' <statements> '}'
  ```
* Not equal operator is changed in:

  ```BNF
  '!='
  ```
* Changed 'repeat until' statement  in 'do while' statement:

  ```BNF
  'do' '{' <statements> '}' while '(' <bool exp> ')'
  ```

Examples:
=============

  * Lua-CLike:
  ```Javascript
  if(a=="x")
  {
      def foo()
      {
         print("foo")
      }
      for i=1,200
      {
         foo()
      }
  }
  elif(a!="b")
  {
     a=def(){ print("NONE") }
     while ( true )
     {
       a()
       break;
     }
  }
  else
  {
     c=(def(){return 1})()
     do { print"hello" } while (true)
  }
  ```

  * LUA:

  ```LUA
  if  a=="x"
  then
        function foo()
           print("foo")
        end
        for i=1,200
        do
           foo()
        end
   elseif a~="b"
   then
      a=function() print("NONE") end
      while true  
      do
         a()
         break;
      end
  else
      c=(function() return 1 end)()
      repeat  print"hello" until false
  end
  ```



Lua-5.1
=============
 * Readme
  ------------
  See INSTALL for installation instructions,
  see HISTORY for a summary of changes since the last released version.

  What is Lua?
  ------------
  Lua is a powerful, light-weight programming language designed for extending
  applications. Lua is also frequently used as a general-purpose, stand-alone
  language. Lua is free software.

  For complete information, visit Lua's web site at http://www.lua.org/ .
  For an executive summary, see http://www.lua.org/about.html .

  Lua has been used in many different projects around the world.
  For a short list, see http://www.lua.org/uses.html .

  Availability
  ------------
  Lua is freely available for both academic and commercial purposes.
  See COPYRIGHT and http://www.lua.org/license.html for details.
  Lua can be downloaded at http://www.lua.org/download.html .

  Installation
  ------------
  Lua is implemented in pure ANSI C, and compiles unmodified in all known
  platforms that have an ANSI C compiler. Under Unix, simply typing "make"
  should work. See INSTALL for detailed instructions.

  Origin
  ------
  Lua is developed at Lua.org, a laboratory of the Department of Computer
  Science of PUC-Rio (the Pontifical Catholic University of Rio de Janeiro
  in Brazil).
  For more information about the authors, see http://www.lua.org/authors.html .
