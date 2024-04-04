<script>

    import { time,elapsedTime } from '../store/stores';


    const dateFormatter = new Intl.DateTimeFormat('en',{
        year: 'numeric',
    month: 'long',
    day: 'numeric',
    hour12: true,
    hour: 'numeric',
    minute: '2-digit',
    second: '2-digit',
  
    
    });
</script>


<h2>The Date and time is {dateFormatter.format($time)}</h2>
<h2>you have been on this page for {$elapsedTime} secs</h2>



