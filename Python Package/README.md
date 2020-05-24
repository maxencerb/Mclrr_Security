# Python Security Package
This version for python is under MIT license. Please review it on [github](https://github.com/maxencerb/Mclrr_Security/blob/master/LICENSE).
Before using it you have to know that it only supports password between 6 and 20 characters in the normal ascii table **Ascii Code between 32 and 126** (included)
Python >= 3.6 is recommended
## Intallation
Simply run this command for the latest version (pip required)

	pip install Mclrr-Security

For the version 1.0.1 or any specific version, run :

	pip install Mclrr-Security==1.0.1
## How to use ?
 First, import the package and declare a variable for the class to use it in your project easily

	from Mclrr_Security import py_mclrr_security
	security = py_mclrr_security()
Then, you can start using it :

	hash = security.Encode('bonjour')
	print(hash)
	# Output: coosvvtYn2]sdwJtYj_uhbUo plrAo<\l2EfBr:?k{Zv-K)1'r
	test = security.Check_Password(hash, 'bonjour')
	print(test)
	# Output : True
	test = security.Check_Password(hash, 'boojour')
	print(test)
	# Output : False
## Example
You can use this package with your favorite python Framework for webservices or softwares such as Flask or Django. I'm gonna write a quick example of a user model using this package. First I assume that I will use a DataBase for my user. You can create your daatabase in the main file and just import it from this file :

	from app import db
The interest of using this package is to secure the user passwords even though there is a security problem with your database. Then we can start creating our User Model.

	# Imports
	...
	from Mclrr_Security import py_mclrr_security
	
	security = py_mclrr_security()

	class User():
		
		id = db.Column(db.Integer(), primary_key = True)
		username = db.Column(db.String(length = 32))
		email = db.Column(db.String(length = 64), unique = True)
		password = db.Column(db.String(length = 64))

		def __repr__(self):
			return self.username + ' ' + self.email

		def __init__(self, username, email, password):
			if User.query.get(email = email):
				throw Exception('Account with this email already exists')
			try:
				self.password = security.Encode(password)
			catch:
				throw Exception('Password is not correctly formatted')
			self.username = username
			self.email = email

		def Set_Email(self, email):
			if User.query.get(email = email):
				throw Exception('Account with this email already exists')
			self.email = email

		def Set_Username(self, username):
			self.username = username

		def Set_Password(self, old_password, password):
			if not Check_Password(old_password):
				throw Exception('Incorrect password')
			try:
				self.password = security.Encode(password)
			catch:
				throw Exception('Password is not correctly formatted')
				
		def Check_Password(self, password):
			return security.Check_Password(self.password, password)

	...

As you can see this package can throw errors. It throws errors for two reasons. First yout password has to be formatted such as :

	# length between 6 and 20
	test = 5 < len(password) < 21

	# characters has to be in the Ascii table with ascii code between 32 and 126
	ascii_table = """ !"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~"""
	if test:
		for c in password:
			if c not in ascii_table:
				test = false
				break
	
	if not test:
		throw Exception('Password is not Correctly formatted')

**This data validation is in the package**, so if you call the Encode function, you don't have to worry about any errors and you can catch it to send an error message back to the user.

To **Save time and ressources** in the execution, you can simply do a data validation directly on the login form in JS using these conditions to minimize the number of requests.
## Issues and requests
If you have any issues or request concerning this package feel free to [email me](mailto:maxenceraballand00@gmail.com?subject=Mclrr%20Security%20package%20python%20v1.0.1).
