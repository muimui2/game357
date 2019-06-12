<template>
  <div class="header">
      {{title}}
  </div>
</template>

<script>
export default {
  props: {
  },
  data () {
    return {
        title:'357游戏'
    }
  },
  created () {},
  mounted () {},
  watch: {},
  computed: {},
  methods: {},
  components: {},
}
</script>
<style>

.header{
  position: fixed;
  width: 100%;
  height: 50px;
  display: flex;
  display: -webkit-flex;
  justify-content: center;
  align-items: center;
  background-color: #63435e;
  color:white;

}

</style>