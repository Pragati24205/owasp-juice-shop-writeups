# Challenge 9: Zero Stars

**Category:** Improper Input Validation  
**Severity:** Low

## Reason
Client-side input validation bypass with no direct user harm, degrades data integrity only.

## Methodology

After getting into the admin account, went to the contact section at `http://localhost:3000/#/contact`. There are three parameters in the UI: comment, rating, and captcha.

Submitted a legitimate feedback request and observed it in Burp:

![Feedback request parameters](../assets/09-zero-stars-1.png)

Sent the request to Burp Repeater and set the rating parameter to `0`.

![Zero rating submission](../assets/09-zero-stars-2.png)

Submitted the zero-rating comment and the challenge was solved.

![Zero stars in admin panel](../assets/09-zero-stars-3.png)

Going further, I also tested with negative integers and very large numbers to see how the application handles out-of-range values.

![Negative integer as rating](../assets/09-zero-stars-4.png)

![Large number as rating](../assets/09-zero-stars-5.png)

Both were accepted successfully.

![Response reflected in UI](../assets/09-zero-stars-6.png)

## Vulnerability Explanation

Comment details are sent via JSON to the server. By intercepting the feedback request in Burp, the rating parameter can be modified to any integer value before sending it to the server. The frontend restricts rating to 1-5 via UI controls, but the API performs no server-side validation on the rating field, allowing any integer value to be submitted directly.

## Impact

An attacker can send mass zero ratings and sabotage business operations, or manipulate ratings in the other direction to artificially flood 5-star reviews and boost products. An attacker can also send any integer value as a rating, making the feedback section meaningless as the rating system loses all integrity and becomes unreliable for users.
