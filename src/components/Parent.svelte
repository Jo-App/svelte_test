<script>
  import { setContext } from 'svelte';
  import Child from './Child.svelte';
  setContext('talk', {parentTalk} );
  let sayChild;

  function parentTalk() {
    console.log('아빠: 미안 아빠도 어느년 이라고 욕먹었다.');
  }
  const callChild = () => {
    console.log('아빠: 엄마생신이다 문자드려라')
    sayChild();
  }
  
</script>

<main>
  <h2>I'm Parent!</h2>
  <button on:click={callChild}>Send to Child</button>
  <Child bind:sayChild={sayChild}></Child>
</main>

<style scoped>
  h2 {
    color: red;
  }
</style>