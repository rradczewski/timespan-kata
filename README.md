# Timespan Coding Kata

## Summary

The goal is to implement a utility function that 'pretty-prints' timespans. For example, 3620 seconds become "1 hour, 20 seconds ago". Such a function greatly enhances UX by providing the user a readable timespan without bothering it with details.

### Suggestions

- Use a unit testing library
- Use git and work in baby-steps
- Commit often
- Don't read or work ahead!

## Increments

### Part 1 - Simple pretty-printing

1. Implement a function that, given a number of seconds, prints the seconds suffixed with " seconds". E.g. ```prettyPrint(30) => "30 seconds"```
2. Extend your function to support minutes e.g. ```prettyPrint(140) => "2 minutes, 20 seconds"```
3. Extend your function to use singular for every unit, e.g. ```prettyPrint(3601) => "1 hour, 1 second"```
4. Implement hours, days, months and years (we assume ```30 days = 1 month```)

### Part 2 - For brevity!

5. Add a parameter ```bool brevity``` to your function so that, if set to true, only the three largest units are shown. E.g. ```prettyPrint(90012, brevity: true) => "1 day, 1 hour"```
6. Add a parameter ```bool skipZeroes``` to your function so that, if set to true, zeroes are skipped. E.g. ```prettyPrint(172860, skipZeroes: true) => "2 days, 1 minute"```
7. Allow both parameters to be used in conjunction, e.g. "prettyPrint(172862, brevity: true, skipZeroes: true) => "2 days, 1 minute"```

### Part 3 - Lossy algorithm

8. Add an exclusive parameter ```bool lossy``` to your function, so that, if set to true, only the largest unit is used. E.g ```prettyPrint(172862, lossy: true) => "2 days")```
9. If ```bool lossy = true```, your function should round to the nearest integer (use Math.round). E.g. ```prettyPrint(198719, lossy: true) => "2 days"``` and ```prettyPrint(233280, lossy: true) => "3 days"```
10. Use the words "over" and "almost" to hint the rounding to the user. E.g. ```prettyPrint(198719, lossy: true) => "over 2 days"``` and ```prettyPrint(233280, lossy: true) => "almost 3 days"```