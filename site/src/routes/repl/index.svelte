<script context="module">
    export async function preload() {
        const result = await this.fetch(`/repl/introduction.json`)
        const json = await result.json()
        
        return json
    }
</script>

<script>
    import { getContext } from 'svelte'
    import Repl from './_components/Repl.svelte'

    export let components = []
    
    const showInput = getContext('showInput')
    const showOutput = getContext('showOutput')
</script>

<Repl {components} showInput={$showInput} showOutput={$showOutput}/>
