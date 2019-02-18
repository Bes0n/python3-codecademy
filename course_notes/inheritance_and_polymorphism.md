##  INHERITANCE AND POLYMORPHISM

### Inheritance 

<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Classes are designed to allow for more code reuse, but what if we need a class that looks a lot like a class we already have? If the bulk of a class's definition is useful, but we have a new use case that is distinct from how the original class was used, we can <em>inherit</em> from the original class. Think of inheritance as a remix — it sounds a lot like the original, but there's something... different about it.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">User</span>:
  <span class="cm-variable">is_admin</span> <span class="cm-operator">=</span> <span class="cm-keyword">False</span>
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">username</span>)
    <span class="cm-variable-2">self</span>.<span class="cm-property">username</span> <span class="cm-operator">=</span> <span class="cm-variable">username</span>

<span class="cm-keyword">class</span> <span class="cm-def">Admin</span>(<span class="cm-variable">User</span>):
  <span class="cm-variable">is_admin</span> <span class="cm-operator">=</span> <span class="cm-keyword">True</span></div></span></pre>
<p>Above we defined <code>User</code> as our <em>base class</em>. We want to create a new class that inherits from it, so we created the <em>subclass</em> <code>Admin</code>. In the above example, <code>Admin</code> has the same constructor as <code>User</code>. Only the class variable <code>is_admin</code> is set differently between the two.</p>
<p>Sometimes a base class is called a <em>parent class</em>. In these terms, the class inheriting from it, the subclass, is also referred to as a <em>child class</em>.</p>
</div>

###### TASK
<p>In <strong>script.py</strong> we've already defined the class <code>Bin</code>. Create a subclass of <code>Bin</code> called <code>RecyclingBin</code>.</p>

```python
class Bin:
  pass

class RecyclingBin(Bin):
  pass
```

### Exceptions
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>There's one very important family of class definitions built in to the Python language. An <em>Exception</em> is a class that inherits from Python's <code>Exception</code> class.</p>
<p>We can validate this ourselves using the <code>issubclass()</code> function. <code>issubclass()</code> is a Python built-in function that takes two parameters. <code>issubclass()</code> returns <code>True</code> if the first argument is a subclass of the second argument. It returns <code>False</code> if the first class is not a subclass of the second. <code>issubclass()</code> raises a <code>TypeError</code> if either argument passed in is not a class.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-builtin">issubclass</span>(<span class="cm-variable">ZeroDivisionError</span>, <span class="cm-variable">Exception</span>)
<span class="cm-comment"># Returns True</span></div></span></pre>
<p>Above, we checked whether <code>ZeroDivisionError</code>, the exception raised when attempting division by zero, is a subclass of <code>Exception</code>. It is, so <code>issubclass</code> returns <code>True</code>.</p>
<p>Why is it beneficial for exceptions to inherit from one another? Let's consider an example where we create our own exceptions. What if we were creating software that tracks our kitchen appliances? We would be able to design a suite of exceptions for that need:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">KitchenException</span>(<span class="cm-variable">Exception</span>):
  <span class="cm-string">"""</span>
<span class="cm-string">  Exception that gets thrown when a kitchen appliance isn't working</span>
<span class="cm-string">  """</span>

<span class="cm-keyword">class</span> <span class="cm-def">MicrowaveException</span>(<span class="cm-variable">KitchenException</span>):
  <span class="cm-string">"""</span>
<span class="cm-string">  Exception for when the microwave stops working</span>
<span class="cm-string">  """</span>

<span class="cm-keyword">class</span> <span class="cm-def">RefrigeratorException</span>(<span class="cm-variable">KitchenException</span>):
  <span class="cm-string">"""</span>
<span class="cm-string">  Exception for when the refrigerator stops working</span>
<span class="cm-string">  """</span></div></span></pre>
<p>In this code, we define three exceptions. First, we define a <code>KitchenException</code> that acts as the parent to our other, specific kitchen appliance exceptions. <code>KitchenException</code> subclasses <code>Exception</code>, so it behaves in the same way that regular <code>Exception</code>s do. Afterward we define <code>MicrowaveException</code> and <code>RefrigeratorException</code> as subclasses.</p>
<p>Since our exceptions are subclassed in this way, we can catch any of <code>KitchenException</code>'s subclasses by catching <code>KitchenException</code>. For example:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">get_food_from_fridge</span>():
  <span class="cm-keyword">if</span> <span class="cm-variable">refrigerator</span>.<span class="cm-property">cooling</span> <span class="cm-operator">==</span> <span class="cm-keyword">False</span>:
    <span class="cm-keyword">raise</span> <span class="cm-variable">RefrigeratorException</span>
  <span class="cm-keyword">else</span>:
    <span class="cm-keyword">return</span> <span class="cm-variable">food</span>

<span class="cm-keyword">def</span> <span class="cm-def">heat_food</span>(<span class="cm-variable">food</span>):
  <span class="cm-keyword">if</span> <span class="cm-variable">microwave</span>.<span class="cm-property">working</span> <span class="cm-operator">==</span> <span class="cm-keyword">False</span>:
    <span class="cm-keyword">raise</span> <span class="cm-variable">MicrowaveException</span>
  <span class="cm-keyword">else</span>:
    <span class="cm-variable">microwave</span>.<span class="cm-property">cook</span>(<span class="cm-variable">food</span>)
    <span class="cm-keyword">return</span> <span class="cm-variable">food</span>

<span class="cm-keyword">try</span>:
  <span class="cm-variable">food</span> <span class="cm-operator">=</span> <span class="cm-variable">get_food_from_fridge</span>()
  <span class="cm-variable">food</span> <span class="cm-operator">=</span> <span class="cm-variable">heat_food</span>(<span class="cm-variable">food</span>)
<span class="cm-keyword">except</span> <span class="cm-variable">KitchenException</span>:
  <span class="cm-variable">food</span> <span class="cm-operator">=</span> <span class="cm-variable">order_takeout</span>()</div></span></pre>
<p>In the above example, we attempt to retrieve food from the fridge and heat it in the microwave. If either <code>RefrigeratorException</code> or <code>MicrowaveException</code> is raised, we opt to order takeout instead. We catch both <code>RefrigeratorException</code> and <code>MicrowaveException</code> in our try/except block because both are subclasses of <code>KitchenException</code>.</p>
<p>Explore Python's exception hierarchy in the <a href="https://docs.python.org/3/library/exceptions.html#exception-hierarchy" target="_blank">Python documentation</a>!</p>
</div>


###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> we've defined a <code>CandleShop</code> class for our new candle shop that we've named <em>Here's a Hot Tip: Buy Drip Candles</em>. We want to define our own exceptions for when we run out of candles to sell.</p>
<p>Define your own exception called <code>OutOfStock</code> that inherits from the <code>Exception</code> class.</p>
</div>

* <p>Have <code>CandleShop</code> raise your <code>OutOfStock</code> exception when <code>CandleShop.buy()</code> tries to buy a candle that's out of stock.</p>


```python
# Define your exception up here:
class OutOfStock(Exception):
  print("No More Candies!")

# Update the class below to raise OutOfStock
class CandleShop:
  name = "Here's a Hot Tip: Buy Drip Candles"
  def __init__(self, stock):
    self.stock = stock
    
  def buy(self, color):
    if self.stock[color] < 1:
      raise OutOfStock
    self.stock[color] = self.stock[color] - 1

candle_shop = CandleShop({'blue': 6, 'red': 2, 'green': 0})
candle_shop.buy('blue')

# This should raise OutOfStock:
candle_shop.buy('green')
```

### Overriding Methods
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Inheritance is a useful way of creating objects with different class variables, but is that all it's good for? What if one of the methods needs to be implemented differently? In Python, all we have to do to <em>override</em> a method definition is to offer a new definition for the method in our subclass. </p>
<p>An overridden method is one that has a different definition from its parent class. What if <code>User</code> class didn't have an <code>is_admin</code> flag but just checked if it had permission for something based on a permissions dictionary? It could look like this:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">User</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">username</span>, <span class="cm-variable">permissions</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">username</span> <span class="cm-operator">=</span> <span class="cm-variable">username</span>
    <span class="cm-variable-2">self</span>.<span class="cm-property">permissions</span> <span class="cm-operator">=</span> <span class="cm-variable">permissions</span>

  <span class="cm-keyword">def</span> <span class="cm-def">has_permission_for</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">key</span>):
    <span class="cm-keyword">if</span> <span class="cm-variable-2">self</span>.<span class="cm-property">permissions</span>.<span class="cm-property">get</span>(<span class="cm-variable">key</span>):
      <span class="cm-keyword">return</span> <span class="cm-keyword">True</span>
    <span class="cm-keyword">else</span>:
      <span class="cm-keyword">return</span> <span class="cm-keyword">False</span></div></span></pre>
<p>Above we defined a class <code>User</code> which takes a <code>permissions</code> parameter in its constructor. Let's assume <code>permissions</code> is a <code>dict</code>. <code>User</code> has a method <code>.has_permission_for()</code> implemented, where it checks to see if a given key is in its <code>permissions</code> dictionary. We could then define our <code>Admin</code> user like this:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Admin</span>(<span class="cm-variable">User</span>):
  <span class="cm-keyword">def</span> <span class="cm-def">has_permission_for</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">key</span>):
    <span class="cm-keyword">return</span> <span class="cm-keyword">True</span></div></span></pre>
<p>Here we define an <code>Admin</code> class that subclasses <code>User</code>. It has all methods, attributes, and functionality that <code>User</code> has. However, if you call <code>has_permission_for</code> on an instance of <code>Admin</code>, it won't check its <code>permissions</code> dictionary. Since this <code>User</code> is also an <code>Admin</code>, we just say they have permission to see everything!</p>
</div>

###### TASK
* <p>In <strong>script.py</strong>, we've defined two classes, <code>Message</code> and <code>User</code>. Create an <code>Admin</code> class that subclasses the <code>User</code> class.</p>

* <p>Override <code>User</code>'s <code>.edit_message()</code> method in <code>Admin</code> so that an <code>Admin</code> can edit any messages.</p>

```python
class Message:
  def __init__(self, sender, recipient, text):
    self.sender = sender
    self.recipient = recipient
    self.text = text

class User:
  def __init__(self, username):
    self.username = username
    
  def edit_message(self, message, new_text):
    if message.sender == self.username:
      message.text = new_text
      
class Admin(User):
  def edit_message(self,message, new_text):
    message.text = new_text
```

### Super()
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Overriding methods is really useful in some cases but sometimes we want to add some extra logic to the existing method. In order to do that we need a way to call the method from the parent class. Python gives us a way to do that using <code>super()</code>. </p>
<p><code>super()</code> gives us a <em>proxy object</em>. With this proxy object, we can invoke the method of an object's parent class (also called its superclass). We call the required function as a method on <code>super()</code>:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Sink</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">basin</span>, <span class="cm-variable">nozzle</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">basin</span> <span class="cm-operator">=</span> <span class="cm-variable">basin</span>
    <span class="cm-variable-2">self</span>.<span class="cm-property">nozzle</span> <span class="cm-operator">=</span> <span class="cm-variable">nozzle</span>

<span class="cm-keyword">class</span> <span class="cm-def">KitchenSink</span>(<span class="cm-variable">Sink</span>):
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">basin</span>, <span class="cm-variable">nozzle</span>, <span class="cm-variable">trash_compactor</span><span class="cm-operator">=</span><span class="cm-keyword">None</span>):
    <span class="cm-builtin">super</span>().<span class="cm-property">__init__</span>(<span class="cm-variable">basin</span>, <span class="cm-variable">nozzle</span>)
    <span class="cm-keyword">if</span> <span class="cm-variable">trash_compactor</span>:
      <span class="cm-variable-2">self</span>.<span class="cm-property">trash_compactor</span> <span class="cm-operator">=</span> <span class="cm-variable">trash_compactor</span></div></span></pre>
<p>Above we defined two classes. First, we defined a <code>Sink</code> class with a constructor that assigns a rinse basin and a sink nozzle to a <code>Sink</code> instance. Afterwards, we defined a <code>KitchenSink</code> class that inherits from <code>Sink</code>. <code>KitchenSink</code>'s constructor takes an additional parameter, a <code>trash_compactor</code>. <code>KitchenSink</code> then calls the constructor for <code>Sink</code> with the <code>basin</code> and <code>nozzle</code> it received using the <code>super()</code> function, with this line of code:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-builtin">super</span>().<span class="cm-property">__init__</span>(<span class="cm-variable">basin</span>, <span class="cm-variable">nozzle</span>)</div></span></pre>
<p>This line says: "call the constructor (the function called <code>__init__</code>) of the class that is this class's parent class." In the example given, <code>KitchenSink</code>'s constructor calls the constructor for <code>Sink</code>. In this way, we can override a parent class's method to add some new functionality (like adding a <code>trash_compactor</code> to a sink), while still retaining the behavior of the original constructor (like setting the <code>basin</code> and <code>nozzle</code> as instance variables).</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>You're invited to a potluck this week and decide to make your own special version of Potato Salad!</p>
<p>In <strong>script.py</strong> you'll find a class called <code>PotatoSalad</code>, make a subclass of <code>PotatoSalad</code> called <code>SpecialPotatoSalad</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Your special potato salad recipe is pretty similar to a regular potato salad, so let's start with making that.</p>
<p>Create a new constructor for <code>SpecialPotatoSalad</code> that just calls the parent constructor for <code>PotatoSalad</code>. Make sure that <code>SpecialPotatoSalad</code>'s constructor takes the same arguments as <code>PotatoSalad</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>The difference with your special potato salad is... you add raisins to it! You can't remember when you started doing this, but Dolores always hoots about it at her potlucks and if that isn't the nicest thing. You always use the full package of raisins for every potato salad you make, and each package has 40 raisins in it.</p>
<p>In your constructor for <code>SpecialPotatoSalad</code>, after making regular potato salad, set <code>self.raisins = 40</code>.</p>
</div>



```python
class PotatoSalad:
  def __init__(self, potatoes, celery, onions):
    self.potatoes = potatoes
    self.celery = celery
    self.onions = onions
    
    
class SpecialPotatoSalad(PotatoSalad):
  def __init__(self, potatoes, celery, onions):
    super().__init__(potatoes, celery, onions)
    self.raisins = 40
```

### Interfaces
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>You may be wondering at this point why we would even want to have two different classes with two differently implemented methods to use the same method name. This style is especially useful when we have an object for which it might not matter which class the object is an instance of. Instead, we're interested in whether that object can perform a given task.</p>
<p>If we have the following code:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">Chess</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">board</span> <span class="cm-operator">=</span> <span class="cm-variable">setup_board</span>()
    <span class="cm-variable-2">self</span>.<span class="cm-property">pieces</span> <span class="cm-operator">=</span> <span class="cm-variable">add_chess_pieces</span>()

  <span class="cm-keyword">def</span> <span class="cm-def">play</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-builtin">print</span>(<span class="cm-string">"Playing chess!"</span>)

<span class="cm-keyword">class</span> <span class="cm-def">Checkers</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">board</span> <span class="cm-operator">=</span> <span class="cm-variable">setup_board</span>()
    <span class="cm-variable-2">self</span>.<span class="cm-property">pieces</span> <span class="cm-operator">=</span> <span class="cm-variable">add_checkers_pieces</span>()

  <span class="cm-keyword">def</span> <span class="cm-def">play</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-builtin">print</span>(<span class="cm-string">"Playing checkers!"</span>)</div></span></pre>
<p>In the code above we define two classes, <code>Chess</code> and <code>Checkers</code>. In <code>Chess</code> we define a constructor that sets up the board and pieces, and a <code>.play()</code> method. <code>Checkers</code> also defines a <code>.play()</code> method. If we have a <code>play_game()</code> function that takes an instance of <code>Chess</code> or <code>Checkers</code>, it could call the <code>.play()</code> method without having to check which class the object is an instance of.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">def</span> <span class="cm-def">play_game</span>(<span class="cm-variable">chess_or_checkers</span>):
  <span class="cm-variable">chess_or_checkers</span>.<span class="cm-property">play</span>()

<span class="cm-variable">chess_game</span> <span class="cm-operator">=</span> <span class="cm-variable">Chess</span>()
<span class="cm-variable">checkers_game</span> <span class="cm-operator">=</span> <span class="cm-variable">Checkers</span>()
<span class="cm-variable">chess_game_2</span> <span class="cm-operator">=</span> <span class="cm-variable">Chess</span>()

<span class="cm-keyword">for</span> <span class="cm-variable">game</span> <span class="cm-keyword">in</span> [<span class="cm-variable">chess_game</span>, <span class="cm-variable">checkers_game</span>, <span class="cm-variable">chess_game_2</span>]:
  <span class="cm-variable">play_game</span>(<span class="cm-variable">game</span>)
<span class="cm-string">"""</span>
<span class="cm-string">Prints out the following:</span>
<span class="cm-string">Playing chess!</span>
<span class="cm-string">Playing checkers!</span>
<span class="cm-string">Playing chess!</span></div></span></pre>
<p>In this code, we defined a <code>play_game</code> function that could take either a <code>Chess</code> object or a <code>Checkers</code> object. We instantiate a few objects and then call <code>play_game</code> on each.</p>
<p>When two classes have the same method names and attributes, we say they implement the same <em>interface</em>. An interface in Python usually refers to the names of the methods and the arguments they take. Other programming languages have more rigid definitions of what an interface is, but it usually hinges on the fact that different objects from different classes can perform the same operation (even if it is implemented differently for each class).</p>
</div>

###### TASK
* <p>In <strong>script.py</strong> we've defined an <code>InsurancePolicy</code> class. Create a subclass of <code>InsurancePolicy</code> called <code>VehicleInsurance</code>.</p>

* <p>Create a different subclass of <code>InsurancePolicy</code> called <code>HomeInsurance</code>.</p>

* <p>Give <code>VehicleInsurance</code> a <code>.get_rate()</code> method that takes <code>self</code> as a parameter. Return <code>.001</code> multiplied by the price of the vehicle.</p>

* <p>Give <code>HomeInsurance</code> a <code>.get_rate()</code> method that takes <code>self</code> as a parameter. Return <code>.00005</code> multiplied by the price of the home.</p>


```python
class InsurancePolicy:
  def __init__(self, price_of_item):
    self.price_of_item = price_of_item
    
class VehicleInsurance(InsurancePolicy):
  def get_rate(self):
    return self.price_of_item * .001

class HomeInsurance(InsurancePolicy):
  def get_rate(self):
    return self.price_of_item * .00005
  
  
def get_insurance(home_or_vehicle):
  home_or_vehicle.get_rate()
  

vehicle_insurance = VehicleInsurance(3000)

home_insurance = HomeInsurance(25000)

print(vehicle_insurance.get_rate())

print(home_insurance.get_rate())
```

### Polymorphism
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>All this talk of interfaces demonstrates flexibility in programming. Flexibility in programming is a broad philosophy, but what's worth remembering is that we want to implement forms that are familiar in our programs so that usage is expected. For example, let's think of the <code>+</code> operator. It's easy to think of it as a single function that "adds" whatever is on the left with whatever is on the right, but it does many different things in different contexts:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-comment"># For an int and an int, + returns an int</span>
<span class="cm-number">2</span> <span class="cm-operator">+</span> <span class="cm-number">4</span> <span class="cm-operator">==</span> <span class="cm-number">6</span>

<span class="cm-comment"># For a float and a float, + returns a float</span>
<span class="cm-number">3.1</span> <span class="cm-operator">+</span> <span class="cm-number">2.1</span> <span class="cm-operator">==</span> <span class="cm-number">5.2</span>

<span class="cm-comment"># For a string and a string, + returns a string</span>
<span class="cm-string">"Is this "</span> <span class="cm-operator">+</span> <span class="cm-string">"addition?"</span> <span class="cm-operator">==</span> <span class="cm-string">"Is this addition?"</span>

<span class="cm-comment"># For a list and a list, + returns a list</span>
[<span class="cm-number">1</span>, <span class="cm-number">2</span>] <span class="cm-operator">+</span> [<span class="cm-number">3</span>, <span class="cm-number">4</span>] <span class="cm-operator">==</span> [<span class="cm-number">1</span>, <span class="cm-number">2</span>, <span class="cm-number">3</span>, <span class="cm-number">4</span>]</div></span></pre>
<p>Look at all the different things that <code>+</code> does! The hope is that all of these things are, for the arguments given to them, the intuitive result of adding them together. <em>Polymorphism</em> is the term used to describe the same syntax (like the <code>+</code> operator here, but it could be a method name) doing different actions depending on the type of data.</p>
<p>Polymorphism is an abstract concept that covers a lot of ground, but defining class hierarchies that all implement the same interface is a way of introducing polymorphism to our code.</p>
</div>

###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> a few different types of data are provided. Call <code>len()</code> on each of them.</p>
<p>Is the same operation happening for each? How is it different? How is it similar? Does using <code>len()</code> to refer to these different operations make sense?</p>
</div>

```python
a_list = [1, 18, 32, 12]
a_dict = {'value': True}
a_string = "Polymorphism is cool!"

len(a_list)
len(a_dict)
len(a_string)
```

### Dunder Methods 

One way that we can introduce polymorphism to our class definitions is by using Python's special dunder methods. We've explored a few already, the constructor __init__ and the string representation method __repr__, but that's only scratching the tip of the iceberg.

Python gives us the power to define dunder methods that define a custom-made class to look and behave like a Python builtin. What does that mean? Say we had a class that has an addition method:

```python 

class Color:
  def __init__(self, red, blue, green):
    self.red = red
    self.blue = blue
    self.green = green

  def __repr__(self):
    return "Color with RGB = ({red}, {blue}, {green})".format(red=self.red, blue=self.blue, green=self.green)

  def add(self, other):
    """
    Adds two RGB colors together
    Maximum value is 255
    """
    new_red = min(self.red + other.red, 255)
    new_blue = min(self.blue + other.blue, 255)
    new_green = min(self.green + other.green, 255)

    return Color(new_red, new_blue, new_green)

red = Color(255, 0, 0)
blue = Color(0, 255, 0)

magenta = red.add(blue)
print(magenta)
# Prints "Color with RGB = (255, 255, 0)"

```

In this code we defined a Color class that implements an addition function. Unfortunately, red.add(blue) is a little verbose for something that we have an intuitive symbol for (i.e., the + symbol). Well, Python offers the dunder method __add__ for this very reason! If we rename the add() method above to something that looks like this:


```python

class Color: 
  def __add__(self, other):
    """
    Adds two RGB colors together
    Maximum value is 255
    """
    new_red = min(self.red + other.red, 255)
    new_blue = min(self.blue + other.blue, 255)
    new_green = min(self.green + other.green, 255)

    return Color(new_red, new_blue, new_green)

```

Then, if we create the colors:

```python 

red = Color(255, 0, 0)
blue = Color(0, 255, 0)
green = Color(0, 0, 255)

```

We can add them together using the + operator!

```python

# Color with RGB: (255, 255, 0)
magenta = red + blue

# Color with RGB: (0, 255, 255)
cyan = blue + green

# Color with RGB: (255, 0, 255)
yellow = red + green

# Color with RGB: (255, 255, 255)
white = red + blue + green

```

Since we defined an __add__ method for our Color class, we were able to add these objects together using the + operator.

###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> there are two classes defined, <code>Atom</code> and <code>Molecule</code>.</p>
<p>Give <code>Atom</code> a <code>.__add__(self, other)</code> method that returns a Molecule with the two <code>Atom</code>s.</p>
</div>

```python

class Atom:
  def __init__(self, label):
    self.label = label
    
  def __add__(self, other):
    return Molecule([self, other])
    
class Molecule:
  def __init__(self, atoms):
    if type(atoms) is list:
	    self.atoms = atoms
      
sodium = Atom("Na")
chlorine = Atom("Cl")
salt = Molecule([sodium, chlorine])
salt = sodium + chlorine

```

### Dunder Methods II
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Python offers a whole suite of magic methods a class can implement that will allow us to use the same syntax as Python's built-in data types. You can write functionality that allows custom defined types to behave like lists:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">UserGroup</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">users</span>, <span class="cm-variable">permissions</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">user_list</span> <span class="cm-operator">=</span> <span class="cm-variable">users</span>
    <span class="cm-variable-2">self</span>.<span class="cm-property">permissions</span> <span class="cm-operator">=</span> <span class="cm-variable">permissions</span>

  <span class="cm-keyword">def</span> <span class="cm-def">__iter__</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-keyword">return</span> <span class="cm-builtin">iter</span>(<span class="cm-variable-2">self</span>.<span class="cm-property">user_list</span>)

  <span class="cm-keyword">def</span> <span class="cm-def">__len__</span>(<span class="cm-variable-2">self</span>):
    <span class="cm-keyword">return</span> <span class="cm-builtin">len</span>(<span class="cm-variable-2">self</span>.<span class="cm-property">user_list</span>)

  <span class="cm-keyword">def</span> <span class="cm-def">__contains__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">user</span>):
    <span class="cm-keyword">return</span> <span class="cm-variable">user</span> <span class="cm-keyword">in</span> <span class="cm-variable-2">self</span>.<span class="cm-property">user_list</span></div></span></pre>
<p>In our <code>UserGroup</code> class above we defined three methods:</p>
<ul>
<li><code>__init__</code>, our constructor, which sets a list of users to the instance variable <code>self.user_list</code> and sets the group's <code>permissions</code> when we create a new <code>UserGroup</code>.</li>
<li><code>__iter__</code>, the iterator, we use the <code>iter()</code> function to turn the list <code>self.user_list</code> into an <em>iterator</em> so we can use <code>for user in user_group</code> syntax. For more information on iterators, review <a href="https://docs.python.org/3/library/stdtypes.html#typeiter" target="_blank">Python's documentation of Iterator Types</a>.</li>
<li><code>__len__</code>, the length method, so when we call <code>len(user_group)</code> it will return the length of the underlying <code>self.user_list</code> list.</li>
<li><code>__contains__</code>, the check for containment, allows us to use <code>user in user_group</code> syntax to check if a <code>User</code> exists in the <code>user_list</code> we have.</li>
</ul>
<p>These methods allow <code>UserGroup</code> to act like a list using syntax Python programmers will already be familiar with. If all you need is something to act like a list you could absolutely have used a list, but if you want to bundle some other information (like a group's permissions, for instance) having syntax that allows for list-like operations can be very powerful.</p>
<p>We would be able to use the following code to do this, for example:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">class</span> <span class="cm-def">User</span>:
  <span class="cm-keyword">def</span> <span class="cm-def">__init__</span>(<span class="cm-variable-2">self</span>, <span class="cm-variable">username</span>):
    <span class="cm-variable-2">self</span>.<span class="cm-property">username</span> <span class="cm-operator">=</span> <span class="cm-variable">username</span>

<span class="cm-variable">diana</span> <span class="cm-operator">=</span> <span class="cm-variable">User</span>(<span class="cm-string">'diana'</span>)
<span class="cm-variable">frank</span> <span class="cm-operator">=</span> <span class="cm-variable">User</span>(<span class="cm-string">'frank'</span>)
<span class="cm-variable">jenn</span> <span class="cm-operator">=</span> <span class="cm-variable">User</span>(<span class="cm-string">'jenn'</span>)

<span class="cm-variable">can_edit</span> <span class="cm-operator">=</span> <span class="cm-variable">UserGroup</span>([<span class="cm-variable">diana</span>, <span class="cm-variable">frank</span>], {<span class="cm-string">'can_edit_page'</span>: <span class="cm-keyword">True</span>})
<span class="cm-variable">can_delete</span> <span class="cm-operator">=</span> <span class="cm-variable">UserGroup</span>([<span class="cm-variable">diana</span>, <span class="cm-variable">jenn</span>], {<span class="cm-string">'can_delete_posts'</span>: <span class="cm-keyword">True</span>})

<span class="cm-builtin">print</span>(<span class="cm-builtin">len</span>(<span class="cm-variable">can_edit</span>))
<span class="cm-comment"># Prints 2</span>

<span class="cm-keyword">for</span> <span class="cm-variable">user</span> <span class="cm-keyword">in</span> <span class="cm-variable">can_edit</span>:
  <span class="cm-builtin">print</span>(<span class="cm-variable">user</span>.<span class="cm-property">username</span>)
<span class="cm-comment"># Prints "diana" and "frank"</span>

<span class="cm-keyword">if</span> <span class="cm-variable">frank</span> <span class="cm-keyword">in</span> <span class="cm-variable">can_delete</span>:
  <span class="cm-builtin">print</span>(<span class="cm-string">"Since when do we allow Frank to delete things? Does no one remember when he accidentally deleted the site?"</span>)</div></span></pre>
<p>Above we created a set of users and then added them to <code>UserGroup</code>s with specific permissions. Then we used Python built-in functions and syntax to calculate the length of a <code>UserGroup</code>, to iterate through a <code>UserGroup</code> and to check for a <code>User</code>'s membership in a <code>UserGroup</code>.</p>
</div>

###### TASK


```python

```
