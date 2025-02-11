# Javascript

## JavaScript: The Fun Side of the Web!

JavaScript is like the magic wand of web development. It's a programming language that lets you add life and excitement to your websites.

Imagine your web page as a static painting hanging on a wall. Nice, but a bit dull, right? Now, sprinkle some JavaScript, and **voila!** You get a lively canvas that can:
- Chat with you
- Show real-time updates
- Create interactive maps
- Play cool animations
- Even turn into a jukebox with all your favorite tunes

In short, whenever you see a web page doing fancy tricks beyond just showing words and pictures, _JavaScript_ is the wizard behind the curtain making it happen!

## Date Class

You can create a `Date` object using the `Date` constructor:

```javascript

// Current date and time
let currentDate = new Date();

// Specific date and time
let specificDate = new Date('January 13, 2025 08:45:00');

// Date from milliseconds since January 1, 1970
let dateFromMilliseconds = new Date(1672531200000);

// Specifying year, month, day, hour, minute, second, and millisecond
let detailedDate = new Date(2025, 0, 13, 8, 45, 0, 0); // Note: January is month 0```
```

### Methods of the Date Class

#### Getting Date and Time Components

-    `getDate()`: Returns the day of the month (1-31).
-    `getDay()`: Returns the day of the week (0-6), where 0 is Sunday.
-    `getFullYear()`: Returns the four-digit year.
-    `getMonth()`: Returns the month (0-11), where 0 is January.
-    `getHours()`: Returns the hour (0-23).
-    `getMinutes()`: Returns the minutes (0-59).
-    `getSeconds()`: Returns the seconds (0-59).
-    `getMilliseconds()`: Returns the milliseconds (0-999).
-    `getTime()`: Returns the number of milliseconds since January 1, 1970.

#### Setting Date and Time Components

-    `setDate(day)`: Sets the day of the month.
-    `setFullYear(year, month, day)`: Sets the full year, and optionally month and day.
-    `setMonth(month, day)`: Sets the month, and optionally day.
-    `setHours(hour, min, sec, ms)`: Sets the hour, and optionally minutes, seconds, and milliseconds.
-    `setMinutes(min, sec, ms)`: Sets the minutes, and optionally seconds and milliseconds.
-    `setSeconds(sec, ms)`: Sets the seconds, and optionally milliseconds.
-    `setMilliseconds(ms)`: Sets the milliseconds.
-    `setTime(milliseconds)`: Sets the date and time by milliseconds since January 1, 1970.

#### Formatting and Parsing

-    `toDateString()`: Returns the date portion of a `Date` object as a string.
-    `toTimeString()`: Returns the time portion of a `Date` object as a string.
-    `toISOString()`: Returns the date as a string in the ISO 8601 format.
-    `toLocaleDateString()`: Returns the date portion formatted according to the local conventions.
-    `toLocaleTimeString()`: Returns the time portion formatted according to the local conventions.
-    `toLocaleString()`: Returns the date and time formatted according to the local conventions.
-    `toUTCString()`: Returns the date as a string in the UTC time zone.

#### Utility Methods

-    `getTimezoneOffset()`: Returns the difference in minutes between UTC and the local time.
-    `valueOf()`: Returns the primitive value of a `Date` object, which is the number of milliseconds since January 1, 1970.

## Example Usage

```javascript
let now = new Date();
console.log('Current Date:', now.toDateString());
console.log('Current Time:', now.toTimeString());

let futureDate = new Date();
futureDate.setFullYear(2025);
futureDate.setMonth(0); // January
futureDate.setDate(13);
console.log('Future Date:', futureDate.toDateString());
