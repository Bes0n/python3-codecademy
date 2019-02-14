## FILES
### Reading a File
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Computers use file systems to store and retrieve data. Each file is an individual container of related information. If you've ever saved a document, downloaded a song, or even sent an email you've created a file on some computer somewhere. Even <strong>script.py</strong>, the Python program you're editing in the learning environment, is a file.</p>
<p>So, how do we interact with files using Python? We're going to learn how to read and write different kinds of files using code. Let's say we had a file called <strong>real_cool_document.txt</strong> with these contents:</p>
<p><strong>real_cool_document.txt</strong></p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">Wowsers! <span class="cm-comment">```</span>

<span class="cm-comment">We</span><span class="cm-comment"> </span><span class="cm-comment">could</span><span class="cm-comment"> </span><span class="cm-comment">read</span><span class="cm-comment"> </span><span class="cm-comment">that</span><span class="cm-comment"> </span><span class="cm-comment">file</span><span class="cm-comment"> </span><span class="cm-comment">like</span><span class="cm-comment"> </span><span class="cm-comment">this</span><span class="cm-comment">:</span>

<span class="cm-comment">*</span><span class="cm-comment">*</span><span class="cm-comment">script.py</span><span class="cm-comment">*</span><span class="cm-comment">*</span>
<span class="cm-comment">```py</span>
<span class="cm-comment">with open('real_cool_document.txt') as cool_doc:</span>
  <span class="cm-comment">cool_contents = cool_doc.read()</span>
<span class="cm-comment">print(cool_contents)</span></div></span></pre><p>This opens a file object called <code>cool_doc</code> and creates a new indented block where you can read the contents of the opened file. We then read the contents of the file <code>cool_doc</code> using <code>cool_doc.read()</code> and save the resulting string into the variable <code>cool_contents</code>. Then we print <code>cool_contents</code>, which outputs the statement <code>Wowsers!</code>.</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Use <code>with</code> to open the file <strong>welcome.txt</strong>. Save the file object as <code>text_file</code>.</p>
</div>

* <p>Read the contents of <code>text_file</code> and save the results in <code>text_data</code>.</p>

* <p>Print out <code>text_data</code>.</p>

```python 
with open("welcome.txt") as text_file:
  text_data = text_file.read()
print(text_data)
```

### Iterating Through Lines
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>When we read a file, we might want to grab the whole document in a single string, like <code>.read()</code> would return. But what if we wanted to store each line in a variable? We can use the <code>.readlines()</code> function to read a text file line by line instead of having the whole thing. Suppose we have a file:</p>
<p><strong>keats_sonnet.txt</strong></p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">To one who has been long in city pent,
’Tis very sweet to look into the fair
And open face of heaven,—to breathe a prayer
Full in the smile of the blue firmament.</div></span></pre><p><strong>script.py</strong></p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-string">'keats_sonnet.txt'</span>) <span class="cm-keyword">as</span> <span class="cm-variable">keats_sonnet</span>:
  <span class="cm-keyword">for</span> <span class="cm-variable">line</span> <span class="cm-keyword">in</span> <span class="cm-variable">keats_sonnet</span>.<span class="cm-property">readlines</span>():
    <span class="cm-builtin">print</span>(<span class="cm-variable">line</span>)</div></span></pre>
<p>The above script creates a temporary file object called <code>keats_sonnet</code> that points to the file <strong>keats_sonnet.txt</strong>. It then iterates over each line in the document and prints the entire file out.</p>
</div>

###### TASK
* <p>Using a <code>with</code> statement, create a file object pointing to the file <strong>how_many_lines.txt</strong>. Store that file object in the variable <code>lines_doc</code>.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Iterate through each of the lines in <code>lines_doc.readlines()</code> using a <code>for</code> loop.</p>
<p>Inside the for loop print out each line of <strong>how_many_lines.txt</strong>.</p>
</div>

```python
with open("how_many_lines.txt") as lines_doc:
  for lines in lines_doc.readlines():
    print(lines)
```

### Reading a Line
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Sometimes you don't want to iterate through a whole file. For that, there's a different file method, <code>.readline()</code>, which will only read a single line at a time. If the entire document is read line by line in this way subsequent calls to <code>.readline()</code> will not throw an error but will start returning an empty string (<code>""</code>). Suppose we had this file:</p>
<p><strong>millay_sonnet.txt</strong></p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">I shall forget you presently, my dear,
So make the most of this, your little day,
Your little month, your little half a year,
Ere I forget, or die, or move away,</div></span></pre><p><strong>script.py</strong></p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-string">'millay_sonnet.txt'</span>) <span class="cm-keyword">as</span> <span class="cm-variable">sonnet_doc</span>:
  <span class="cm-variable">first_line</span> <span class="cm-operator">=</span> <span class="cm-variable">sonnet_doc</span>.<span class="cm-property">readline</span>()
  <span class="cm-variable">second_line</span> <span class="cm-operator">=</span> <span class="cm-variable">sonnet_doc</span>.<span class="cm-property">readline</span>()
  <span class="cm-builtin">print</span>(<span class="cm-variable">second_line</span>)</div></span></pre>
<p>This script also creates a file object called <code>sonnet_doc</code> that points to the file <strong>millay_sonnet.txt</strong>. It then reads in the first line using <code>sonnet_doc.readline()</code> and saves that to the variable <code>first_line</code>. It then saves the second line (<code>So make the most of this, your little day,</code>) into the variable <code>second_line</code> and then prints it out. </p>
</div>

###### TASK 
* <p>Using a <code>with</code> statement, create a file object pointing to the file <strong>just_the_first.txt</strong>. Store that file object in the variable <code>first_line_doc</code>.</p>

* <p>Save the first line of <strong>just_the_first.txt</strong> into the variable <code>first_line</code>.</p>

* <p>Print out the variable <code>first_line</code>.</p>
```python
with open("just_the_first.txt") as first_line_doc:
  first_line = first_line_doc.readline()
  
print(first_line)
```

### Writing a File
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Reading a file is all well and good, but what if we want to create a file of our own? With Python we can do just that. It turns out that our <code>open()</code> function that we're using to open a file to read needs another argument to open a file to write to.</p>
<p><strong>script.py</strong></p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-string">'generated_file.txt'</span>, <span class="cm-string">'w'</span>) <span class="cm-keyword">as</span> <span class="cm-variable">gen_file</span>:
  <span class="cm-variable">gen_file</span>.<span class="cm-property">write</span>(<span class="cm-string">"What an incredible file!"</span>)</div></span></pre>
<p>Here we pass the argument <code>'w'</code> to <code>open()</code> in order to indicate to open the file in write-mode. The default argument is <code>'r'</code> and passing <code>'r'</code> to <code>open()</code> opens the file in read-mode as we've been doing.</p>
<p>This code creates a new file in the same folder as <em>script.py</em> and gives it the text <code>What an incredible file!</code>. It's important to note that if there is already a file called <em>generated_file.txt</em> it will completely overwrite that file, erasing whatever its contents were before.</p>
</div>

###### TASK
* <p>Create a file object for the file <strong>bad_bands.txt</strong> using the <code>open()</code> function with the <code>w</code> argument. Assign this object to the temporary variable <code>bad_bands_doc</code>.</p>

* <p>Use the <code>bad_bands_doc.write()</code> method to add the name of a musical group you dislike to the document <code>bad_bands</code>.</p>

```python 
with open("bad_bands.txt", "w") as bad_bands_doc:
  bad_bands = bad_bands_doc.write("No Such Bands")
```

### Appending to a File
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>So maybe completely deleting and overwriting existing files is something that bothers you. Isn't there a way to just add a line to a file without completely deleting it? Of course there is! Instead of opening the file using the argument <code>'w'</code> for write-mode, we open it with <code>'a'</code> for append-mode. If we have a generated file with the following contents:</p>
<p><strong>generated_file.txt</strong></p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">This was a popular file...</div></span></pre><p>Then we can add another line to that file with the following code:</p>
<p><strong>script.py</strong></p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-string">'generated_file.txt'</span>, <span class="cm-string">'a'</span>) <span class="cm-keyword">as</span> <span class="cm-variable">gen_file</span>:
  <span class="cm-variable">gen_file</span>.<span class="cm-property">write</span>(<span class="cm-string">"... and it still is"</span>)</div></span></pre>
<p>In the code above we open a file object in the temporary variable <code>gen_file</code>. This variable points to the file <em>generated_file.txt</em> and, since it's open in append-mode, adds the line <code>... and it still is</code> as a new line to the file. If you were to open the file after running the script it would look like this:</p>
<p><strong>generated_file.txt</strong></p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">This was a popular file...
... and it still is</div></span></pre><p>Notice that opening the file in append-mode, with <code>'a'</code> as an argument to <code>open()</code>, means that using the file object's <code>.write()</code> method <em>appends</em> whatever is passed to the end of the file in a new line. If we were to run <strong>script.py</strong> again, this would be what <strong>generated_file.txt</strong> looks like:</p>
<p><strong>generated_file.txt</strong></p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">This was a popular file...
... and it still is
... and it still is</div></span></pre><p>Notice that we've appended <code>"... and it still is"</code> to the file a second time! This is because in <strong>script.py</strong> we opened <strong>generated_file.txt</strong> in append-mode.</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>We've got a file, <strong>cool_dogs.txt</strong>, filled with all the cool dogs we know. Somehow while compiling this list we forgot about one very cool dog. Let's fix that problem by adding him to our <strong>cool_dogs.txt</strong>.</p>
<p>Open up our file <strong>cool_dogs.txt</strong> in append-mode and assign it to the file object <code>cool_dogs_file</code>.</p>
</div>

* <p>Inside your <code>with</code> block, add "Air Buddy" to <strong>cool_dogs.txt</strong>. Air Buddy is a Golden Retriever that plays basketball, which more than qualifies him for this list.</p>

```python 
with open("cool_dogs.txt", "a") as cool_dogs_file:
  cool_dogs_file.write("Air Buddy")
```

### What's With "with"?
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>We've been opening these files with this <code>with</code> block so far, but it seems a little weird that we can only use our file variable in the indented block. Why is that? The <code>with</code> keyword invokes something called a <em>context manager</em> for the file that we're calling <code>open()</code> on. This context manager takes care of opening the file when we call <code>open()</code> and then closing the file after we leave the indented block.</p>
<p>Why is closing the file so complicated? Well, most other aspects of our code deal with things that Python itself controls. All the variables you create: integers, lists, dictionaries — these are all Python objects, and Python knows how to clean them up when it's done with them. Since your files exist <em>outside</em> your Python script, we need to tell Python when we're done with them so that it can close the connection to that file. Leaving a file connection open unnecessarily can affect performance or impact other programs on your computer that might be trying to access that file.</p>
<p>The <code>with</code> syntax replaces older ways to access files where you need to call <code>.close()</code> on the file object manually. We can still open up a file and append to it with the old syntax, as long as we remember to close the file connection afterwards.</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">fun_cities_file</span> <span class="cm-operator">=</span> <span class="cm-builtin">open</span>(<span class="cm-string">'fun_cities.txt'</span>, <span class="cm-string">'a'</span>)

<span class="cm-comment"># We can now append a line to "fun_cities".</span>
<span class="cm-variable">fun_cities_file</span>.<span class="cm-property">write</span>(<span class="cm-string">"Montréal"</span>)

<span class="cm-comment"># But we need to remember to close the file</span>
<span class="cm-variable">fun_cities_file</span>.<span class="cm-property">close</span>()</div></span></pre>
<p>In the above script we added "Montréal" as a new line in our file <strong>fun_cities.txt</strong>. However, since we used the older-style syntax, we had to remember to close the file afterwards. Since this is necessarily more verbose (requires at least one more line of code) without being any more expressive, using <code>with</code> is preferred.</p>
</div>

###### TASK
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In <strong>script.py</strong> there's a file object that doesn't get closed correctly. Let's fix it by changing the syntax!</p>
<p>Remove this line:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">close_this_file</span> <span class="cm-operator">=</span> <span class="cm-builtin">open</span>(<span class="cm-string">'fun_file.txt'</span>)</div></span></pre>
<p>And change it to use the <code>with</code> syntax from our previous exercises.</p>
<p>Remember to indent the rest of the body so that we don't get an <code>IndentError</code>.</p>
</div>

```python
with open("fun_file.txt") as close_this_file:
  setup = close_this_file.readline()
  punchline = close_this_file.readline()

print(setup)

```

### What Is a CSV File?
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Text files aren't the only thing that Python can read, but they're the only thing that we don't any need additional parsing library to understand. CSV files are an example of a text file that impose a structure to their data. CSV stands for <em>Comma-Separated Values</em> and CSV files are usually the way that data from spreadsheet software (like Microsoft Excel or Google Sheets) is exported into a portable format. A spreadsheet that looks like the following</p>
<div>

<table>
<thead>
<tr>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody><tr>
<td>Roger Smith</td>
<td>rsmith</td>
<td><a href="mailto:wigginsryan@yahoo.com">wigginsryan@yahoo.com</a></td>
</tr>
<tr>
<td>Michelle Beck</td>
<td>mlbeck</td>
<td><a href="mailto:hcosta@hotmail.com">hcosta@hotmail.com</a></td>
</tr>
<tr>
<td>Ashley Barker</td>
<td>a_bark_x</td>
<td><a href="mailto:a_bark_x@turner.com">a_bark_x@turner.com</a></td>
</tr>
<tr>
<td>Lynn Gonzales</td>
<td>goodmanjames</td>
<td><a href="mailto:lynniegonz@hotmail.com">lynniegonz@hotmail.com</a></td>
</tr>
<tr>
<td>Jennifer Chase</td>
<td>chasej</td>
<td><a href="mailto:jchase@ramirez.com">jchase@ramirez.com</a></td>
</tr>
<tr>
<td>Charles Hoover</td>
<td>choover</td>
<td><a href="mailto:choover89@yahoo.com">choover89@yahoo.com</a></td>
</tr>
<tr>
<td>Adrian Evans</td>
<td>adevans</td>
<td><a href="mailto:adevans98@yahoo.com">adevans98@yahoo.com</a></td>
</tr>
<tr>
<td>Susan Walter</td>
<td>susan82</td>
<td><a href="mailto:swilliams@yahoo.com">swilliams@yahoo.com</a></td>
</tr>
<tr>
<td>Stephanie King</td>
<td>stephanieking</td>
<td><a href="mailto:sking@morris-tyler.com">sking@morris-tyler.com</a></td>
</tr>
<tr>
<td>Erika Miller</td>
<td>jessica32</td>
<td><a href="mailto:ejmiller79@yahoo.com">ejmiller79@yahoo.com</a></td>
</tr>
<tr>
<td></td></tr></tbody></table></div>
<td></td>
<td></td>

<tr>
<td><br></td>
<td></td>
<td></td>
</tr>

<p>In a CSV file that same exact data would be rendered like this:</p>
<p><strong>users.csv</strong></p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">Name,Username,Email
Roger Smith,rsmith,wigginsryan@yahoo.com
Michelle Beck,mlbeck,hcosta@hotmail.com
Ashley Barker,a_bark_x,a_bark_x@turner.com
Lynn Gonzales,goodmanjames,lynniegonz@hotmail.com
Jennifer Chase,chasej,jchase@ramirez.com
Charles Hoover,choover,choover89@yahoo.com
Adrian Evans,adevans,adevans98@yahoo.com
Susan Walter,susan82,swilliams@yahoo.com
Stephanie King,stephanieking,sking@morris-tyler.com
Erika Miller,jessica32,ejmiller79@yahoo.com</div></span></pre><p>Notice that the first row of the CSV file doesn't actually represent any data, just the labels of the data that's present in the rest of the file. The rest of the rows of the file are the same as the rows in the spreadsheet software, just instead of being separated into different cells they're separated by… well I suppose it's fair to say they're separated by commas.</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p> CSV files are just plain text files! </p>
<p>Open <code>logger.csv</code> using our standard <code>with</code> syntax, saving the file object in the temporary variable <code>log_csv_file</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Print out the contents of <code>logger.csv</code> by calling <code>.read()</code> on the file. Notice that it is parsed as a string.</p>
</div>

```python
with open("logger.csv") as log_csv_file:
  print(log_csv_file.read())
```

### Reading a CSV File
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Recall our CSV file from our last exercise:</p>
<p><strong>users.csv</strong></p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">Name,Username,Email
Roger Smith,rsmith,wigginsryan@yahoo.com
Michelle Beck,mlbeck,hcosta@hotmail.com
Ashley Barker,a_bark_x,a_bark_x@turner.com
Lynn Gonzales,goodmanjames,lynniegonz@hotmail.com</div></span></pre><p>Even though we can read these lines as text without a problem, there are ways to access the data in a format better suited for programming purposes. In Python we can convert that data into a dictionary using the <code>csv</code> library's <code>DictReader</code> object. Here's how we'd create a list of the email addresses of all of the users in the above table:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">import</span> <span class="cm-variable">csv</span>

<span class="cm-variable">list_of_email_addresses</span> <span class="cm-operator">=</span> []
<span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-string">'users.csv'</span>, <span class="cm-variable">newline</span><span class="cm-operator">=</span><span class="cm-string">''</span>) <span class="cm-keyword">as</span> <span class="cm-variable">users_csv</span>:
  <span class="cm-variable">user_reader</span> <span class="cm-operator">=</span> <span class="cm-variable">csv</span>.<span class="cm-property">DictReader</span>(<span class="cm-variable">users_csv</span>)
  <span class="cm-keyword">for</span> <span class="cm-variable">row</span> <span class="cm-keyword">in</span> <span class="cm-variable">user_reader</span>:
    <span class="cm-variable">list_of_email_addresses</span>.<span class="cm-property">append</span>(<span class="cm-variable">row</span>[<span class="cm-string">'Email'</span>])</div></span></pre>
<p>In the above code we first import our <code>csv</code> library, which gives us the tools to parse our CSV file. We then create the empty list <code>list_of_email_addresses</code> which we'll later populate with the email addresses from our CSV. Then we open the <strong>users.csv</strong> file with the temporary variable <code>users_csv</code>. </p>
<p>We pass the additional keyword argument <code>newline=''</code> to the file opening <code>open()</code> function so that we don't accidentally mistake a line break in one of our data fields as a new row in our CSV (read more about this in <a href="https://docs.python.org/3/library/csv.html#id3" target="_blank">the Python documentation</a>).</p>
<p>After opening our new CSV file we use <code>csv.DictReader(users_csv)</code> which converts the lines of our CSV file to Python dictionaries which we can use access methods for. The keys of the dictionary are, by default, the entries in the first line of our CSV file. Since our CSV's first line calls the third field in our CSV "<code>Email</code>", we can use that as the key in each row of our DictReader.</p>
<p>When we iterate through the rows of our <code>user_reader</code> object, we access all of the rows in our CSV as dictionaries (except for the first row, which we used to label the keys of our dictionary). By accessing the <code>'Email'</code> key of each of these rows we can grab the email address in that row and append it to our <code>list_of_email_addresses</code>.</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Import the <code>csv</code> module.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Open up the file <strong>cool_csv.csv</strong> in the temporary variable <code>cool_csv_file</code>.</p>
</div>

* <p>Using <code>csv.DictReader</code> read the contents of <code>cool_csv_file</code> into a new variable called <code>cool_csv_dict</code>.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p><strong>cool_csv.csv</strong> includes a cool fact about every person in the CSV.</p>
<p>For each row in <code>cool_csv_dict</code> print out that row's <code>"Cool Fact"</code>.</p>
</div>

```python
import csv

with open('cool_csv.csv') as cool_csv_file:
  cool_csv_dict = csv.DictReader(cool_csv_file)
  for row in cool_csv_dict:
    print(row['Cool Fact'])
```

### Reading Different Types of CSV Files
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>I need to level with you, I've been lying to you for the past two exercises. Well, kind of. We've been acting like CSV files are Comma-Separated Values files. It's true that CSV stands for that, but it's also true that other ways of separating values are valid CSV files these days. </p>
<p>People used to call Tab-Separated Values files TSV files, but as other separators grew in popularity everyone realized that creating a new <code>.[a-z]sv</code> file format for every value-separating character used is not sustainable. </p>
<p>So we call all files with a list of different values a CSV file and then use different <em>delimiters</em> (like a comma or tab) to indicate where the different values start and stop. </p>
<p>Let's say we had an address book. Since addresses usually use commas in them, we'll need to use a different delimiter for our information.     Since none of our data has semicolons (<code>;</code>) in them, we can use those.</p>
<p><strong>addresses.csv</strong></p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror">Name;Address;Telephone
Donna Smith;126 Orr Corner Suite 857\nEast Michael, LA 54411;906-918-6560
Aaron Osborn;6965 Miller Station Suite 485\nNorth Michelle, KS 64364;815.039.3661x42816
Jennifer Barnett;8749 Alicia Vista Apt. 288\nLake Victoriaberg, TN 51094;397-796-4842x451
Joshua Bryan;20116 Stephanie Stravenue\nWhitneytown, IA 87358;(380)074-6173
Andrea Jones;558 Melissa Keys Apt. 588\nNorth Teresahaven, WA 63411;+57(8)7795396386
Victor Williams;725 Gloria Views Suite 628\nEast Scott, IN 38095;768.708.3411x954</div></span></pre><p>Notice the <code>\n</code> character, this is the escape sequence for a new line. The possibility of a new line escaped by a <code>\n</code> character in our data is why we pass the <code>newline=''</code> keyword argument to the <code>open()</code> function.</p>
<p>Also notice that many of these addresses have commas in them! This is okay, we'll still be able to read it. If we wanted to, say, print out all the addresses in this CSV file we could do the following:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">import</span> <span class="cm-variable">csv</span>

<span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-string">'addresses.csv'</span>, <span class="cm-variable">newline</span><span class="cm-operator">=</span><span class="cm-string">''</span>) <span class="cm-keyword">as</span> <span class="cm-variable">addresses_csv</span>:
  <span class="cm-variable">address_reader</span> <span class="cm-operator">=</span> <span class="cm-variable">csv</span>.<span class="cm-property">DictReader</span>(<span class="cm-variable">addresses_csv</span>, <span class="cm-variable">delimiter</span><span class="cm-operator">=</span><span class="cm-string">';'</span>)
  <span class="cm-keyword">for</span> <span class="cm-variable">row</span> <span class="cm-keyword">in</span> <span class="cm-variable">address_reader</span>:
    <span class="cm-builtin">print</span>(<span class="cm-variable">row</span>[<span class="cm-string">'Address'</span>])</div></span></pre>
<p>Notice that when we call <code>csv.DictReader</code> we pass in the <code>delimiter</code> parameter, which is the string that's used to delineate separate fields in the CSV. We then iterate through the CSV and print out each of the addresses.</p>
</div>

###### TASK
* <p>Import the <code>csv</code> module.</p>

* <p>Open up the file <strong>books.csv</strong> in the variable <code>books_csv</code>.</p>

* <p>Create a <code>DictReader</code> instance that uses the <code>@</code> symbol as a delimiter to read <code>books_csv</code>. Save 
the result in a variable called <code>books_reader</code>.</p>

* <p>Create a list called <code>isbn_list</code>, iterate through <code>books_csv</code> to get the ISBN number of every book in the CSV file. Use the <code>['ISBN']</code> key for the dictionary objects passed to it.</p>

```python
import csv

with open("books.csv") as books_csv:
  isbn_list = []
  books_reader = csv.DictReader(books_csv, delimiter='@')
  for row in books_reader:
    isbn_list.append(row['ISBN'])
```

### Writing a CSV File
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Naturally if we have the ability to read different CSV files we might want to be able to programmatically create CSV files that save output and data that someone could load into their spreadsheet software. Let's say we have a big list of data that we want to save into a CSV file. We could do the following:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">big_list</span> <span class="cm-operator">=</span> [{<span class="cm-string">'name'</span>: <span class="cm-string">'Fredrick Stein'</span>, <span class="cm-string">'userid'</span>: <span class="cm-number">6712359021</span>, <span class="cm-string">'is_admin'</span>: <span class="cm-keyword">False</span>}, {<span class="cm-string">'name'</span>: <span class="cm-string">'Wiltmore Denis, '</span><span class="cm-variable">userid</span><span class="cm-string">': 2525942, '</span><span class="cm-variable">is_admin</span><span class="cm-string">': False}, {'</span><span class="cm-variable">name</span><span class="cm-string">': '</span><span class="cm-variable">Greely</span> <span class="cm-variable">Plonk</span><span class="cm-string">', '</span><span class="cm-variable">userid</span><span class="cm-string">': 15890235, '</span><span class="cm-variable">is_admin</span><span class="cm-string">': False}, {'</span><span class="cm-variable">name</span><span class="cm-string">': '</span><span class="cm-variable">Dendris</span> <span class="cm-variable">Stulo</span><span class="cm-string">', '</span><span class="cm-variable">userid</span><span class="cm-string">': 572189563, '</span><span class="cm-variable">is_admin</span><span class="cm-string">': True}] </span>

<span class="cm-keyword">import</span> <span class="cm-variable">csv</span>

<span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-string">'output.csv'</span>, <span class="cm-string">'w'</span>) <span class="cm-keyword">as</span> <span class="cm-variable">output_csv</span>:
  <span class="cm-variable">fields</span> <span class="cm-operator">=</span> [<span class="cm-string">'name'</span>, <span class="cm-string">'userid'</span>, <span class="cm-string">'is_admin'</span>]
  <span class="cm-variable">output_writer</span> <span class="cm-operator">=</span> <span class="cm-variable">csv</span>.<span class="cm-property">DictWriter</span>(<span class="cm-variable">output_csv</span>, <span class="cm-variable">fieldnames</span><span class="cm-operator">=</span><span class="cm-variable">fields</span>)

  <span class="cm-variable">output_writer</span>.<span class="cm-property">writeheader</span>()
  <span class="cm-keyword">for</span> <span class="cm-variable">item</span> <span class="cm-keyword">in</span> <span class="cm-variable">big_list</span>:
    <span class="cm-variable">output_writer</span>.<span class="cm-property">writerow</span>(<span class="cm-variable">item</span>)</div></span></pre>
<p>In our code above we had a set of dictionaries with the same keys for each, a prime candidate for a CSV. We import the <code>csv</code> library, and then open a new CSV file in write-mode by passing the <code>'w'</code> argument to the <code>open()</code> function. </p>
<p>We then define the fields we're going to be using into a variable called <code>fields</code>. We then instantiate our CSV writer object and pass two arguments. The first is <code>output_csv</code>, the file handler object. The second is our list of fields <code>fields</code> which we pass to the keyword parameter <code>fieldnames</code>.</p>
<p>Now that we've instantiated our CSV file writer, we can start adding lines to the file itself! First we want the headers, so we call <code>.writeheader()</code> on the writer object. This writes all the fields passed to <code>fieldnames</code> as the first row in our file. Then we iterate through our <code>big_list</code> of data. Each <code>item</code> in <code>big_list</code> is a dictionary with each field in <code>fields</code> as the keys. We call <code>output_writer.writerow()</code> with the <code>item</code> dictionaries which writes each line to the CSV file.</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>We have a list in the workspace <code>access_log</code> which is a list of dictionaries we want to write out to a CSV file.</p>
<p>Let's start by importing the <code>csv</code> module.</p>
</div>

* <p>Open up the file <strong>logger.csv</strong> in the temporary variable <code>logger_csv</code>. Don't forget to open the file in write-mode.</p>

* <p>Create a <code>csv.DictWriter</code> instance called <code>log_writer</code>. Pass <code>logger_csv</code> as the first argument and then <code>fields</code> as a keyword argument to the keyword <code>fieldnames</code>.</p>

* <p>Write the header to <code>log_writer</code> using the <code>.writeheader()</code> method.</p>

* <p>Iterate through the <code>access_log</code> list and add each element to the CSV using <code>log_writer.writerow()</code>.</p>


```python
access_log = [{'time': '08:39:37', 'limit': 844404, 'address': '1.227.124.181'}, {'time': '13:13:35', 'limit': 543871, 'address': '198.51.139.193'}, {'time': '19:40:45', 'limit': 3021, 'address': '172.1.254.208'}, {'time': '18:57:16', 'limit': 67031769, 'address': '172.58.247.219'}, {'time': '21:17:13', 'limit': 9083, 'address': '124.144.20.113'}, {'time': '23:34:17', 'limit': 65913, 'address': '203.236.149.220'}, {'time': '13:58:05', 'limit': 1541474, 'address': '192.52.206.76'}, {'time': '10:52:00', 'limit': 11465607, 'address': '104.47.149.93'}, {'time': '14:56:12', 'limit': 109, 'address': '192.31.185.7'}, {'time': '18:56:35', 'limit': 6207, 'address': '2.228.164.197'}]
fields = ['time', 'address', 'limit']

import csv

with open("logger.csv", "w") as logger_csv:
  log_writer = csv.DictWriter(logger_csv, fieldnames = fields)
  log_writer.writeheader()
  for items in access_log:
    log_writer.writerow(items)
```

### Reading a JSON File
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>CSV isn't the only file format that Python has a built-in library for. We can also use Python's file tools to read and write JSON. JSON, an abbreviation of JavaScript Object Notation, is a file format inspired by the programming language JavaScript. The name, like CSV is a bit of a misnomer — some JSON is not valid JavaScript (and plenty of JavaScript is not valid JSON).</p>
<p>JSON's format is endearingly similar to Python dictionary syntax, and so JSON files might be easy to read from a Python developer standpoint. Nonetheless, Python comes with a <code>json</code> package that will help us parse JSON files into actual Python dictionaries. Suppose we have a JSON file like the following:</p>
<p><strong>purchase_14781239.json</strong></p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-js" language="js"><div class="CodeMirror">{
  <span class="cm-string">'user'</span>: <span class="cm-string">'ellen_greg'</span>,
  <span class="cm-string">'action'</span>: <span class="cm-string">'purchase'</span>,
  <span class="cm-string">'item_id'</span>: <span class="cm-string">'14781239'</span>,
}</div></span></pre>
<p>We would be able to read that in as a Python dictionary with the following code:</p>
<p><strong>json_reader.py</strong></p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">import</span> <span class="cm-variable">json</span>

<span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-string">'purchase_14781239.json'</span>) <span class="cm-keyword">as</span> <span class="cm-variable">purchase_json</span>:
  <span class="cm-variable">purchase_data</span> <span class="cm-operator">=</span> <span class="cm-variable">json</span>.<span class="cm-property">load</span>(<span class="cm-variable">purchase_json</span>)

<span class="cm-builtin">print</span>(<span class="cm-variable">purchase_data</span>[<span class="cm-string">'user'</span>])
<span class="cm-comment"># Prints 'ellen_greg'</span></div></span></pre>
<p>First we import the <code>json</code> package. We opened the file using our trusty <code>open()</code> command. Since we're opening it in read-mode we just need to pass the file name. We save the file in the temporary variable <code>purchase_json</code>. </p>
<p>We continue by parsing <code>purchase_json</code> using <code>json.load()</code>, creating a Python dictionary out of the file. Saving the results into <code>purchase_data</code> means we can interact with it. We print out one of the values of the JSON file by keying into the <code>purchase_data</code> object.</p>
</div>

###### TASK
* <p>Let's read a JSON file! Start by importing the <code>json</code> module.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Open up the file <strong>message.json</strong>, saving the file object to the variable <code>message_json</code>. </p>
<p>Open the file in read-mode, without passing any additional arguments to <code>open()</code>.</p>
</div>

* <p>Pass the JSON file object as an argument to <code>json.load()</code> and save the resulting Python dictionary as <code>message</code>.</p>

* <p>Print out <code>message['text']</code>.</p>

```python
import json

with open("message.json") as message_json:
  message = json.load(message_json)
  
print(message['text'])
```

### Writing a JSON File
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Naturally we can use the <code>json</code> library to translate Python objects to JSON as well. This is especially useful in instances where you're using a Python library to serve web pages, you would also be able to serve JSON. Let's say we had a Python dictionary we wanted to save as a JSON file:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-variable">turn_to_json</span> <span class="cm-operator">=</span> {
  <span class="cm-string">'eventId'</span>: <span class="cm-number">674189</span>,
  <span class="cm-string">'dateTime'</span>: <span class="cm-string">'2015-02-12T09:23:17.511Z'</span>,
  <span class="cm-string">'chocolate'</span>: <span class="cm-string">'Semi-sweet Dark'</span>,
  <span class="cm-string">'isTomatoAFruit'</span>: <span class="cm-keyword">True</span>
}</div></span></pre>
<p>We'd be able to create a JSON file with that information by doing the following:</p>
<pre><span class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined language-py" language="py"><div class="CodeMirror"><span class="cm-keyword">import</span> <span class="cm-variable">json</span>

<span class="cm-keyword">with</span> <span class="cm-builtin">open</span>(<span class="cm-string">'output.json'</span>, <span class="cm-string">'w'</span>) <span class="cm-keyword">as</span> <span class="cm-variable">json_file</span>:
  <span class="cm-variable">json</span>.<span class="cm-property">dump</span>(<span class="cm-variable">turn_to_json</span>, <span class="cm-variable">json_file</span>)</div></span></pre>
<p>We import the <code>json</code> module, open up a write-mode file under the variable <code>json_file</code>, and then use the <code>json.dump()</code> method to write to the file. <code>json.dump()</code> takes two arguments: first the data object, then the file object you want to save.</p>
</div>

###### TASK
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>In your workspace we've put dictionary called <code>data_payload</code>. We want to save this to a file called <strong>data.json</strong>.</p>
<p>Let's start by importing the <code>json</code> library.</p>
</div>

* <p>Open a new file object in the variable <code>data_json</code>. The filename should be <code>'data.json'</code> and the file should be opened in write-mode.</p>

* <p>Call <code>json.dump()</code> with <code>data_payload</code> and <code>data_json</code> to convert our data to JSON and then save it to the file <strong>data.json</strong>.</p>

```python
data_payload = [
  {'interesting message': 'What is JSON? A web application\'s little pile of secrets.',
   'follow up': 'But enough talk!'}
]

import json

with open("data.json", "w") as data_json:
  json.dump(data_payload, data_json)
```

### Review
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p>Now you know all about files! You were able to:</p>
<ul>
<li>Open up file objects using <code>open()</code> and <code>with</code>.</li>
<li>Read a file's full contents using Python's <code>.read()</code> method.</li>
<li>Read a file line-by-line using <code>.readline()</code> and <code>.readlines()</code></li>
<li>Create new files by opening them in write-mode.</li>
<li>Append to a file non-destructively by opening a file in append-mode.</li>
<li>Apply all of the above to different types of data-carrying files including CSV and JSON!</li>
</ul>
<p>You have all the skills necessary to read, write, and update files programmatically, a very useful skill in the Python universe!</p>
</div>
