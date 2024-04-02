<script>
    import { count } from '../store/stores'

let counter

    count.subscribe((value)=> {
        counter = value
    })
</script>


<h2>Current count is {counter}</h2>