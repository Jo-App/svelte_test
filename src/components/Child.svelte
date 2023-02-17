<script>
  import { getContext } from 'svelte';
  export const sayChild = () => {console.log('아들: 엄마생신 아니라는데요ㅋㅋㅋㅋㅋㅋ');}
  const { parentTalk } = getContext('talk');

  const childTalk = () => {
    console.log('아들: 엄마한테 혼났어요');
    parentTalk();
  }

</script>

<section>
  <h2>I'm Child !!!</h2>
  <button on:click={childTalk}>
    <span class="material-symbols-outlined child-arrow">arrow_top_left</span>
    Send to Parent
  </button>
</section>

<style scoped>
  section {
    border: 1px solid green;
    width: 500px;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 10px;
  }
  h2 {
    color: green;
  }
  button {
    width: 155px;
  }
  .child-arrow {
    transform: rotate(90deg) scaleY(-1);
    position: relative;
  }
</style>