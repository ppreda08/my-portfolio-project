# Notes – Authentication Attack

## Username Enumeration

The application responds differently depending on whether the username is valid or not.

* Invalid usernames → same response length
* Valid username → different response length

This allows attackers to identify valid accounts without knowing passwords.

---

## Password Brute Force

After identifying a valid username, password brute force becomes easier.

Key indicator:

* Status 200 → invalid login
* Status 302 → successful login (redirect)

---

## Key Observation

Small differences in:

* Response length
* Status code

can completely break authentication systems.

---

## Real World Impact

An attacker can:

* Discover valid users
* Gain unauthorized access
* Compromise accounts

---

## Prevention

* Same error messages for all cases
* Rate limiting
* Account lockout
* CAPTCHA
