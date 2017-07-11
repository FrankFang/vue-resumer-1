<template>
  <div id="editor">
    <nav>
      <ol>
        <li v-for="i in [0,1,2,3,4,5]" v-bind:class="{active: currentTab === i}" v-on:click="currentTab = i" >
          <svg class="icon">
            <use v-bind:xlink:href="`#icon-${icons[i]}`"></use>
          </svg>
        </li>
      </ol>
    </nav>
    <ol class="panes">
      <li v-for="i in [0,1,2,3,4,5]" v-bind:class="{active: currentTab === i}" >
        Tab {{i+1}}
      </li>
    </ol>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        currentTab: 0,
        icons: ['shenfenzheng', 'work', 'book', 'heartsurgery', 'jiangbei', 'phone']
      }
    }
  }
</script>

<style lang="scss">
  #editor{ min-height: 100px;
    display: flex;
    > nav {
      background: #000;
      width: 80px;
      > ol > li {
        padding: 16px 0;
        text-align: center;
        > .icon {
          width: 24px;
          height: 24px;
          fill: white;
        }
        &.active{
          background: white;
          > .icon{
            fill: black;
          }
        }
      }
    }
    > .panes {
      > li{
        display: none;
        &.active{
          display: block;
        }
      }
    }
  }
</style>
