<header>

<!--
  <<< Author notes: Course header >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  Add your open-source license. Recommended: MIT license.
-->

# Cracking Spectrum WiFi Passwords

_Learn how to build a wordlist and use Hashcat to crack default Spectrum WiFi passwords._

</header>

---

## Step 1: Understand the Target and Pattern

_Default Spectrum WiFi passwords follow a specific pattern._  

The target password pattern is: **[adjective][noun][ddd]**  
Example: `happydog422`

Spectrum passwords are lowercase and consist of:
- **6-character adjective**
- **4-character noun**
- **3-digit number**

We will generate a wordlist that combines adjectives, nouns, and three-digit numbers.

---

## Step 2: Generate Your Wordlist Using Hashcat `--stdout`

Hashcat's `--stdout` mode allows you to build the wordlist by combining multiple files._

### Activity: Generate the Wordlist

1. **Prepare your input files**:
   - [adjectives.txt](https://github.com/dark-marc/spectrum-password-cracking/blob/main/adjectives.txt): Contains all possible adjectives (e.g., happy, smart, tiny).  
   - [nouns.txt](https://github.com/dark-marc/spectrum-password-cracking/blob/main/nouns.txt): Contains all possible nouns (e.g., dog, bird, fish).  
   - [numbers.txt](https://github.com/dark-marc/spectrum-password-cracking/blob/main/numbers.txt): Contains all three-digit numbers from 000 to 999.

2. **Combine adjectives and nouns** to create a `combined_wordlist.txt`:
   ```bash
   hashcat --stdout adjectives.txt nouns.txt > combined_wordlist.txt

3. **Add three-digit numbers to complete the wordlist:**
    ```bash
    hashcat --stdout -a 1 combined_wordlist.txt numbers.txt > final_wordlist.txt

## Disclaimer

This information is for cybersecurity professionals only. Use it to test security on accounts and networks you own. Unauthorized password cracking is illegal and unethical. Always obtain permission before testing.

## How to Protect Your Spectrum Wifi from Password Cracking

To reduce the risk of your WiFi network being compromised, follow these steps:

   - Change your default WiFi network name (SSID): Default names like "MySpectrumWiFi" reveal the router type, making it easier for attackers to target you. Use a custom SSID instead.
   - Set a strong, unique WiFi password: Use a long passphrase with a mix of uppercase letters, lowercase letters, numbers, and symbols.
   - Avoid dictionary words or easily guessed combinations. Example: N3tw0rk!Secure#2025
