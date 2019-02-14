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
