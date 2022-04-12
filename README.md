# Things I changed

    1. I have renamed the functions, so they explain what they do clearer and to make the code easier to read
    2. I removed accessing data via parent and replaced this with passing data via props. The reason for this is:
        - If the app was bigger and there was more data the component would get all data, even if it was not used in this component
        By using props, I am able to define the type of data that each component should receive which makes it easier for those wanting to know how to use the Number.vue component
        - It also meant that i could remove the watch function from the component as well.

    3. Changed the order of the numbers, so they are in ascending order. I did this in a computed function as it was amending the original structure of the data which was the max number on the input field.
    4. Ensured that the max number the user could input was 100.
    5. Removed the two query selectors on each of the functions as this loop was not the most efficient way, so I put the divisors in an array and used a method to define if each of the rendered numbers should have a range of classes on the element.

# Spec

Using Vue, display all numbers from 1 to 100 in a random order on the screen. This number should be configurable via a provided input box.
If the user places their pointer over a given number, highlight that numbers' divisors.
For example, if the user hovers over 21, the numbers 1, 3, 7 would be highlighted. 22 would highlight 1, 2 and 11.

# Interview Task

The provided code is functional, but it's got some issues that need to be resolved. These issues may or may not be logical in nature - just because the code is working doesn't necessarily mean it is the best way of doing something.

Improve the code how you see fit - please leave comments to justify your decisions.

# GitHub Pull Requests

This is an interview task sent to prospective candidates to work at Aluminati. As such, all pull requests will be rejected. This code is, by its very nature, purposely designed with issues that candiates are asked to review!

If you have been invited to perform this test your submission should be through your point of contact with us, e.g. your recruitment agency.
