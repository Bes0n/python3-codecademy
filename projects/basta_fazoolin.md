## BASTA FAZOOLIN
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>You've started position as the lead programmer for the family-style Italian restaurant  <em>Basta Fazoolin' with My Heart</em>. The restaurant has been doing fantastically and seen a lot of growth lately. You've been hired to keep things organized.</p>
<p>If you get stuck during this project, check out the <strong>project walkthrough video</strong> which can be found at the bottom of the page after the final step of the project.</p>
</div>

### Making the Menus

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>At <em>Basta Fazoolin' with my Heart</em> our motto is simple: when you're here with family, that's great! We have four different menus: brunch, early-bird, dinner, and kids.</p>
<p>Create a <code>Menu</code> class .</p>
</div>

* <p>Give <code>Menu</code> a constructor with the five parameters <code>self</code>, <code>name</code>, <code>items</code>, <code>start_time</code>, and <code>end_time</code>.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Let's create our first menu: <code>brunch</code>. Brunch is served from 11am to 4pm. The following items are sold during brunch:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined lang-py" language="lang-py"><div class="CodeMirror">{<!-- -->
<!-- -->  <!-- --><span class="cm-string">'pancakes'</span>:<!-- --> <!-- --><span class="cm-number">7.50</span>, <span class="cm-string">'waffles'</span>: <span class="cm-number">9.00</span>, <span class="cm-string">'burger'</span>: <span class="cm-number">11.00</span>, <span class="cm-string">'home fries'</span>: <span class="cm-number">4.50</span>, <span class="cm-string">'coffee'</span>: <span class="cm-number">1.50</span>, <span class="cm-string">'espresso'</span>: <span class="cm-number">3.00</span>, <span class="cm-string">'tea'</span>: <span class="cm-number">1.00</span>, <span class="cm-string">'mimosa'</span>: <span class="cm-number">10.50</span>, <span class="cm-string">'orange juice'</span>: <span class="cm-number">3.50</span>
}</div></span></pre>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Let's create our second menu item <code>early_bird</code>. Early-bird Dinners are served from 3pm to 6pm. The following items are available during the early-bird menu:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined lang-py" language="lang-py"><div class="CodeMirror">{<!-- -->
<!-- -->  <!-- --><span class="cm-string">'salumeria plate'</span>:<!-- --> <!-- --><span class="cm-number">8.00</span>, <span class="cm-string">'salad and breadsticks (serves 2, no refills)'</span>: <span class="cm-number">14.00</span>, <span class="cm-string">'pizza with quattro formaggi'</span>: <span class="cm-number">9.00</span>, <span class="cm-string">'duck ragu'</span>: <span class="cm-number">17.50</span>, <span class="cm-string">'mushroom ravioli (vegan)'</span>: <span class="cm-number">13.50</span>, <span class="cm-string">'coffee'</span>: <span class="cm-number">1.50</span>, <span class="cm-string">'espresso'</span>: <span class="cm-number">3.00</span>,
}</div></span></pre>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Let's create our third menu, <code>dinner</code>. Dinner is served from 5pm to 11pm. The following items are available for dinner:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined lang-py" language="lang-py"><div class="CodeMirror">{<!-- -->
<!-- -->  <!-- --><span class="cm-string">'crostini with eggplant caponata'</span>:<!-- --> <!-- --><span class="cm-number">13.00</span>, <span class="cm-string">'ceaser salad'</span>: <span class="cm-number">16.00</span>, <span class="cm-string">'pizza with quattro formaggi'</span>: <span class="cm-number">11.00</span>, <span class="cm-string">'duck ragu'</span>: <span class="cm-number">19.50</span>, <span class="cm-string">'mushroom ravioli (vegan)'</span>: <span class="cm-number">13.50</span>, <span class="cm-string">'coffee'</span>: <span class="cm-number">2.00</span>, <span class="cm-string">'espresso'</span>: <span class="cm-number">3.00</span>,
}</div></span></pre>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>And let's create our last menu, <code>kids</code>. The kids menu is available from 11am until 9pm. The following items are available on the kids menu.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined lang-py" language="lang-py"><div class="CodeMirror">{<!-- -->
<!-- -->  <!-- --><span class="cm-string">'chicken nuggets'</span>:<!-- --> <!-- --><span class="cm-number">6.50</span>, <span class="cm-string">'fusilli with wild mushrooms'</span>: <span class="cm-number">12.00</span>, <span class="cm-string">'apple juice'</span>: <span class="cm-number">3.00</span>
}</div></span></pre>
</div>

* <p>Give our <code>Menu</code> class a string representation method that will tell you the <code>name</code> of the menu. Also, indicate in this representation when the menu is available.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Try out our string representation. If you call <code>print(brunch)</code> it should print out something like the following:</p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">brunch<!-- --> <!-- -->menu<!-- --> <!-- -->available<!-- --> <!-- -->from<!-- --> <!-- -->11am<!-- --> <!-- -->to<!-- --> <!-- -->4pm<!-- --></div></span></pre></div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Give <code>Menu</code> a method <code>.calculate_bill()</code> that has two parameters: <code>self</code>, and <code>purchased_items</code>, a list of the names of purchased items.</p>
<p>Have <code>calculate_bill</code> return the total price of a purchase consisiting of all the items in <code>purchased_items</code>.</p>
</div>

* <p>Test out <code>Menu.calculate_bill()</code>. We have a breakfast order for one order of pancakes, one order of home fries, and one coffee. Pass that into <code>brunch.calculate_bill()</code> and print out the price.</p>

* <p>What about an early-bird purchase? Our last guests ordered the salumeria plate and the vegan mushroom ravioli. Calculate the bill with <code>.caluclate_bill()</code>.</p>

### Creating the Franchises

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p><em>Basta Fazoolin' with my Heart</em> has seen tremendous success with the family market, which is fantastic because when you're at <em>Basta Fazoolin' with my Heart</em> with family, that's great!</p>
<p>We've decided to create more than one restaurant to offer our fantastic menus, services, and ambience around the country.</p>
<p>First, let's create a <code>Franchise</code> class.</p>
</div>

* <p>Give the <code>Franchise</code> class a constructor. Take in an <code>address</code>, and assign it to <code>self.address</code>. Also take in a list of <code>menus</code> and assign it to <code>self.menus</code>.</p>

* <p>Let's create our first two franchises! Our flagship store is located at <code>"1232 West End Road"</code> and our new installment is located at <code>"12 East Mulberry Street"</code>. Pass in all four menus along with these addresses to define <code>flagship_store</code> and <code>new_installment</code>.</p>

* <p>Give our <code>Franchise</code>s a string represenation so that we'll be able to tell them apart. If we print out a <code>Franchise</code> it should tell us the address of the restaurant.</p>

* <p>Let's tell our customers what they can order! Give <code>Franchise</code> an <code>.available_menus()</code> method that takes in a <code>time</code> parameter and returns a list of the <code>Menu</code> objects that are available at that time.</p>

* <p>Let's test out our <code>.available_menus()</code> method! Call it with 12 noon as an argument and print out the results.</p>

* <p>Let's do another test! If we call <code>.available_menus()</code> with 5pm as an argument and print out the results.</p>

### Creating Businesses!
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Since we've been so successful building out a branded chain of restaurants, we've decided to diversify. We're going to create a restaurant that sells arepas!</p>
<p>First let's define a <code>Business</code> class.</p>
</div>

* <p>Give <code>Business</code> a constructor. A <code>Business</code> needs a <code>name</code> and a list of <code>franchises</code>.</p>

* <p>Let's create our first <code>Business</code>. The name is <code>"Basta Fazoolin' with my Heart"</code> and the two franchises are <code>flagship_store</code> and <code>new_installment</code>.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Before we create our new business, we'll need a <code>Franchise</code> and before our <code>Franchise</code> we'll need a menu. The items for our <em>Take a' Arepa</em> available from 10am until 8pm are the following:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined lang-py" language="lang-py"><div class="CodeMirror">{<!-- -->
<!-- -->  <!-- --><span class="cm-string">'arepa pabellon'</span>:<!-- --> <!-- --><span class="cm-number">7.00</span>, <span class="cm-string">'pernil arepa'</span>: <span class="cm-number">8.50</span>, <span class="cm-string">'guayanes arepa'</span>: <span class="cm-number">8.00</span>, <span class="cm-string">'jamon arepa'</span>: <span class="cm-number">7.50</span>
}</div></span></pre>
<p>Save this to a variable called <code>arepas_menu</code>.</p>
</div>

* <p>Next let's create our first <em>Take a' Arepa</em> franchise! Our new restaurant is located at <code>"189 Fitzgerald Avenue"</code>. Save the <code>Franchise</code> object to a variable called <code>arepas_place</code>.</p>

* 

```python 
class Business:
  def __init__(self, name, franchises):
    self.name = name
    self.franchises = franchises

class Franchise:
  def __init__(self, address, menus):
    self.address = address
    self.menus = menus
  def __repr__(self):
    return "Address of the restaurant: {address}".format(address=self.address)
  def available_menus(self, time):
    self.time = time
    print("For this time current menu(s) available:")
    for available_menu in self.menus:
      if time >= available_menu.start_time and time <= available_menu.end_time:
        print("{menu}".format(menu=available_menu))

  
class Menu:
  def __init__(self, name, items, start_time, end_time):
    self.name = name
    self.items = items
    self.start_time = start_time
    self.end_time = end_time
    
  def calculate_bill(self, purchased_items):
    self.purchased_item = purchased_items
    bill = 0
    for keys, values in self.items.items():
      for item in purchased_items:
        if item in keys:
          bill += values
    return bill
    
  def __repr__(self):
    return "Name of the menu: {name}. Available: from {start_time} to {end_time}".format(name=self.name, start_time=self.start_time, end_time = self.end_time)
  
  
brunch_items = {
  'pancakes': 7.50, 'waffles': 9.00, 'burger': 11.00, 'home fries': 4.50, 'coffee': 1.50, 'espresso': 3.00, 'tea': 1.00, 'mimosa': 10.50, 'orange juice': 3.50
}
early_bird_items = {
  'salumeria plate': 8.00, 'salad and breadsticks (serves 2, no refills)': 14.00, 'pizza with quattro formaggi': 9.00, 'duck ragu': 17.50, 'mushroom ravioli (vegan)': 13.50, 'coffee': 1.50, 'espresso': 3.00,
}
dinner_items = {
  'crostini with eggplant caponata': 13.00, 'ceaser salad': 16.00, 'pizza with quattro formaggi': 11.00, 'duck ragu': 19.50, 'mushroom ravioli (vegan)': 13.50, 'coffee': 2.00, 'espresso': 3.00,
}
kids_items = {
  'chicken nuggets': 6.50, 'fusilli with wild mushrooms': 12.00, 'apple juice': 3.00
}


brunch_menu = Menu('Brunch', brunch_items, 1100, 1600)
early_bird_menu = Menu("Early Bird", early_bird_items, 1500, 1800)
dinner_menu = Menu("Dinner", dinner_items, 1700, 2300)
kids_menu = Menu("Kids", kids_items, 1100, 2100)


menus = [brunch_menu, early_bird_menu, dinner_menu, kids_menu]

flagship_store = Franchise("1232 West End Road", menus)
new_installment = Franchise("12 East Mulberry Street", menus)


franchises = [flagship_store, new_installment]

first_business = Business("Basta Fazoolin' with my Heart", franchises)

#print(first_business.franchises)
#Arepa 
arepas_items = {
  'arepa pabellon': 7.00, 'pernil arepa': 8.50, 'guayanes arepa': 8.00, 'jamon arepa': 7.50
}

arepas_menu = Menu("Take a'Arepa", arepas_items, 1000,2000)
arepas_place = Franchise("189 Fitzgerald Avenue12 East Mulberry Street", [arepas_menu])
arepa_business = Business("Take a' Arepa", [arepas_place])

print(arepa_business.franchises[0].menus[0].items)
#print(flagship_store.available_menus(1200))
#print(flagship_store.available_menus(1700))
#print(brunch_menu.calculate_bill(['pancakes', 'home fries', 'coffee']))
#print(early_bird_menu.calculate_bill(['salumeria plate', 'mushroom ravioli (vegan)']))



```
