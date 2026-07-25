# Day 00

**Challenge name:** The Brochure
**Category:** OSINT <!-- OSINT / Web / Cloud / Forensics / AI Prompt Attacks / etc. -->
**Difficulty:** Easy
**Date completed:** 25th of July 2026

## Summary

This challenge is about reviewing the downloadable task file — in this case, a Byte Lotus Hotel brochure saved as a `.png` file. The clues to finding the flag are hidden somewhere in the brochure.

## Exploitation / Walkthrough

### Step 1

After opening the brochure, my initial thought was to zoom in and look for a watermark or any other clue. Finding nothing, I checked the file's properties to see if anything unusual would show up there. Needless to say, I came up short.

### Step 2

Then I remembered that this challenge is about **OSINT**, and specifically about using Social Media & Username Intelligence (**SOCMINT**) techniques. Looking at the brochure again, I noticed a clue that read: *"Find us on Instagram... or not."*

I opened Instagram and searched for **Byte Lotus Resort**, and found an account called **thebytelotusresort**. The account had 2 pictures uploaded as of 25th of July, but what caught my eye was that it followed exactly 1 other account.

### Step 3

<!-- INCLUDE AN IMAGE OF THE 1 FOLLOWER -->

I opened the account **veratheconcierge**, visible in the image above. This account had 3 posts, each containing a string of upper- and lower-case letters, numbers, and symbols:

- `VEhNe1YzckBzX2FD`
- `QzB1bnRfaDRzX2Iz`
- `M25fZjB1bmQhfQ==`

These three strings are Base64-encoded. Decoding each part and joining them together gives the flag:
| 1 | `VEhNe1YzckBzX2FD` | `THM{V3r@s_aC` |
| 2 | `QzB1bnRfaDRzX2Iz` | `C0unt_h4s_b3` |
| 3 | `M25fZjB1bmQhfQ==` | `3n_f0und!}` |

And voilà, there you have it!

## Flag(s)

```
THM{V3r@s_aCCount_h4s_b33n_f0und!}
```

## Lessons Learned

Key takeaway: OSINT is a powerful reminder that even a seemingly harmless marketing brochure can leak enough information (a stray hint, a linked social account) to lead straight to sensitive data. Always check the "small stuff" — social media follows, image metadata, and hidden text — before assuming a source is clean.
