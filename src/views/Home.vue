<template>
  <div class="home">
    <img alt="Vue logo" @click="add" src="../assets/logo.png">
    <HelloWorld :msg="newMsg"></HelloWorld>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

@Options({
  components: {
    HelloWorld,
  },
})
export default class Home extends Vue {
  msg = '欢迎来到德莱联盟';
  language = 'english';
  a = 0;
  add(): void {
    this.a += 1;
  }
  changeMsg(): void {
    this.msg = 'welcome1';
  }
  get newMsg(): string {
    return this.a + this.msg + this.language;
  }
  mounted(): void {
    this.changeMsg();
  }
}
</script>
