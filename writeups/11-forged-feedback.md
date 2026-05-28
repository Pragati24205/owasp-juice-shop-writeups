# Challenge 11: Forged Feedback

**Category:** Broken Access Control  
**Severity:** Medium

## Reason
Missing server-side user binding allows impersonation in feedback submission.

## Methodology

Went to the contact section and submitted legitimate feedback by clicking "Customer Feedback". Observed the request in Burp:

```json
{
  "UserId": 1,
  "captchaId": 2,
  "captcha": "33",
  "comment": "test-comment (***in@juice-sh.op)",
  "rating": 2
}
```
[!Forged feedback response](../assets/img-024.png)

Sent the above request to Burp Repeater and tried changing the `UserId` parameter to `2`.

![Forged feedback response](../assets/img-025.png)

It was a success.

![Forged feedback challenge solved](../assets/img-026.png)

## Vulnerability Explanation

When a person posts a comment, their details are sent to the server as a JSON document. Since no server-side checks are implemented, such as verifying the `userId` against the authenticated session's token, a person can post a comment from another user by intercepting the request and changing the `userId` to another user's ID.

## Impact

An attacker can impersonate any user and post defamatory or manipulative feedback under their identity. This can be used to damage a user's reputation, manipulate product ratings, or plant false evidence against a specific account.
