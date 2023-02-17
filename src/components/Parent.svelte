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

<section>
  <h2>I'm Parent!</h2>
  <button on:click={callChild}>
    Send to Child
    <span class="material-symbols-outlined parent-arrow">arrow_top_left</span>
</button>
  <Child bind:sayChild={sayChild}></Child>
</section>

<style scoped>
  section {
    border: 1px solid red;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }
  h2 {
    color: red;
  }
  button {
    width: 155px;
  }
  .material-symbols-outlined {
    font-variation-settings:
    'FILL' 0,
    'wght' 400,
    'GRAD' 0,
    'opsz' 48,
  }
  .parent-arrow {
    transform: rotate(90deg) scaleX(-1);
    position: relative;
    top: 10px;
  }
</style>