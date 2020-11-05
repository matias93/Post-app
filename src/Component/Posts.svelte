<script>
    import Card from './Card.svelte';
    export let posts;
</script>

<div class="row mt-3">
  {#each posts as item }
    <div class="col-md-6">
      <Card
        tituloPost={item.id}
        imagen={item.image}
        tags={item.tags}
        texto={item.text}
       />
     </div>
    {/each}
   </div> 
<style>
</style>
