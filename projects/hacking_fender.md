## Hacking The Fender
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p><code>The Fender</code>, a notorious computer hacker and general villain of the people, has compromised several top-secret passwords including your own. Your mission, should you choose to accept it, is threefold. You must acquire access to <code>The Fender</code>'s systems, you must update his <code>"passwords.txt"</code> file to scramble the secret data. The last thing you need to do is add the signature of <code>Slash Null</code>, a different hacker whose nefarious deeds could be very conveniently halted by <code>The Fender</code> if they viewed <code>Slash Null</code> as a threat.</p>
<p>Use your knowledge of working with Python files to retrieve, manipulate, obscure, and create data in your quest for justice. Work with CSV files and other text files in this exploration of the strength of Python file programming.</p>
<p>If you get stuck during this project, check out the <strong>project walkthrough video</strong> which can be found at the bottom of the page after the final step of the project.</p>
</div>

### Reading In The Passwords
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Are you there? We've opened up a communications link to <code>The Fender</code>'s secret computer. We need you to write a program that will read in the compromised usernames and passwords that are stored in a file called <code>"passwords.csv"</code>.</p>
<p>First import the CSV module, since we'll be needing it to parse the data.</p>
</div>

*  <p>We need to create a list of users whose passwords have been compromised, create a new list and save it to the variable <code>compromised_users</code>.</p>
*  <p>Next we'll need you to open up the file itself. Store it in a file object called <code>password_file</code>.</p>

*  <p>Pass the <code>password_file</code> object holder to our CSV reader for parsing. Save the parsed <code>csv.DictReader</code> object as <code>password_csv</code>.</p>

*  <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Now we'll want to iterate through each of the lines in the CSV.</p>
<p>Create a for loop and save each row of the CSV into the temporary variable <code>password_row</code>.</p>
</div>

*  <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Inside your <code>for</code> loop, print out <code>password_row['Username']</code>. This is the username of the person whose password was compromised.</p>
<p>Run your code, do you see a list of usernames?</p>
</div>

* <p>Remove the <code>print</code> statement. We want to add each username to the list of <code>compromised_users</code>. Use the list's <code>.append()</code> method to add the username to <code>compromised_users</code> instead of printing them.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Exit out of your <code>with</code> block for <code>"passwords.csv"</code>. We have all the data we need from that file.</p>
<p>Start a new <code>with</code> block, opening a file called <code>compromised_users.txt</code>. Open this file in write-mode, saving the file object as <code>compromised_user_file</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Inside the new context-managed block opened by the <code>with</code> statement start a new <code>for</code> loop.</p>
<p>Iterate over each of your <code>compromised_users</code>.</p>
</div>

* <p>Write the username of each <code>compromised_user</code> in <code>compromised_users</code> to <code>compromised_user_file</code>.</p>

* <p>Exit out of that <code>with</code> block. You're doing great so far! We've got the data we need to employ as insurance against <code>The Fender</code>.</p>

### Notifying the Boss
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Your boss needs to know that you were successful in retrieving that compromised data. We'll need to send him an encoded message over the internet. Let's use JSON to do that.</p>
<p>First we'll need to import the <code>json</code> module.</p>
</div>

* <p>Open a new JSON file in write-mode called <code>boss_message.json</code>. Save the file object to the variable <code>boss_message</code>.</p>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Create a Python dictionary object within your <code>with</code> statement that relays a boss message. Call this <code>boss_message_dict</code>.</p>
<p>Give it a <code>"recipient"</code> key with a value <code>"The Boss"</code>.</p>
<p>Also give it a <code>"message"</code> key with the value <code>"Mission Success"</code>.</p>
</div>

* <p>Write out <code>boss_message_dict</code> to <code>boss_message</code> using <code>json.dump()</code>.</p>

### Scrambling the Password
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Now that we've safely recovered the compromised users we'll want to remove the <code>"passwords.csv"</code> file completely.</p>
<p>Create a new <code>with</code> block and open <code>"new_passwords.csv"</code> in write-mode. Save the file object to a variable called <code>new_passwords_obj</code>.</p>
</div>

* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Enemy of the people, <code>Slash Null</code>, is who we want <code>The Fender</code> to think was behind this attack. He has a signature, whenever he hacks someone he adds this signature to one of the files he touches. Here is the signature:</p>
<pre><span language="md" class="CodeBlock__1F3rKYW3tV11w2KEKvALNg wrap__1LR6hOLkoUYCHqQeJFO6HA defaults__1l9bk0Z91YqvzRByZKNgHF cc__1zsV8w8Rj_vs2ayVLJ-2x undefined"><div class="CodeMirror"> <span class="cm-hr">_  _     ___   __  ____             </span>
<!-- -->/<!-- --> <!-- -->)<!-- -->(<!-- --> <!-- -->\ <!-- --> <!-- --> <!-- -->/<!-- --> <span class="cm-strong">__</span><span class="cm-strong">)</span><span class="cm-strong"> </span><span class="cm-strong">/</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">\(</span><span class="cm-strong">_</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong em">_</span><span class="cm-strong em">)</span><span class="cm-strong em trailing-space-a"> </span><span class="cm-strong em trailing-space-b"> </span><span class="cm-strong em trailing-space-a"> </span><span class="cm-strong em trailing-space-b"> </span><span class="cm-strong em trailing-space-a"> </span><span class="cm-strong em trailing-space-b"> </span><span class="cm-strong em trailing-space-a"> </span><span class="cm-strong em trailing-space-b"> </span><span class="cm-strong em trailing-space-a"> </span><span class="cm-strong em trailing-space-b"> </span><span class="cm-strong em trailing-space-a"> </span><span class="cm-strong em trailing-space-new-line"> </span>
<span class="cm-strong em">)</span><span class="cm-strong em"> </span><span class="cm-strong em">\/</span><span class="cm-strong em"> </span><span class="cm-strong em">(</span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em">(</span><span class="cm-strong em"> </span><span class="cm-strong em">(</span><span class="cm-strong em">_</span><span class="cm-strong"> </span><span class="cm-strong">\(</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">O</span><span class="cm-strong"> </span><span class="cm-strong">)</span><span class="cm-strong"> </span><span class="cm-strong">)</span><span class="cm-strong">(</span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-new-line"> </span>
<span class="cm-strong">\_</span><span class="cm-strong em">___</span><span class="cm-em">/</span><span class="cm-em"> </span><span class="cm-em"> </span><span class="cm-em"> </span><span class="cm-em">\_</span><span class="cm-strong em">__</span><span class="cm-strong em">/</span><span class="cm-strong em"> </span><span class="cm-strong em">\_</span><span class="cm-strong em">_</span><span class="cm-strong">/</span><span class="cm-strong"> </span><span class="cm-strong">(</span><span class="cm-strong">__</span>)<span class="cm-trailing-space-a"> </span><span class="cm-trailing-space-b"> </span><span class="cm-trailing-space-a"> </span><span class="cm-trailing-space-b"> </span><span class="cm-trailing-space-a"> </span><span class="cm-trailing-space-b"> </span><span class="cm-trailing-space-a"> </span><span class="cm-trailing-space-b"> </span><span class="cm-trailing-space-a"> </span><span class="cm-trailing-space-b"> </span><span class="cm-trailing-space-a"> </span><span class="cm-trailing-space-b"> </span><span class="cm-trailing-space-new-line"> </span>
<!-- --> <span class="cm-hr">_  _   __    ___  __ _  ____  ____  </span>
<!-- -->/<!-- --> <!-- -->)<!-- -->(<!-- --> <!-- -->\ <!-- -->/<!-- --> <span class="cm-em">_</span><span class="cm-em">\ </span><span class="cm-em"> </span><span class="cm-em">/</span><span class="cm-em"> </span><span class="cm-strong em">__</span><span class="cm-strong em">)</span><span class="cm-strong em">(</span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em">/</span><span class="cm-strong em"> </span><span class="cm-strong em">)</span><span class="cm-strong em">(</span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em">__</span><span class="cm-strong em">)</span><span class="cm-strong em">(</span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em">\ </span>
<span class="cm-strong em">)</span><span class="cm-strong em"> </span><span class="cm-strong em">__</span><span class="cm-strong em"> </span><span class="cm-strong em">(</span><span class="cm-strong em">/</span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em">\(</span><span class="cm-strong em"> </span><span class="cm-strong em">(</span><span class="cm-strong em">__</span><span class="cm-em"> </span><span class="cm-em"> </span><span class="cm-em">)</span><span class="cm-em"> </span><span class="cm-em"> </span><span class="cm-em">(</span><span class="cm-em"> </span><span class="cm-em"> </span><span class="cm-em">)</span><span class="cm-em"> </span><span class="cm-em">_</span><span class="cm-em">)</span><span class="cm-em"> </span><span class="cm-em"> </span><span class="cm-em">)</span><span class="cm-em"> </span><span class="cm-em">D</span><span class="cm-em"> </span><span class="cm-em">(</span><span class="cm-em"> </span>
<span class="cm-em">\_</span><span class="cm-em">)</span><span class="cm-em">(</span><span class="cm-em">_</span>/<!-- -->\_<!-- -->/<!-- -->\_<!-- -->/<!-- --> <!-- -->\_<span class="cm-strong">__</span><span class="cm-strong">)</span><span class="cm-strong">(</span><span class="cm-strong">__</span>\_<!-- -->)<!-- -->(<span class="cm-strong em">___</span><span class="cm-strong em">_</span><span class="cm-strong">)</span><span class="cm-strong">(</span><span class="cm-strong em">___</span><span class="cm-em">_</span>/<!-- --> <!-- -->
<!-- -->        <span class="cm-strong em">___</span><span class="cm-strong em">_</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">__</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">__</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong em">___</span><span class="cm-strong em">_</span><span class="cm-strong"> </span><span class="cm-strong"> _</span><span class="cm-strong"> </span><span class="cm-strong"> _</span><span class="cm-strong"> </span>
<!-- --> <span class="cm-strong">___</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">/</span><span class="cm-strong"> </span><span class="cm-strong em">___</span><span class="cm-strong em">)</span><span class="cm-strong em">(</span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em">)</span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em"> </span><span class="cm-strong em">/</span><span class="cm-strong em"> </span><span class="cm-strong em">_</span><span class="cm-strong em">\ </span><span class="cm-strong em">/</span><span class="cm-strong em"> </span><span class="cm-strong em">___</span><span class="cm-strong em">)/</span><span class="cm-strong em"> </span><span class="cm-strong em">)</span><span class="cm-strong em">(</span><span class="cm-strong em"> </span><span class="cm-strong em">\</span>
<span class="cm-strong em">(</span><span class="cm-strong em">___</span>)<!-- --> <!-- --> <!-- -->\_<!-- -->__<!-- --> <!-- -->\/<!-- --> <!-- -->(<span class="cm-em">_</span><span class="cm-em">/</span><span class="cm-em">\/</span><span class="cm-em"> </span><span class="cm-em"> </span><span class="cm-em"> </span><span class="cm-em"> </span><span class="cm-em">\\</span><span class="cm-em">___</span> <!-- -->\)<!-- --> <!-- -->__<!-- --> <!-- -->(<!-- -->
<!-- -->       <!-- -->(<span class="cm-strong em">___</span><span class="cm-strong em">_</span><span class="cm-strong">/</span><span class="cm-strong">\_</span><span class="cm-strong em">___</span><span class="cm-em">/</span><span class="cm-em">\_</span><span class="cm-em">/</span><span class="cm-em">\_</span><span class="cm-em">/</span><span class="cm-em">(</span><span class="cm-strong em">___</span><span class="cm-strong em">_</span><span class="cm-strong em">/</span><span class="cm-strong em">\_</span><span class="cm-strong em">)</span><span class="cm-strong em">(</span><span class="cm-strong em">_</span><span class="cm-strong">/</span>
<!-- --> <span class="cm-hr">__ _  _  _  __    __                </span>
<span class="cm-strong">(</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">(</span><span class="cm-strong"> </span><span class="cm-strong">\/</span><span class="cm-strong"> </span><span class="cm-strong">)</span><span class="cm-strong">(</span><span class="cm-strong"> </span><span class="cm-strong">\(</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">)</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">(</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">)</span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-new-line"> </span>
<span class="cm-strong">/</span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong"> </span><span class="cm-strong">/)</span><span class="cm-strong"> </span><span class="cm-strong">\/</span><span class="cm-strong"> </span><span class="cm-strong">(</span><span class="cm-strong">/</span><span class="cm-strong"> </span><span class="cm-strong">(</span><span class="cm-strong em">_</span><span class="cm-strong em">/</span><span class="cm-strong em">\/</span><span class="cm-strong em"> </span><span class="cm-strong em">(</span><span class="cm-strong em">_</span><span class="cm-strong">/</span><span class="cm-strong">\ </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-b"> </span><span class="cm-strong trailing-space-a"> </span><span class="cm-strong trailing-space-new-line"> </span>
<span class="cm-strong">\_</span><span class="cm-strong">)</span><span class="cm-strong">__</span>)<!-- -->\_<span class="cm-strong em">___</span><span class="cm-strong em">/</span><span class="cm-strong em">\_</span><span class="cm-strong em">___</span>/<!-- -->\_<span class="cm-strong em">___</span><span class="cm-strong em">/</span></div></span></pre><p>Save that as a multiline string to the variable <code>slash_null_sig</code>.</p>
</div>

* <p>Write <code>slash_null_sig</code> to <code>new_passwords_obj</code>. Now we have the file to replace <code>passwords.csv</code> with!</p>

* <p>What an incredible success! We'll take care of moving the new passwords file over the old one in case you want to practice hacking <code>The Fender</code> in the future.</p>

```python
import csv, json

compromised_users = []

with open("passwords.csv") as password_file:
  password_csv = csv.DictReader(password_file)
  for password_row in password_csv:
    compromised_users.append(password_row['Username'])
    
with open("compromised_users.txt", "w") as compromised_user_file:
  for user in compromised_users:
    compromised_user_file.write(user)
    
with open("boss_message.json", "w") as boss_message:
  boss_message_dict = {"recipient" : "The Boss", "message" : "Mission Success"}
  json.dump(boss_message_dict, boss_message)
  
with open("new_passwords.csv", "w") as new_passwords_obj:
  slash_null_sig = """
 / )( \   / __) /  \(_  _)            
) \/ (  ( (_ \(  O ) )(              
\____/   \___/ \__/ (__)             
 _  _   __    ___  __ _  ____  ____  
/ )( \ / _\  / __)(  / )(  __)(    \ 
) __ (/    \( (__  )  (  ) _)  ) D ( 
\_)(_/\_/\_/ \___)(__\_)(____)(____/ 
        ____  __     __   ____  _  _ 
 ___   / ___)(  )   / _\ / ___)/ )( \
(___)  \___ \/ (_/\/    \\___ \) __ (
       (____/\____/\_/\_/(____/\_)(_/
 __ _  _  _  __    __                
(  ( \/ )( \(  )  (  )               
/    /) \/ (/ (_/\/ (_/\             
\_)__)\____/\____/\____/ 
  """
  new_passwords_obj.write(slash_null_sig)

```
