CSS Variables:

Declaring default settings for css variables , assinging this in root as this is one of the highest elements like html.

        :root {
          --base: #ffc600;
          --spacing: 10px;
          --blur: 10px;
        }

To then call the css variables :

        img {
          padding: var(--spacing);
        }

(The -- is how you call the css variable)


Amending these with JS

querySelectorAll - will return something similar to an array, but its not an array. Its a note list, you are not able to call all the methods used on an array for these.

Dataset - will take everything that has data- .... from the element and return it such as data-sizing will be returned if requested.

Creates a constant for the inputs we have in html:

        const inputs = document.querySelectorAll('.controls input');

Create the event listening for the inputs:

        inputs.forEach(input => input.addEventListener('change', handleUpdate));
        inputs.forEach(input => input.addEventListener('mousemove', handleUpdate));

Create the handleUpdate function:

        function handleUpdate() {
          const suffix = this.dataset.sizing || '';
          document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
        };

In the html data-sizing has been set on spacing and blur in px, by adding this we are able to call it in the method and add it to the value of the blur/spacing we want. If we didn't add this on the number would be eg. 20 instead of 20px which is what we would need. By adding the || we have the option to add on nothing so this is able to work for the colour selector too.

 The line :

        document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);

Is what targets the css elements we want to change, the input name is the same as the css variable name so by calling them and adding on the -- we call the css variables. 
