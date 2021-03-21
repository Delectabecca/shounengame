<template>
  <div>
    <div @click="show()" style="display:inline">Show</div> <div @click="hide()" style="display:inline">Hide</div>
    <div id="actions" :class="{ hidden: curMenu!='actions'}">
    <div class="row" style="width:100%">
      <div class="col-sm-4">
        This is a testy test test
      </div>
      <div class="col-sm-8">
        <div id="actions" class="row overflow-auto" style="height:100px">
          <div style="padding:10px" :class="{ 'col-sm-6': true, hidden: action.unlocked != 1 }" v-for="action in actions" :key="action.name">
              <div class="rounded" style="background-color:grey;border-color:black;border-width:2px;border-style:solid;color:white;"><center>{{action.name}}</center></div>
          </div>
        </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script>

export default{
  data() {
    return{
      actions: {
        eat: {
          name: "Eat",
          unlocked: 1
          },
        sleep: {
          name: "Sleep",
          unlocked: 1
        },
        lift: {
          name: "Lift Weights"
        },
        run: {
          name: "Run"
        },
        magic: {
          name: "Do Magic"
        }
      },
      curMenu: String
    }
  },
  methods: {
    show: function() {
      this.curMenu = "actions"
    },
    hide: function() {
      this.curMenu = ""
    }
  }
}

</script>

<style>
.hidden {
  display:none;
}
</style>