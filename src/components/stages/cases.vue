<template>
  <section class="stage stage--cases" v-el:cases>
    <div class="stage__inner">

      <ul class="container">
        <li class="block block--four" v-for="case in cases">
          <a v-link="{name: 'case', params: {case: case.id}}" class="inner-block" v-bind:class="case.id" v-bind:style="{ backgroundImage: 'url(' + getThumb(case.id) + ')' }">
            <div class="responsive-element">
              <div class="content">
                <h2>{{ case.title }}</h2>
                <span class="link line">view case</span>
              </div>
            </div>
          </a>
        </li>

      </ul>

    </div>
  </section>
</template>

<script>
import { getCases } from 'vuex/getters';
export default {
  vuex: {
    getters: {
      cases: getCases
    }
  },

  methods: {
    getThumb (caseId) {
      return require('../cases/' + caseId + '/thumbnail.png');
    }
  }
};
</script>
