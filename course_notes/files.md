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

```python 
with open('welcome.txt') as text_file:
  text_data = text_file.read()
```
