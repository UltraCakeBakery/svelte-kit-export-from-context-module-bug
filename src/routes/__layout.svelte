<script context="module">
    import { writable } from "svelte/store";
    export const now = new writable(new Date())
</script>

<script>
    import { onDestroy, onMount } from "svelte";

    let interval;
    onMount( () =>
    {
        interval = setInterval( () => {
            $now = new Date()
        })
    })

    onDestroy( () => clearInterval( interval ) )
</script>


<strong>Is updating</strong>:
<br/>
{ $now }
<br/>
<br/>

<slot></slot>