<template>
  <div>
    <section class="container">
      <h2>What are we doing first?</h2>

      <section class="group-card" id="v-for-object">
        <nuxt-link
          v-for="value in object"
          v-bind:key="value"
          class="card"
          v-bind:to="value.link"
        >
          <h3>{{ value.title }}</h3>
          <p>{{ value.description }}</p>
          <!-- <img :src="value.image"> -->
          <svg v-html="value.image" class="illustration"></svg>
        </nuxt-link>
      </section>
    </section>
  </div>
</template>

<script>
// import {archeryPana, notes} from "../icons";

import * as icons from "../icons"

export default {
  name: "index",
  data() {
    return {
      el: "#v-for-object",
      object: [
        {
          title: "Time Tracker",
          description: "Be easily aware of the use of your time.",
          link: "/time",
          image:icons.archeryPana,
        },
        {
          title: "To Do List",
          description: "The way to keep your tasks up to date.",
          link: "/todo",
          image:icons.todo,
        },
        {
          title: "Personal Notes",
          description: "All your ideas in one place.",
          link: "/notes",
          image:icons.notes,
        },
        {
          title: "Goals",
          description: "Achieve your goals in an organized way.",
          link: "/goals",
          image:icons.goals,
        },
        {
          title: "Dashboard",
          description: "Check your metrics in graphs.",
          link: "/dashboard",
          image:icons.dashboard,
        },
      ],
    };
  },
};
</script>

<style lang="scss">
*,
body,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  background-color: #fff;
  font-family: "Nunito Sans", sans-serif;
  color: #3b847f;

  h1,
  h2,
  h3,
  h4,
  p {
    padding-bottom: 20px;
  }

  li {
    list-style: none;
  }

  .container {

    h2 {
      text-align: center;
      padding-bottom: 30px;
    }

    .group-card {
      display: grid;
      grid-template-rows: 1fr 1fr;
      column-gap: 15px;
      row-gap: 15px;

      @media (max-width: 400px) {
        grid-column: 1fr;
      }

      @media (min-width: 700px) {
        grid-template-columns: 1fr 1fr;
      }

      @media (min-width: 1200px) {
        grid-template-columns: 1fr 1fr 1fr;
      }
    }

    .card {
      border-radius: 4px;
      background-color: #f8f8f8;
      padding: 20px;
      display: flex;
      flex-direction: column;
      text-decoration: none;
      color: #3b847f;
      // transition: 0.5s ease-in-out;

      &:hover {
        box-shadow: 0px 4px 5px 0px #e7e7e7bf;
      }

      h3 {
        padding-bottom: 10px;
      }

      .illustration {
        width: 50%;
        height: 200px;
        margin-left: auto;
      }

      &:hover {
        //-------time tracker-------

        .freepik--Plant--inject-4 {
          transform: translateY(-10px);
        }

        .plant-group-one,
        .plant-group-two,
        .plant-group-three,
        .plant-group-four,
        .plant-group-five {
          path {
            transform: rotateX(20deg);
          }
        }

        //-------todo list-------
        .checkToDoList {
          transform: translateY(-10px);
        }
        .plantToDoList {
          transform: rotateX(2deg);
        }

        //-------notes-------
        .freepik--Plant--inject-31 {
          .circles-flowers {
            fill: #6ca8a4;
            stroke: #3b847f;
          }
        }

        .lapicera {
          transform: translateY(-5px);
        }

        //-------goals-------
        .freepik--clouds--inject-3 {
          stroke: #3b847f;
        }

        .freepik--target--inject-3 {
          transform: translateY(-10px);
        }
      }
    }
  }
}
</style>
