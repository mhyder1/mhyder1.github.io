# Acceptance Criteria

A user should be able to enter a valid email address and a password in the form input fields, and see that the submit button become active. The submit button should be disabled until the following criteria are met:

- The email address must be in a valid format. For the purposes of this exercise, a valid format looks like: example@mail.com, with a name of at least one character, followed by an @ symbol, followed by a domain of at least one character, followed by .com.

- The password must be at least 6 characters long.

- When the user is typing their password, it should obfuscate the characters they are entering so that it appears as “*” character.

- Before the login button is enabled, a user must check the "I am not a robot" checkbox. If that checkbox is not checked, the login button will remain disabled.

- Users can click the "hide/show" button inside of the password input to make the password appear instead of "*" characters. The user can toggle back and forth between the hide and show states, and will see the password input characters update accordingly.

- Once the submit button is active, it can be clicked and a user will be presented with a prompt that says “Login successful!”

- Finally, users can click the "clear form" prompt to clear the currently entered characters in the password and email inputs.