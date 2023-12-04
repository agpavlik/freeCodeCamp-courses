# Telephone Number Validator

Return `true` if the passed string looks like a valid US phone number. The user may fill out the form field any way they choose as long as it has the format of a valid US number. The following are examples of valid formats for US numbers (refer to the tests below for other variants):

```
555-555-5555
(555)555-5555
(555) 555-5555
555 555 5555
5555555555
1 555 555 5555
```

For this challenge you will be presented with a string such as `800-692-7753` or `8oo-six427676;laskdjf`. Your job is to validate or reject the US phone number based on any combination of the formats provided above. The area code is required. If the country code is provided, you must confirm that the country code is 1. Return `true` if the string is a valid US phone number; otherwise return `false`.

> Answer variant 1

```javascript
function telephoneCheck(str) {
  // Define the regular expression pattern for valid US phone numbers
  const regex = /^(1\s?)?(\(\d{3}\)|\d{3})([\s\-]?)\d{3}([\s\-]?)\d{4}$/;

  // Test the input string against the pattern
  return regex.test(str);
}
```

Explanation:

- ^: Asserts the start of the string.
- (1\s?)?: Matches an optional "1" followed by an optional space.
- (\(\d{3}\)|\d{3}): Matches either three digits within parentheses or three consecutive digits.
- ([\s\-]?): Matches an optional space or hyphen.
- \d{3}: Matches exactly three digits.
- ([\s\-]?): Matches another optional space or hyphen.
- \d{4}: Matches exactly four digits.
- $: Asserts the end of the string.
- Uses the test method of the regular expression (regex) to check if the input string (str) matches the specified pattern.
- Returns true if the string is a valid US phone number and false otherwise.

> Answer variant 2

```javascript
function telephoneCheck(str) {
  // Count the number of digits in the string
  const digitCount = str.replace(/\D/g, "").length;

  // Check if the string starts with "1" (country code) and has 10 or 11 digits
  if ((str.startsWith("1") && digitCount === 11) || digitCount === 10) {
    // Check for valid formats using explicit conditions
    if (
      /^\d{10}$/.test(str) || // 5555555555
      /^1?\s?\d{3}[-\s]?\d{3}[-\s]?\d{4}$/.test(str) ||
      // 555-555-5555, (555)555-5555, (555) 555-5555, 555 555 5555, 1 555 555 5555
      /^1?\s?\(\d{3}\)\s?\d{3}[-\s]?\d{4}$/.test(str)
      // (555)555-5555, (555) 555-5555
    ) {
      return true;
    }
  }

  // If none of the conditions are met, return false
  return false;
}
```
