## Hacking The Fender
<div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW"><p><code>The Fender</code>, a notorious computer hacker and general villain of the people, has compromised several top-secret passwords including your own. Your mission, should you choose to accept it, is threefold. You must acquire access to <code>The Fender</code>'s systems, you must update his <code>"passwords.txt"</code> file to scramble the secret data. The last thing you need to do is add the signature of <code>Slash Null</code>, a different hacker whose nefarious deeds could be very conveniently halted by <code>The Fender</code> if they viewed <code>Slash Null</code> as a threat.</p>
<p>Use your knowledge of working with Python files to retrieve, manipulate, obscure, and create data in your quest for justice. Work with CSV files and other text files in this exploration of the strength of Python file programming.</p>
<p>If you get stuck during this project, check out the <strong>project walkthrough video</strong> which can be found at the bottom of the page after the final step of the project.</p>
</div>

### Reading In The Passwords
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Are you there? We've opened up a communications link to <code>The Fender</code>'s secret computer. We need you to write a program that will read in the compromised usernames and passwords that are stored in a file called <code>"passwords.csv"</code>.</p>
<p>First import the CSV module, since we'll be needing it to parse the data.</p>
</div>
* <p>We need to create a list of users whose passwords have been compromised, create a new list and save it to the variable <code>compromised_users</code>.</p>
* <p>Next we'll need you to open up the file itself. Store it in a file object called <code>password_file</code>.</p>
* <p>Pass the <code>password_file</code> object holder to our CSV reader for parsing. Save the parsed <code>csv.DictReader</code> object as <code>password_csv</code>.</p>
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Now we'll want to iterate through each of the lines in the CSV.</p>
<p>Create a for loop and save each row of the CSV into the temporary variable <code>password_row</code>.</p>
</div>
* <div class="spacing-tight__YTkj-JgyxXu1yRjOr_AFW narrativeMarkdown__1pqyNDZ_zljr-gC8Q1pur9"><p>Inside your <code>for</code> loop, print out <code>password_row['Username']</code>. This is the username of the person whose password was compromised.</p>
<p>Run your code, do you see a list of usernames?</p>
</div>
* 
