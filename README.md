# Superpeer UI Challenge

## Resources

- https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA24.html
- https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time
- https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles
- https://www.digitala11y.com/accessibility-cheat-sheets/
- https://bitsofco.de/the-accessibility-cheatsheet/
- https://moritzgiessmann.de/accessibility-cheatsheet/
- https://webaim.org/techniques/forms/advanced

## Notes

- I couldn't find the exact font on figma :/

- In Firefox, there is a bug that causes `select` elements to be taller than it's actual height since it adds 2px internal padding. ([Reference 1](https://bugzilla.mozilla.org/show_bug.cgi?id=1582545), [Reference 2](https://bugzilla.mozilla.org/show_bug.cgi?id=1560824)). I ended up adding `height: 48px` to solve this

- Tested on Chrome, Edge, Firefox, Android Chrome

- I added all the states to the form elements
