/* eslint no-console: "allow"*/
<template>
  <div>
        <div  class="board">

          <div class="board-row">
            <square :value=store.state.squares[0] :index=0 v-on:onClick="onHandleClick"></square>
            <square :value=store.state.squares[1] :index=1 v-on:onClick="onHandleClick"></square>
            <square :value=store.state.squares[2] :index=2 v-on:onClick="onHandleClick"></square>
          </div>
          <div class="board-row">
            <square :value=store.state.squares[3] :index=3 v-on:onClick="onHandleClick"></square>
            <square :value=store.state.squares[4] :index=4 v-on:onClick="onHandleClick"></square>
            <square :value=store.state.squares[5] :index=5 v-on:onClick="onHandleClick"></square>
          </div>
          <div class="board-row">
            <square :value=store.state.squares[6] :index=6 v-on:onClick="onHandleClick"></square>
            <square :value=store.state.squares[7] :index=7 v-on:onClick="onHandleClick"></square>
            <square :value=store.state.squares[8] :index=8 v-on:onClick="onHandleClick"></square>
          </div>
        </div>
      </div>
</template>

<script>
import Square from './Square.vue'

export default {
  name: 'board',
  props: ['store'],
  components: {
    Square,
  },
  data() {
    return {
      // status: 'play',
      // privateState: Object.assign({}, this.store.state),
    };
  },
  methods: {
    onHandleClick(i) {
      // const squares = this.privateState.squares.slice();
      // if (squares[i] !== null) return;
      // squares[i] = this.privateState.xIsNext ? 'X' : '0';
      // this.privateState.squares = squares;
      // this.privateState.xIsNext = !this.privateState.xIsNext;
      // this.status = `xNext player: ${this.privateState.xIsNext ? 'X' : 'O'}`;
      this.$emit('onClick', i);
    },
  },
};

</script>

<style lang="css">

.board {
  display: flex;
  flex-direction: column;
  align-items: center;
}



</style>
