<script>
    import Comment from './Comment.svelte';
    export let tituloPost;
    export let imagen;
    export let tags;
    export let texto;
</script>
   <div class="row">
       <div class="col-md-12">
        <div class="carb mb-3 base" style="width:18res;">
            <p class="title-post py-4">{tituloPost}</p>
              <img src={imagen} width="90%" height="480" alt={tituloPost} style="border-radius:6px; margin-left:40px"/>
              <div class="card-body">
               <h5 class="tags card-title" >{tags}</h5>
                 <p class="text-post">{texto}</p>
                 <div>
                     <Comment/>
                 </div>
                <div>
               </div>
              </div>
          </div>
       </div>
   </div>
   

<style>
    .base {
        background: #fff;
        border-radius: 6px; 
        -webkit-box-shadow: 4px 4px 15px 1px #000000; 
        box-shadow: 4px 4px 15px 1px #000000;
    }
   .title-post {
       color: rgba(14, 12, 12, 0.788);
       font-size: 2em;
       text-align: center;
   }
   .tags {
       color: rgba(14, 12, 12, 0.788);
       margin-left: 50px;
   }
   .text-post {
       color: rgba(14, 12, 12, 0.788);
       font-weight: bold;
       text-align: justify;
       margin-left: 50px;
   }
   img {
       background-size: cover;
   }
</style>