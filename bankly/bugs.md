1. BUG #1: In the User model, the getAll() function does not take any arguments. Removed username, password as arguments.

2. BUG #2: In the config.js file, the require('dotenv') is missing the config function. Changed it to require('dotenv').config()

3. BUG #3: In the app.js file, the module.exports = app is written twice. Removed the repitition.

4. BUG #4: In the server.js file, Express is listening for a PORT which has been configured in the config.js file but not used in the server.js file. Fixed that - imported PORT and used that to start server.

5. BUG #5: In the user.routes, for the patch route, removed "requireAdmin" this allows for any authenticated user to make changes to their own profile. Added a conditional to to allow admin to make changes.

6. BUG #6: In auth.js, payload needs to verify against the SECRET from config.js rather than itself. Changed the JWT to verify rather than decode.

<!-- ##### FOR RUNNING THE TESTS FOR BUG #5 & BUG #6 ##### -->

- Uncomment the "OLD CODE" and run the tests. Tests will fail due to the bugs!
- Comment OUT the "OLD CODE" and uncomment the replaced code and run the tests. Tests will pass!
