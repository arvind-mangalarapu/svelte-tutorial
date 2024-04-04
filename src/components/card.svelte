<!-- <script>
    export let content
</script> -->
<!-- <slot>default content</slot> -->

<div class="card">
    <div class="card-header"><slot name="header"></slot>
    </div>
    <div class="card-content"><slot name="content"></slot>
    </div>
    <div class="card-footer"><slot name="footer"> </slot>
    </div>
</div>



<!-- <style>
    
    .card{
        box-shadow: 0.4px 5px 1px rgb(255, 255, 255);
        transition: 0.3s;
         padding: 16px;
         margin-bottom: 20px;
         width: 400px;
         color: white;
         margin: 30px auto;
        
       
    
        }
    .card:hover{
         box-shadow: 0 8px 16px 0 rgb(255, 255, 255);
     }

    
</style> -->