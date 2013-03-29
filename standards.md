# NewsApps standards

## Code style:

Write code at a 2nd-year coding level. This means that anyone who has been coding for a year or more should be able to read your code. Use if statements and for loops. Advanced language features (functional programming, meta-programming) should only be used in exceedingly rare situations. When used, the use of these advanced features should be clearly explained in neighboring comments. Do not use clever list comprehensions or functional programming solutions when simple if statements or for loops will suffice. Remember, DRY (don't repeat yourself), but don't confuse this with writing verbose code. You should write many similar functions instead of meta-programming. You should not copy-and-paste code. Write your code to be read.

Always write unit-tests before writing code (test-driven development). When finding a bug, write a test for that bug before fixing it. The only thing you do not have to write tests for is css and structural HTML. You should write unit tests for javascript, http requests & responses, cookies, sessions, backend code (database, apis), html forms.

All code uses 4 space soft-tabs:
- PHP
- Python
- HTML (and templates)
- CSS (and variants)
- YAML
- Config Files
- Javascript

Python code must pass pep8. There is a pep8 command available via brew that will check a file and tell you what needs to be fixed.

Document every python function and class:

	def myfunction(arg):
		"""
		my function does really neat stuff
		"""
		code

HTML must be indented to show nesting. Don't put a bunch of HTML in one line. Don't just let HTML end up where ever. Format it nicely, It'll make it easier to understand for yourself and others.

	<div>
		<ul>
			<li><a href="">link</a></li>
		</ul>
	</div>

## Git practices:

All repos must have at least two branches:
- Master. Where all leading edge development occurs. Tests should always pass.
- Stable. The code that is in production. Any commits on this branch must be pushed to production. Tests should always pass

Other branches:
If you are working on code that you want to push to the server for safe keeping, code that's not complete and not passing tests, create a new branch and publish that to the server. Name the branch something that describes the code (i.e. don't use your name or some other code words).

Prior to pushing code you must:
- Make sure you have committed.
- Make sure you have not committed any data dump files: sql dumps, initial_data.json. Fixtures and static data files that are used by the application are okay (test fixtures, kmls, shape files)
- Make sure you have not committed large binary files (photoshop files) or user uploaded media (blogs.dir, wordpress uploads).
- Pull code from the server (git pull)
- Resolve any merge conflicts. If the conflicts exist in compiled files (css if your using sass or less, js if your using coffee script), simply resave your files or rerun the compiler scripts.
- Run all tests. If any tests fail, it is your responsibility to resolve those bugs. If the tests that fail are not related to any code you worked on, connect to the folks who were working on that code last to decide who should fix the bugs. Those folks may have pushed the bugs and may be working on fixes.
- Push. Once all the tests pass, you can push your code.
