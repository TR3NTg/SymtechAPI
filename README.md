# Refactoring Assessment

After looking through the code the assignment is a very close representation of what you get as a default visual studio web API.

The first problem I noticed was that threading was not implemented to support asynchronous tasks which is a problem for scalability in the future and causes blocking.
	- making every call asynchronous including the SQL server commands to ensure full asynchronization.
	- Changed the return types to Task and added system threading to the references.
	
The second thing that stood out when testing the API was the exceptions that would display in the response body if a request was not formatted correctly.
	- I implemented basic validation in all the method calls necessary, to validate account data i.e., name and number. Etc.

After this I was low on time but since this API is for bank accounts there would need to be some authorization involved.
The default web API authorization works okay with tokens however it would be easiest to create a new project with it already built in by deafult,
and then copy the existing code to it. The default route would be changed to api/auth instead of api/account since we already have an api/account route set up.
Once the account register and token authentication is working this API would now be a lot more secure and scalable for the future, and support more simultaneous traffic.