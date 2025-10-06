# Optional Chaining

Nested data can *quickly* become hard to work with. In most production systems you'll regularly encounter objects nested 3–4 levels deep.

Using the normal `.` operator on a value that is `null` or `undefined` will throw a runtime `TypeError`. Thankfully, JavaScript provides the optional chaining operator `?.` to safely access nested properties.

Example:

```js
const user = {
  profile: {
    name: 'Ada Lovelace',
    contact: { email: 'ada@example.com' }
  }
};

// Without optional chaining — may throw if `profile` is null/undefined
const email1 = user.profile && user.profile.contact && user.profile.contact.email;

// With optional chaining — safe and concise
const email2 = user?.profile?.contact?.email;

// You can also use it with function calls and array access:
const maybeValue = obj?.method?.(arg1, arg2);
const item = arr?.[index];
```

Use optional chaining when you need to safely traverse nested structures. It prevents runtime errors and makes code clearer and more predictable.