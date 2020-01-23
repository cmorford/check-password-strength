# Overview
A simple way to check that password strength of a certain passphrase. A password strength checker based from [Javascript RegEx](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions).

## Installation

    npm i check-password-strength

## Setup & Basic Usage

```
const { passwordStrength } = require('check-password-strength')

console.log(passwordStrength(asdfasdf))
// Weak (It wiill return weak if the value doesn't match the RegEx conditions)
console.log(passwordStrength(asdfasdf2020))
// Medium
console.log(passwordStrength(A@2asdF2020!!*))
// Strong
```
## Additional Info

**Strong Password RegEx used:** `^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!@#\$%\^&\*])(?=.{8,})`
**Medium Password RegEx used:** `^(((?=.*[a-z])(?=.*[A-Z]))|((?=.*[a-z])(?=.*[0-9]))|((?=.*[A-Z])(?=.*[0-9])))(?=.{6,})"`

|RegEx| Desc. |
|--|--|
| ^ | The password string will start this way |
| (?=.*[a-z]) | The string must contain at least 1 lowercase alphabetical character |
|(?=.*[A-Z]) | The string must contain at least 1 uppercase alphabetical character
|(?=.*[0-9]) | The string must contain at least 1 numeric character
|(?=._[!@#\$%\^&_]) | The string must contain at least one special character, but we are escaping reserved RegEx characters to avoid conflict
| (?=.{8,}) | The string must be eight characters or longer


Credits to Nic Raboy for his awesome [blog!](https://www.thepolyglotdeveloper.com/2015/05/use-regex-to-test-password-strength-in-javascript/).

Feel free to clone or fork this project: `https://github.com/deanilvincent/check-password-strength.git`

### License
This project is licensed under the MIT License - see the  [LICENSE.md]([https://github.com/deanilvincent/check-password-strength/blob/master/LICENSE.md](https://github.com/deanilvincent/check-password-strength/blob/master/LICENSE.md))  file for details.