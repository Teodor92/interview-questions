# Simple coding questions

## 1. Implement an algorithm to determine if a string has all unique characters. What if you cannot use additional data structures?

- Asks question about charset/encoding. And use info for quick exit condition.
- Use a map.
- Use search based approach.
- Uses a bit vector(Advanced!).

## 2. Create a function that by a given object, key name and key value - returns a new object with the updated values for the specific key

- Duplicated keys?
- Object in updated key?
- Mutable vs immutable approach?

## 3. Given two strings, write a method to decide if one is a permutation of the other

- If different lengths - no permutation.
- Is it case insensitive?
- Sort strings.
- Check for char counts - maps.

## 4. Create a comma separated string from all the properties of an object

## 5. Find the average of an array of numbers

## 6. Flatten a 2D array

Example input: `[[1,2],[3,4]]`
Example output: `[1,2,3,4]`

## 7. Flatten an N-D array

Example input: `[[1,[2],[3,[4]]`
Example output: `[1,2,3,4]`

## 8. Find the path to a property in an object

Example input object:

```json
{
    "menu": {
    "id": "file",
    "value": "File",
    "popup": {
        "menuitem": {
                "onclick": "CreateNewDoc()"
        }
    }
}}
```

Example property to search for: `onclick`
Example path output: `popup > menuitem > onclick`
