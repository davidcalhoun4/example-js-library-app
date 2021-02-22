<template>
  <div class="home">
    <div>
      <h1>Pokemon Game</h1>
      <button v-on:click="popUp">Let's Play!</button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import swal from "sweetalert";

export default {
  methods: {
    popUp() {
      swal("A wild Pikachu appeared! What do you want to do?", {
        buttons: {
          cancel: "Run away!",
          catch: {
            text: "Throw Pokéball!",
            value: "catch",
          },
          defeat: true,
        },
      }).then((value) => {
        switch (value) {
          case "defeat":
            swal("Pikachu fainted! You gained 500 XP!");
            break;

          case "catch":
            swal("Gotcha!", "Pikachu was caught!", "success");
            break;

          default:
            swal("Got away safely!");
        }
      });
    },
  },
  // mounted: function() {
  //   swal("A wild Pikachu appeared! What do you want to do?", {
  //     buttons: {
  //       cancel: "Run away!",
  //       catch: {
  //         text: "Throw Pokéball!",
  //         value: "catch",
  //       },
  //       defeat: true,
  //     },
  //   }).then((value) => {
  //     switch (value) {
  //       case "defeat":
  //         swal("Pikachu fainted! You gained 500 XP!");
  //         break;

  //       case "catch":
  //         swal("Gotcha!", "Pikachu was caught!", "success");
  //         break;

  //       default:
  //         swal("Got away safely!");
  //     }
  //   });
  // },
};
</script>
