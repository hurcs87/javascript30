* Question 1 :

      const isAdult = people.some(function(person) {
        const currentYear = (new Date()).getFullYear();
        if(currentYear - person.year >= 19) {
          return true;
        }
      });

      console.log({isAdult});

By added the {} inside the (), the console log will be isAdult: true , rather than just true.

refactored :

      const isAdult = people.some(person => {
        const currentYear = (new Date()).getFullYear();
        return currentYear - person.year >= 19;
      });
or:

      const isAdult = people.some(person => ((new Date()).getFullYear()) - person.year >= 19);

* Question 2 :

      const comment = comments.find(function(comment){
        if(comment.id === 823423){
          return true;
        }
      });

refactored:

      const comment = comments.find(comment => comment.id === 823423);

* Question 3 :

to remove from array

      comments.splice(index, 1);

or

      const newComments = [
      ...comments.slice(0, index),
      ...comments.slice(index + 1)
      ];
