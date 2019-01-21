HTML and CSS file already filled in, just needed to fill in the script tags

In Script tags:

The element you are listening for (in this case window) listening for a keydown event(pressing button on keyboard) when this happens action the function(e) - event

        window.addEventListener('keydown', function(e) {

selects the audio element (sound) linked to the data-key (letter pressed)

        const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);

selects element of this time class 'key' so we can create an animation for when button is pressed

        const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);

if no audio saved for keyCode it will return and end function

        if(!audio) return;

rewind the audio to the start

        audio.currentTime = 0;
        audio.play();

adds css animation for the class playing to the button when clicked

        key.classList.add('playing');
        });

create the removeTransition function

        function removeTransition(e){

skip it if its not a transform

      if(e.propertyName !== 'transform') return;

removes classList playing from the key which has just been pressed as this is what 'this' currently is

      this.classList.remove('playing');
      };

adds query to everything with a key class

      const keys = document.querySelectorAll('.key');

this would give us something similar to an array, which we cannot add an
event listener too so the following would not work. Instead you would need
to look through the array.
keys.addEventListener('transitionend');

      keys.forEach(key => key.addEventListener('transitionend', removeTransition));
