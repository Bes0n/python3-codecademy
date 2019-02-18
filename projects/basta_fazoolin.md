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


