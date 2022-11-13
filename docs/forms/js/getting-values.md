---
title: Getting Values from a Form
---

# {{this.$frontmatter.title}}

```html
<form>
	<input type="text" id="name">
	<input type="password" id="password">
	<input type="submit" value="Submit">
</form>
```

### Basic

```js
// get the form element
const form = document.querySelector("form");

// get input elements
const name = document.getElementById("name");
const password = document.getElementById("password");

// handle event
form.addEventListener("submit", e => {
	e.preventDefault();
	// stringify object
	alert(JSON.stringify({
		// get value of name
		name: name.value,
		// get value of password
		password: password.value
	}));
});
```
