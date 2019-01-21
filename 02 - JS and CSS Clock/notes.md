Notes

- In .hand css adding           

      transform-origin: 100%;

will allow us to rotate from the end rather than from the centre when using rotate.

          transform: rotate(90deg);

Puts hands up to 12 o'clock.             

- setInterval

        setInterval(setDate, 1000);

Counts down in seconds, so will run set date function every second

- Sets seconds variable

          const seconds = now.getSeconds();

- Works out the degrees for second hand.

      const secondsDegrees = (seconds / 60) * 360;
