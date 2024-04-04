<script>
    import { count,customCount } from '../store/stores'

let counter

    count.subscribe((value)=> {
        counter = value
    })
</script>


<h2>Current count is {counter}</h2>
<h2>The custom count is {$customCount}</h2>


<button on:click={()=> customCount.increment()}>Increment</button>
<button on:click={()=> customCount.increment(5)}>Increment 5</button>
<button on:click={()=> customCount.decrement()}>Decrement</button>
<button on:click={()=> customCount.decrement(5)}>Decrement 5</button>
<button on:click={customCount.reset}>Reset</button>




