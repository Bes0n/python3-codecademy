## Classes
### Types
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Python equips us with many different ways to store data. A <code>float</code> is a different kind of number from an <code>int</code>, and we store different data in a <code>list</code> than we do in a <code>dict</code>. These are known as different <em>types</em>. We can check the type of a Python variable using the <code>type()</code> function.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">a_string</span> <span class="cm-operator">=</span> <span class="cm-string">"Cool String"</span>
<span class="cm-variable">an_int</span> <span class="cm-operator">=</span> <span class="cm-number">12</span>

<span class="cm-builtin">print</span>(<span class="cm-builtin">type</span>(<span class="cm-variable">a_string</span>))
<span class="cm-comment"># prints "&lt;class 'str'&gt;"</span>

<span class="cm-builtin">print</span>(<span class="cm-builtin">type</span>(<span class="cm-variable">an_int</span>))
<span class="cm-comment"># prints "&lt;class 'int'&gt;"</span></div></span></pre>
<p>Above, we defined two variables, and checked the <code>type</code> of these two variables. A variable's type determines what you can do with it and how you can use it. You can't <code>.get()</code> something from an integer, just as you can't add two dictionaries together using <code>+</code>. This is because those operations are defined at the <code>type</code> level.</p>
</div>

###### TASK

* <p>Call <code>type()</code> on the integer <code>5</code> and print the results.</p>

* <p>Define a dictionary <code>my_dict</code>.</p>

* <p>Print out the <code>type()</code> of <code>my_dict</code>.</p>

* <p>Define a list called <code>my_list</code>.</p>

* <p>Print out the <code>type()</code> of <code>my_list</code>.</p>

```python 
print(type(5))
my_dict = {}
print(type(my_dict))
my_list = []
print(type(my_list))
```

### Class
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>A <em>class</em> is a template for a data type. It describes the kinds of information that class will hold and how a programmer will interact with that data. Define a class using the <code>class</code> keyword. &lt;a href="<a href="https://www.python.org/dev/peps/pep-0008/#class-names&quot;">https://www.python.org/dev/peps/pep-0008/#class-names"</a> target="_blank", rel="noopener noreferrer"&gt;PEP 8 Style Guide for Python Code  recommends capitalizing the names of classes to make them easier to identify.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">CoolClass</span>:
  <span class="cm-keyword">pass</span></div></span></pre>
<p>In the above example we created a class and named it <code>CoolClass</code>. We used the <code>pass</code> keyword in Python to indicate that the body of the class was intentionally left blank so we don't cause an <code>IndentationError</code>. We’ll learn about all the things we can put in the body of a class in the next few exercises.</p>
</div>

###### TASK
<p>Define an empty class called <code>Facade</code>. We'll chip away at it soon!</p>

```python 
class Facade(object):
  pass
```

### Instantiation
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>A class doesn't accomplish anything simply by being defined. A class must be <em>instantiated</em>. In other words, we must create an <em>instance</em> of the class, in order to breathe life into the schematic.  </p>
<p>Instantiating a class looks a lot like calling a function.  We would be able to create an instance of our defined <code>CoolClass</code> as follows:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">cool_instance</span> <span class="cm-operator">=</span> <span class="cm-variable">CoolClass</span>()</div></span></pre>
<p>Above, we created an object by adding parentheses to the name of the class. We then assigned that new instance to the variable <code>cool_instance</code> for safe-keeping. </p>
</div>

###### TASK
<p>In <strong>script.py</strong> we see our <code>Facade</code> class from last exercise. Make a <code>Facade</code> instance and save it to the variable <code>facade_1</code>.</p>

```python
class Facade:
  pass

facade_1 = Facade()
```

### Object-Oriented Programming
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>A class instance is also called an <em>object</em>. The pattern of defining classes and creating objects to represent the responsibilities of a program is known as <em>Object Oriented Programming</em> or OOP.</p>
<p>Instantiation takes a class and turns it into an object, the <code>type()</code> function does the opposite of that. When called with an object, it returns the class that the object is an instance of.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-builtin">print</span>(<span class="cm-builtin">type</span>(<span class="cm-variable">cool_instance</span>))
<span class="cm-comment"># prints "&lt;class '__main__.CoolClass'&gt;"</span></div></span></pre>
<p>We then print out the <code>type() of cool_instance</code> and it shows us that this object is of type <code>__main__.CoolClass</code>. </p>
<p>In Python <code>__main__</code>  means "this current file that we're running" and so one could read the output from <code>type()</code> to mean  "the class <code>CoolClass</code> that was defined here, in the script you're currently running."</p>
</div>

###### TASK
* <p>In <strong>script.py</strong> we see <code>facade_1</code> from last exercise. Try calling <code>type()</code> on <code>facade_1</code> and saving it to the variable <code>facade_1_type</code>.</p>

* <p>Print out <code>facade_1_type</code>.</p>

```python 
class Facade:
  pass

facade_1 = Facade()
facade_1_type = type(facade_1)
print(facade_1_type)
``` 

### Class Variables
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>When we want the same data to be available to every instance of a class we use a <em>class variable</em>. A class variable is a variable that's the same for every instance of the class. </p>
<p>You can define a class variable by including it in the indented part of your class definition, and you can access all of an object's class variables with <code>object.variable</code> syntax.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Musician</span>:
  <span class="cm-variable">title</span> <span class="cm-operator">=</span> <span class="cm-string">"Rockstar"</span>

<span class="cm-variable">drummer</span> <span class="cm-operator">=</span> <span class="cm-variable">Musician</span>()
<span class="cm-builtin">print</span>(<span class="cm-variable">drummer</span>.<span class="cm-property">title</span>)
<span class="cm-comment"># prints "Rockstar"</span></div></span></pre>
<p>Above we defined the class <code>Musician</code>, then instantiated <code>drummer</code> to be an object of type <code>Musician</code>. We then printed out the drummer's <code>.title</code> attribute, which is a class variable that we defined as the string "Rockstar". </p>
<p>If we defined another musician, like <code>guitarist = Musician()</code> they would have the same <code>.title</code> attribute.</p>
</div>

###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>You are digitizing grades for <em>Jan van Eyck High School and Conservatory</em>. At <em>Jan van High</em>, as the students call it, <code>65</code> is the minimum passing grade.</p>
<p>Create a <code>Grade</code> class with a class attribute <code>minimum_passing</code> equal to <code>65</code>.</p>
</div>

```python
class Grade:
  minimum_passing = 65
```

### Methods
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p><em>Methods</em> are functions that are defined as part of a class. The first argument in a method is always the object that is calling the method. Convention recommends that we name this first argument <code>self</code>. Methods always have at least this one argument. </p>
<p>We define methods similarly to functions, except that they are indented to be part of the class.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Dog</span>():
  <span class="cm-variable">dog_time_dilation</span> <span class="cm-operator">=</span> <span class="cm-number">7</span>

  <span class="cm-keyword">def</span> <span class="cm-def">time_explanation</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-builtin">print</span>(<span class="cm-string">"Dogs experience {} years for every 1 human year."</span>.<span class="cm-property">format</span>(<span class="cm-variable-2">self</span>.<span class="cm-property">dog_time_dilation</span>))

<span class="cm-variable">pipi_pitbull</span> <span class="cm-operator">=</span> <span class="cm-variable">Dog</span>()
<span class="cm-variable">pipi_pitbull</span>.<span class="cm-property">time_explanation</span>()
<span class="cm-comment"># Prints "Dogs experience 7 years for every 1 human year."</span></div></span></pre>
<p>Above we created a <code>Dog</code> class with a <code>time_explanation</code> method that takes one argument, <code>self</code>, which refers to the object calling the function. We created a <code>Dog</code> named <code>pipi_pitbull</code> and called the <code>.time_explanation()</code> method on our new object for Pipi.</p>
<p>Notice we didn't pass any arguments when we called <code>.time_explanation()</code>, but were able to refer to <code>self</code> in the function body. When you call a method it automatically passes the object calling the method as the first argument.</p>
</div>

###### TASK 
* <p>At <em>Jan van High</em>, the students are constantly calling the school rules into question. Create a <code>Rules</code> class so that we can explain the rules.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Give <code>Rules</code> a method <code>washing_brushes</code> that returns the string .</p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">"Point bristles towards the basin while washing your brushes."</div></span></pre></div>

```python 
class Rules():
  def washing_brushes(self):
    return "Point bristles towards the basin while washing your brushes."
```

### Methods with Arguments
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Methods can also take more arguments than just <code>self</code>:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">DistanceConverter</span>:
  <span class="cm-variable">kms_in_a_mile</span> <span class="cm-operator">=</span> <span class="cm-number">1.609</span>
  <span class="cm-keyword">def</span> <span class="cm-def">how_many_kms</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">miles</span>):
    <span class="cm-keyword">return</span> <span class="cm-variable">miles</span> <span class="cm-operator">*</span> <span class="cm-variable-2">self</span>.<span class="cm-property">kms_in_a_mile</span>

<span class="cm-variable">converter</span> <span class="cm-operator">=</span> <span class="cm-variable">DistanceConverter</span>()
<span class="cm-variable">kms_in_5_miles</span> <span class="cm-operator">=</span> <span class="cm-variable">converter</span>.<span class="cm-property">how_many_kms</span>(<span class="cm-number">5</span>)
<span class="cm-builtin">print</span>(<span class="cm-variable">kms_in_5_miles</span>)
<span class="cm-comment"># prints "8.045"</span></div></span></pre>
<p>Above we defined a <code>DistanceConverter</code> class, instantiated it, and used it to convert 5 miles into kilometers. Notice again that even though <code>how_many_kms</code> takes two arguments in its definition, we only pass <code>miles</code>, because <code>self</code> is implicitly passed (and refers to the object <code>converter</code>).</p>
</div>


###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>It's March 14th (known in some places as <strong>Pi day</strong>) at <em>Jan van High</em>, and you're feeling awfully festive. You decide to create a program that calculates the area of a circle.</p>
<p>Create a <code>Circle</code> class with class variable <code>pi</code>. Set <code>pi</code> to the approximation <code>3.14</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Give <code>Circle</code> an <code>area</code> method that takes two parameters: <code>self</code> and <code>radius</code>.</p>
<p>Return the area as given by this formula:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">area</span> <span class="cm-operator">=</span> <span class="cm-variable">pi</span> <span class="cm-operator">*</span> <span class="cm-variable">radius</span> <span class="cm-operator">*</span><span class="cm-operator">*</span> <span class="cm-number">2</span></div></span></pre>
</div>

* <p>Create an instance of <code>Circle</code>. Save it into the variable <code>circle</code>.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>You go to measure several circles you happen to find around. </p>
<ul>
<li>A medium pizza that is 12 inches across.</li>
<li>Your teaching table which is 36 inches across.</li>
<li>The Round Room auditorium, which is 11,460 inches across.</li>
</ul>
<p>You save the areas of these three things into <code>pizza_area</code>, <code>teaching_table_area</code>, and <code>round_room_area</code>.</p>
<p>Remember that the <code>radius</code> of a circle is half the diameter. We gave three diameters here, so halve them before you calculate the given circle's area.</p>
</div>


```python
class Circle():
  pi = 3.14
  def area(self, radius):
    return self.pi * radius ** 2
  
circle = Circle()

pizza_radius = 12/2
teaching_table_radius = 36/2
round_room_radius = 11460/2

pizza_area = circle.area(pizza_radius)
teaching_table_area = circle.area(teaching_table_radius)
round_room_area = circle.area(round_room_radius)
```

### Constructors
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>There are several methods that we can define in a Python class that have special behavior. These methods are sometimes called "magic", because they behave differently from regular methods. Another popular term is <em>dunder methods</em>, so-named because they have two underscores (double-underscore abbreviated to "dunder") on either side of them.</p>
<p>The first dunder method we're going to use is the <code>__init__</code> method (note the two underscores before and after the word "init"). This method is used to <em>initialize</em> a newly created object. It is called every time the class is instantiated.</p>
<p>Methods that are used to prepare an object being instantiated are called <em>constructors</em>. The word "constructor" is used to describe similar features in other object-oriented programming languages but programmers who refer to a constructor in Python are usually talking about the <code>__init__</code> method.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Shouter</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-builtin">print</span>(<span class="cm-string">"HELLO?!"</span>)

<span class="cm-variable">shout1</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>()
<span class="cm-comment"># prints "HELLO?!"</span>

<span class="cm-variable">shout2</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>()
<span class="cm-comment"># prints "HELLO?!"</span></div></span></pre>
<p>Above we created a class called <code>Shouter</code> and every time we create an instance of <code>Shouter</code> the program prints out a shout. Don't worry, this doesn't hurt the computer at all.</p>
<p>Pay careful attention to the instantiation syntax we use. <code>Shouter()</code> looks a lot like a function call, doesn't it? If it's a function, can we pass parameters to it? We absolutely can, and those parameters will be received by the <code>__init__</code> method.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Shouter</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">phrase</span>):
    <span class="cm-comment"># make sure phrase is a string</span>
    <span class="cm-keyword">if</span> <span class="cm-builtin">type</span>(<span class="cm-variable">phrase</span>) <span class="cm-operator">==</span> <span class="cm-builtin">str</span>:

      <span class="cm-comment"># then shout it out</span>
      <span class="cm-builtin">print</span>(<span class="cm-variable">phrase</span>.<span class="cm-property">upper</span>())

<span class="cm-variable">shout1</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>(<span class="cm-string">"shout"</span>)
<span class="cm-comment"># prints "SHOUT"</span>

<span class="cm-variable">shout2</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>(<span class="cm-string">"shout"</span>)
<span class="cm-comment"># prints "SHOUT"</span>

<span class="cm-variable">shout3</span> <span class="cm-operator">=</span> <span class="cm-variable">Shouter</span>(<span class="cm-string">"let it all out"</span>)
<span class="cm-comment"># prints "LET IT ALL OUT"</span></div></span></pre>
<p>Above we've updated our <code>Shouter</code> class to take the additional parameter <code>phrase</code>. When we created each of our objects we passed an argument to the constructor. The constructor takes the argument <code>phrase</code> and, if it's a string, prints out the all-caps version of <code>phrase</code>.</p>
</div>



###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Add a constructor to our <code>Circle</code> class.</p>
<p>Since we seem more frequently to know the diameter of a circle, it should take the argument <code>diameter</code>.</p>
<p>It doesn't need to do anything yet, just write <code>pass</code> in the body of the constructor.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Now have the constructor print out the message <code>"New circle with diameter: {diameter}"</code> when a new circle is created.</p>
<p>Create a circle <code>teaching_table</code> with diameter 36.</p>
</div>

```python
class Circle:
  pi = 3.14
  
  # Add constructor here:
  def __init__(self,diameter):
    print("New circle with diameter: {}".format(diameter))  
  
teaching_table = Circle(36)  
```

### Instance Variables
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>We've learned so far that a class is a schematic for a data type and an object is an instance of a class, but why is there such a strong need to differentiate the two if each object can only have the methods and class variables the class has? This is because each instance of a class can hold different kinds of data. </p>
<p>The data held by an object is referred to as an <em>instance variable</em>. Instance variables aren't shared by all instances of a class — they are variables that are specific to the object they are attached to.</p>
<p>Let's say that we have the following class definition:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">FakeDict</span>:
  <span class="cm-keyword">pass</span></div></span></pre>
<p>We can instantiate two different objects from this class, <code>fake_dict1</code> and <code>fake_dict2</code>, and assign instance variables to these objects using the same attribute notation that was used for accessing class variables.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">fake_dict1</span> <span class="cm-operator">=</span> <span class="cm-variable">FakeDict</span>()
<span class="cm-variable">fake_dict2</span> <span class="cm-operator">=</span> <span class="cm-variable">FakeDict</span>()

<span class="cm-variable">fake_dict1</span>.<span class="cm-property">fake_key</span> <span class="cm-operator">=</span> <span class="cm-string">"This works!"</span>
<span class="cm-variable">fake_dict2</span>.<span class="cm-property">fake_key</span> <span class="cm-operator">=</span> <span class="cm-string">"This too!"</span>

<span class="cm-comment"># Let's join the two strings together!</span>
<span class="cm-variable">working_string</span> <span class="cm-operator">=</span> <span class="cm-string">"{} {}"</span>.<span class="cm-property">format</span>(<span class="cm-variable">fake_dict1</span>.<span class="cm-property">fake_key</span>, <span class="cm-variable">fake_dict2</span>.<span class="cm-property">fake_key</span>)
<span class="cm-builtin">print</span>(<span class="cm-variable">working_string</span>)
<span class="cm-comment"># prints "This works! This too!"</span></div></span></pre>
</div>

###### TASK
* <p>In <strong>script.py</strong> we have defined a <code>Store</code> class. Create two objects from this store class, named <code>alternative_rocks</code> and <code>isabelles_ices</code>.</p>

* <p>Give them both instance attributes called <code>store_name</code>. Set <code>alternative_rocks</code>'s <code>store_name</code> to "Alternative Rocks". Set <code>isabelles_ices</code>'s <code>store_name</code> to "Isabelle's Ices".</p>

```python
class Store:
  pass

alternative_rocks = Store()
isabelles_ices = Store()

alternative_rocks.store_name = "Alternative Rocks"

isabelles_ices.store_name = "Isabelle's Ices"
```

### Attribute Functions
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Instance variables and class variables are both accessed similarly in Python. This is no mistake, they are both considered <em>attributes</em> of an object. If we attempt to access an attribute that is neither a class variable nor an instance variable of the object Python will throw an <code>AttributeError</code>.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">NoCustomAttributes</span>:
  <span class="cm-keyword">pass</span>

<span class="cm-variable">attributeless</span> <span class="cm-operator">=</span> <span class="cm-variable">NoCustomAttributes</span>()

<span class="cm-keyword">try</span>:
  <span class="cm-variable">attributeless</span>.<span class="cm-property">fake_attribute</span>
<span class="cm-keyword">except</span> <span class="cm-variable">AttributeError</span>:
  <span class="cm-builtin">print</span>(<span class="cm-string">"This text gets printed!"</span>)

<span class="cm-comment"># prints "This text gets printed!"</span></div></span></pre>
<p>What if we aren't sure if an object has an attribute or not? <code>getattr()</code> is a Python function that works a lot like the usual dot-syntax (i.e., <code>object_name.attribute_name</code>) but we can supply a third argument that will be the default if the object does not have the given attribute. What if we only really care whether the attribute exists? <code>hasattr()</code> will return <code>True</code> if an object has a given attribute and <code>False</code> otherwise.</p>
<p>Calling those functions looks like this:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-builtin">hasattr</span>(<span class="cm-variable">attributeless</span>, <span class="cm-string">"fake_attribute"</span>)
<span class="cm-comment"># returns False</span>

<span class="cm-builtin">getattr</span>(<span class="cm-variable">attributeless</span>, <span class="cm-string">"other_fake_attribute"</span>, <span class="cm-number">800</span>)
<span class="cm-comment"># returns 800, the default value</span></div></span></pre>
<p>Above we checked if the <code>attributeless</code> object has the attribute <code>fake_attribute</code>. Since it does not, <code>hasattr()</code> returned <code>False</code>. After that, we used <code>getattr</code> to attempt to retrieve <code>other_fake_attribute</code>. Since <code>other_fake_attribute</code> isn't a real attribute on <code>attributeless</code>, our call to <code>getattr()</code> returned the supplied default value <code>800</code>, instead of throwing an <code>AttributeError</code>.</p>
</div>


###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> we have a list of different data types, some strings, some lists, and some dictionaries, all saved in the variable <code>how_many_s</code>.</p>
<p>For every element in the list, check if the element has the attribute <code>count</code>. If so, count the number of times the string <code>"s"</code> appears in the element. Print this number.</p>
</div>

```python
how_many_s = [{'s': False}, "sassafrass", 18, ["a", "c", "s", "d", "s"]]

for element in how_many_s:
  if hasattr(element, "count"):
    print(element.count("s"))
```

### SELF
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Since we can already use dictionaries to store key-value pairs, using objects for that purpose is not really useful. Instance variables are more powerful when you can guarantee a rigidity to the data the object is holding. </p>
<p>This convenience is most apparent when the constructor creates the instance variables, using the arguments passed in to it. If we were creating a search engine, and we wanted to create classes for each separate entry we could return. We'd do that like this:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">SearchEngineEntry</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">url</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">url</span> <span class="cm-operator">=</span> <span class="cm-variable">url</span>

<span class="cm-variable">codecademy</span> <span class="cm-operator">=</span> <span class="cm-variable">SearchEngineEntry</span>(<span class="cm-string">"www.codecademy.com"</span>)
<span class="cm-variable">wikipedia</span> <span class="cm-operator">=</span> <span class="cm-variable">SearchEngineEntry</span>(<span class="cm-string">"www.wikipedia.org"</span>)

<span class="cm-builtin">print</span>(<span class="cm-variable">codecademy</span>.<span class="cm-property">url</span>)
<span class="cm-comment"># prints "www.codecademy.com"</span>

<span class="cm-builtin">print</span>(<span class="cm-variable">wikipedia</span>.<span class="cm-property">url</span>)
<span class="cm-comment"># prints "www.wikipedia.org"</span></div></span></pre>
<p>Since the <code>self</code> keyword refers to the object and not the class being called, we can define a <code>secure</code> method on the <code>SearchEngineEntry</code> class that returns the secure link to an entry.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">SearchEngineEntry</span>:
  <span class="cm-variable">secure_prefix</span> <span class="cm-operator">=</span> <span class="cm-string">"https://"</span>
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">url</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">url</span> <span class="cm-operator">=</span> <span class="cm-variable">url</span>

  <span class="cm-keyword">def</span> <span class="cm-def">secure</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-keyword">return</span> <span class="cm-string">"{prefix}{site}"</span>.<span class="cm-property">format</span>(<span class="cm-variable">prefix</span><span class="cm-operator">=</span><span class="cm-variable-2">self</span>.<span class="cm-property">secure_prefix</span>, <span class="cm-variable">site</span><span class="cm-operator">=</span><span class="cm-variable-2">self</span>.<span class="cm-property">url</span>)

<span class="cm-variable">codecademy</span> <span class="cm-operator">=</span> <span class="cm-variable">SearchEngineEntry</span>(<span class="cm-string">"www.codecademy.com"</span>)

<span class="cm-builtin">print</span>(<span class="cm-variable">codecademy</span>.<span class="cm-property">secure</span>())
<span class="cm-comment"># prints "https://www.codecademy.com"</span>

<span class="cm-builtin">print</span>(<span class="cm-variable">wikipedia</span>.<span class="cm-property">secure</span>())
<span class="cm-comment"># prints "https://www.wikipedia.org"</span></div></span></pre>
<p>Above we define our <code>secure()</code> method to take just the one required argument, <code>self</code>. We access both the class variable <code>self.secure_prefix</code> and the instance variable <code>self.url</code> to return a secure URL. </p>
<p>This is the strength of writing object-oriented programs. We can write our classes to structure the data that we need and write methods that will interact with that data in a meaningful way.</p>
</div>


###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> you'll find our familiar friend, the <code>Circle</code> class.</p>
<p>Even though we usually know the <code>diameter</code> beforehand, what we need for most calculations is the <code>radius</code>. </p>
<p>In <code>Circle</code>'s constructor set the instance variable <code>self.radius</code> to equal half the <code>diameter</code> that gets passed in.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Define three <code>Circle</code>s with three different diameters.</p>
<ul>
<li>A medium pizza, <code>medium_pizza</code>, that is 12 inches across.</li>
<li>Your teaching table, <code>teaching_table</code>, which is 36 inches across.</li>
<li>The Round Room auditorium, <code>round_room</code>, which is 11,460 inches across.</li>
</ul>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Define a new method <code>circumference</code> for your circle object that takes only one argument, <code>self</code>, and returns the circumference of a circle with the given radius by this formula:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">circumference</span> <span class="cm-operator">=</span> <span class="cm-number">2</span> <span class="cm-operator">*</span> <span class="cm-variable">pi</span> <span class="cm-operator">*</span> <span class="cm-variable">radius</span></div></span></pre>
</div>

* <p>Print out the circumferences of <code>medium_pizza</code>, <code>teaching_table</code>, and <code>round_room</code>.</p>

```python
class Circle:
  pi = 3.14
  def __init__(self, diameter):
    print("Creating circle with diameter {d}".format(d=diameter))
    # Add assignment for self.radius here:
    self.radius = diameter / 2
  def circumference(self):
    return 2 * self.pi * self.radius
    
medium_pizza = Circle(12)
teaching_table = Circle(36)
round_room = Circle(11460)

print(medium_pizza.circumference())
print(teaching_table.circumference())
print(round_room.circumference())
```

### Everything is an Object
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Attributes can be added to user-defined objects after instantiation, so it's possible for an object to have some attributes that are not explicitly defined in an object's constructor. We can use the <code>dir()</code> function to investigate an object's attributes at runtime. <code>dir()</code> is short for <em>directory</em> and offers an organized presentation of object attributes.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">FakeDict</span>:
  <span class="cm-keyword">pass</span>

<span class="cm-variable">fake_dict</span> <span class="cm-operator">=</span> <span class="cm-variable">FakeDict</span>()
<span class="cm-variable">fake_dict</span>.<span class="cm-property">attribute</span> <span class="cm-operator">=</span> <span class="cm-string">"Cool"</span>

<span class="cm-builtin">dir</span>(<span class="cm-variable">fake_dict</span>)
<span class="cm-comment"># Prints ['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', 'attribute']</span></div></span></pre>
<p>That's certainly a lot more attributes than we defined! Python automatically adds a number of attributes to all objects that get created. These internal attributes are usually indicated by double-underscores. But sure enough, <code>attribute</code> is in that list.</p>
<p>Do you remember being able to use <code>type()</code> on Python's native data types? This is because they are also objects in Python. Their classes are <code>int</code>, <code>float</code>, <code>str</code>, <code>list</code>, and <code>dict</code>. These Python classes have special syntax for their instantiation, <code>1</code>, <code>1.0</code>, <code>"hello"</code>, <code>[]</code>, and <code>{}</code> specifically. But these instances are still full-blown objects to Python.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">fun_list</span> <span class="cm-operator">=</span> [<span class="cm-number">10</span>, <span class="cm-string">"string"</span>, {<span class="cm-string">'abc'</span>: <span class="cm-keyword">True</span>}]

<span class="cm-builtin">type</span>(<span class="cm-variable">fun_list</span>)
<span class="cm-comment"># Prints &lt;class 'list'&gt;</span>

<span class="cm-builtin">dir</span>(<span class="cm-variable">fun_list</span>)
<span class="cm-comment"># Prints ['__add__', '__class__', [...], 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']</span></div></span></pre>
<p>Above we define a new list. We check it's type and see that's an instantiation of class <code>list</code>. We use <code>dir()</code> to explore its attributes, and it gives us a large number of internal Python dunder attributes, but, afterward, we get the usual list methods.</p>
</div>

###### TASK
* <p>Call <code>dir()</code> on the number <code>5</code>. Print out the results.</p>

* <p>Define a function called <code>this_function_is_an_object</code>. It can take any parameters and return anything you'd like.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Print out the result of calling <code>dir()</code> on <code>this_function_is_an_object</code>. </p>
<p>Functions are objects too!</p>
</div>


```python
dir(5)

def this_function_is_an_object():
  return

print(dir(this_function_is_an_object))
```

### String Representation
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>One of the first things we learn as programmers is how to print out information that we need for debugging. Unfortunately, when we print out an object we get a default representation that seems fairly useless.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Employee</span>():
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">name</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">name</span> <span class="cm-operator">=</span> <span class="cm-variable">name</span>

<span class="cm-variable">argus</span> <span class="cm-operator">=</span> <span class="cm-variable">Employee</span>(<span class="cm-string">"Argus Filch"</span>)
<span class="cm-builtin">print</span>(<span class="cm-variable">argus</span>)
<span class="cm-comment"># prints "&lt;__main__.Employee object at 0x104e88390&gt;"</span></div></span></pre>
<p>This default string representation gives us some information, like where the class is defined and our computer's memory address where this object is stored, but is usually not useful information to have when we are trying to debug our code.</p>
<p>We learned about the dunder method <code>__init__</code>. Now, we will learn another dunder method called  <code>__repr__</code>. This is a method we can use to tell Python what we want the <em>string representation</em> of the class to be. <code>__repr__</code> can only have one parameter, <code>self</code>, and must return a string.</p>
<p>In our <code>Employee</code> class above, we have an instance variable called <code>name</code> that should be unique enough to be useful when we're printing out an instance of the  <code>Employee</code> class.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Employee</span>():
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">name</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">name</span> <span class="cm-operator">=</span> <span class="cm-variable">name</span>

  <span class="cm-keyword">def</span> <span class="cm-def">__repr__</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-keyword">return</span> <span class="cm-variable-2">self</span>.<span class="cm-property">name</span>

<span class="cm-variable">argus</span> <span class="cm-operator">=</span> <span class="cm-variable">Employee</span>(<span class="cm-string">"Argus Filch"</span>)
<span class="cm-builtin">print</span>(<span class="cm-variable">argus</span>)
<span class="cm-comment"># prints "Argus Filch"</span></div></span></pre>
<p>We implemented the <code>__repr__</code> method and had it return the <code>.name</code> attribute of the object. When we printed the object out it simply printed the <code>.name</code> of the object! Cool!</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Add a <code>__repr__</code> method to the <code>Circle</code> class that returns</p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">Circle with radius {radius}</div></span></pre></div>

* <p>Print out <code>medium_pizza</code>, <code>teaching_table</code>, and <code>round_room</code>.</p>

```python
class Circle:
  pi = 3.14
  
  def __init__(self, diameter):
    self.radius = diameter / 2
  
  def area(self):
    return self.pi * self.radius ** 2
  
  def circumference(self):
    return self.pi * 2 * self.radius
  
  def __repr__(self):
    return "Circle with radius {radius}".format(radius=self.radius)
  
medium_pizza = Circle(12)
teaching_table = Circle(36)
round_room = Circle(11460)

print(medium_pizza)
print(teaching_table)
print(round_room)
```

### Review
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>So far we've covered what a data type actually is in Python. We explored what the functionality of Python's built-in types (also referred to as <em>primitives</em>) are. We learned how to create our own data types using the <code>class</code> keyword.</p>
<p>We explored the relationship between a class and an object — we create objects when we instantiate a class, we find the class when we check the <code>type()</code> of an object. We learned the difference between class variables (the same for all objects of a class) and instance variables (unique for each object).</p>
<p>We learned about how to define an object's functionality with methods. We created multiple objects from the same class, all with similar functionality, but with different internal data. They all had the same methods, but produced different output because they were different instances.</p>
<p>Take a moment to congratulate yourself, object-oriented programming is a complicated concept.</p>
</div>


###### TASK
* <p>Define a class <code>Student</code> this will be our data model at <em>Jan van Eyck High School and Conservatory</em>.</p>

* <p>Add a constructor for <code>Student</code>. Have the constructor take in two parameters: a <code>name</code> and a <code>year</code>. Save those two as attributes <code>.name</code> and <code>.year</code>.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Create three instances of the <code>Student</code> class:</p>
<ul>
<li>Roger van der Weyden, year 10</li>
<li>Sandro Botticelli, year 12</li>
<li>Pieter Bruegel the Elder, year 8</li>
</ul>
<p>Save them into the variables <code>roger</code>, <code>sandro</code>, and <code>pieter</code>.</p>
</div>

* <p>Create a <code>Grade</code> class, with <code>minimum_passing</code> as an attribute set to <code>65</code>.</p>

* <p>Give <code>Grade</code> a constructor. Take in a parameter <code>score</code> and assign it to <code>self.score</code>.</p>

* <p>In the body of the constructor for <code>Student</code>, declare <code>self.grades</code> as an empty list.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Add an <code>.add_grade()</code> method to <code>Student</code> that takes a parameter, <code>grade</code>.</p>
<p><code>.add_grade()</code> should verify that <code>grade</code> is of type <code>Grade</code> and if so, add it to the <code>Student</code>'s <code>.grades</code>.</p>
<p>If <code>grade</code> isn't an instance of <code>Grade</code> then <code>.add_grade()</code> should do nothing.</p>
</div>

* <p>Create a new <code>Grade</code> with a score of <code>100</code> and add it to <code>pieter</code>'s <code>.grades</code> attribute using <code>.add_grade()</code>.</p>



```python
class Student:
  def __init__(self, name, year):
    self.name = name
    self.year = year
    self.grades = []
  
  def add_grade(self, grade):
    if type(grade) is Grade:
      self.grades.append(grade)
    
roger = Student("Roger van der Weyden", 10)
sandro = Student("Sandro Botticelli", 12)
pieter = Student("Pieter Bruegel the Elder", 8)

class Grade:
  minimum_passing = 65
  
  def __init__(self, score):
    self.score = score
    
pieter.add_grade(Grade(100))    
```

