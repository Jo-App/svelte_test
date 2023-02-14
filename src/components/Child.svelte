<script>
  import { getContext } from 'svelte';
  export const sayChild = () => {console.log('아들: 엄마생신 아니라는데요ㅋㅋㅋㅋㅋㅋ');}
  const { parentTalk } = getContext('talk');

  const childTalk = () => {
    console.log('아들: 엄마한테 혼났어요');
    parentTalk();
  }

</script>

<main>
  <h2>I'm Child !!!</h2>
  <button on:click={childTalk}>Send to Parent</button>
</main>

<style scoped>
  h2 {
    color: green;
  }
</style>