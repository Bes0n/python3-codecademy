## The Nile
<p><code>The Nile</code> fullfilment agency brings everything you could possibly want straight to your door! Use your knowledge of Python functions and how to manipulate arguments to help automate practices for the biggest world-changing company.</p>

### Not Just A River In Egypt
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>At <em>The Nile</em> our biggest concern is our consumers, and our biggest cost is delivering their goods to them. We want to develop a program that will help us minimize these costs so we can continue making everyone happy.</p>
<p>First we'll need to calculate these costs using a function that you're going to write called <code>calculate_shipping_cost()</code>.</p>
<p>Give <code>calculate_shipping_cost</code> three parameters: <code>from_coords</code>, <code>to_coords</code>, and <code>shipping_type</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Both <code>from_coords</code> and <code>to_coords</code> are tuples, containing first the latitude and then the longitude. Since our <code>get_distance()</code> function looks for all four as separate arguments, we'll need to separate these variables out.</p>
<p>Inside <code>calculate_shipping_cost</code> unpack those tuples into <code>from_lat</code>, <code>from_long</code>, <code>to_lat</code>, and <code>to_long</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Now call <code>get_distance(from_lat, from_long, to_lat, to_long)</code> and save the result as <code>distance</code>.</p>
<p>There's other ways to separate those two coordinates when calling this function, how would you have done it?</p>
</div>

* <p>Next, get the <code>shipping_rate</code> by using the provided <code>SHIPPING_PRICES</code> dictionary and fetching the key passed in as <code>shipping_type</code>.</p>

* <p>Next, get the <code>shipping_rate</code> by using the provided <code>SHIPPING_PRICES</code> dictionary and fetching the key passed in as <code>shipping_type</code>.</p>

* <p>Calculate the <code>price</code> by multiplying the <code>distance</code> by the <code>shipping_rate</code>.</p>

* <p>Finally, return the formatted <code>price</code>, created by calling the provided <code>format_price()</code> on the price itself.</p>

* <p>What about our shoppers who hastily purchase goods without indicating their shipping type? Let's give our function a default argument for <code>shipping_type</code>. Since they're in such a hurry let's make the default argument <code>'Overnight'</code>. They'll be happier to get what they ordered earlier, and we'll be happier because they paid more money for it. It's a win-win!</p>

* <p>Want to make sure you wrote the function correctly? Try calling <code>test_function(calculate_shipping_cost)</code> after your function definition.</p>

### Careers At The Nile
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>At The Nile, we have a joke. Without our fantastic drivers, who fulfill orders every day, we'd just be sitting with millions of toys, electronics, and clothing in warehouses to ourselves.</p>
<p>Our team is important, and we want to make sure the hardest workers find their home in our careers. In order to do that, we need to figure out who the best person is for each job.</p>
<p>Write a function called <code>calculate_driver_cost()</code> with <code>distance</code> as the first parmameter, and as many drivers as are available as positional arguments after that, as <code>drivers</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>In order to find the best person, we need to calculate how much it would cost for any of the drivers to fulfill this order.</p>
<p>Create two new variables, <code>cheapest_driver</code> and <code>cheapest_driver_price</code>. Set them both to <code>None</code>.</p>
</div>

* <p>Now let's iterate over every <code>driver</code> in <code>drivers</code>. Use a <code>for</code> loop.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Now we want to check if the current <code>driver</code> is the cheapest driver we've looked at.</p>
<p>First, we'll check if <code>cheapest_driver</code> is <code>None</code>, this likely means this is the first driver we've looked at.</p>
<p>In that case, set <code>cheapest_driver</code> equal to <code>driver</code> and then set <code>cheapest_driver_price</code> equal to <code>price_for_driver</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>In an <code>elif</code> statment, check if <code>price_for_driver</code> is less than <code>cheapest_driver_price</code>. This means that our current driver is cheaper than the driver stored in <code>cheapest_driver</code>.</p>
<p>Update <code>cheapest_driver</code> to be equal to <code>driver</code> and update <code>cheapest_driver_price</code> to be equal to <code>price_for_driver</code>.</p>
</div>

* <p>After outdenting out of our <code>elif</code> statement and the <code>for</code> loop, return <code>cheapest_driver_price</code> and <code>cheapest_driver</code>.</p>

### The Nile Exclusive
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Great first day, friend! Let's try and figure out all the money you've saved us today.</p>
<p>Let's define a function called <code>calculate_money_made()</code>.</p>
<p>This function will be passed a number of Trip IDs with corresponding trip information as arguments, so let's just take any keyword arguments passed into it. Store them all as <code>trips</code>!</p>
</div>

* <p>Let's start a counter at <code>0</code>. Create a variable called <code>total_money_made</code> that will count up for us.</p>

* <p>Iterate through every trip_id and trip in the <code>trips</code> dictionary.</p>

* <p>Calculate the trip revenue into the variable <code>trip_revenue</code> by calculating <code>trip.cost</code> minus <code>trip.driver.cost</code>.</p>

* <p>Add up that sweet revenue by incrementing <code>total_money_made</code> by <code>trip_revenue</code>.</p>

* <p>Outside your for loop, return the total!</p>

* <p>Congratulations! You've been a real life-saver around these parts. We broke up functions using arbitrary and default parameters! Remember you can test your function by calling <code>test_function(calculate_money_made)</code> afterwards!</p>

```python 

from nile import get_distance, format_price, SHIPPING_PRICES
from test import test_function

# Define calculate_shipping_cost() here:
def calculate_shipping_cost(from_coords, to_coords, shipping_type='Overnight'):
  from_lat, from_long = from_coords
  to_lat, to_long = to_coords
  distance = get_distance(*from_coords,*to_coords)
  shipping_rate = SHIPPING_PRICES[shipping_type]
  price = distance * shipping_rate
  return format_price(price)

# Test the function by calling 
#test_function(calculate_shipping_cost)

# Define calculate_driver_cost() here
def calculate_driver_cost(distance,*drivers):
  cheapest_driver = None
  cheapest_driver_price = None
  for driver in drivers:
    driver_time = driver.speed * distance
    price_for_driver = driver.salary * driver_time
    if cheapest_driver is None:
      cheapest_driver = driver
      cheapest_driver_price = price_for_driver
    elif price_for_driver < cheapest_driver_price:
      cheapest_driver = driver
      cheapest_driver_price = price_for_driver
  return cheapest_driver_price, cheapest_driver
      

# Test the function by calling 
#test_function(calculate_driver_cost)

# Define calculate_money_made() here
def calculate_money_made(**trips):
  total_money_made = 0 
  for trid_id,trip in trips.items():
    trip_revenue = trip.cost - trip.driver.cost
    total_money_made += trip_revenue
  return total_money_made

# Test the function by calling 
test_function(calculate_money_made)


```
