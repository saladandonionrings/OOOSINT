>[!INFO]
>When a target platform or leak masks an email address (e.g., `t*******@g******`), your goal is to **confirm the provider**, **determine the character length**, and **cross-reference leaks** to find the missing characters.

# 1. Analyze the Masking Pattern
- **Fixed vs. Dynamic Masking:**
    - _Fixed:_ The platform always shows 7 asterisks regardless of the real length (e.g., `t*******@...`).
	    - *It is the case for : Discord, Amazon, Apple, PayPal*
    - _Dynamic:_ Every asterisk represents exactly one missing character. Count them to get the precise length of the username and domain.
	    - It is the case for : Twitter, Instagram, Yahoo, Spotify, Adobe

- **Domain Guessing:**
    - `g******` $\rightarrow$ Almost certainly `gmail.com` (5 letters after the 'g').
    - `h******` $\rightarrow$ Likely `hotmail.com` or `hotmail.fr`.
    - `o******` $\rightarrow$ Likely `outlook.com` or `orange.fr`.

# Test combination
- https://mailmeteor.com/email-permutator