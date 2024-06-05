<script lang="ts">
    import { onMount } from "svelte";
    import { storage } from "../storage";
    import Options from "./Options.svelte";

    let count = 0;

    onMount(() => {
        storage.get().then((storage) => (count = storage.count));
    });
</script>

<div class="page">
    <Options {count} />
</div>

<style>
    .page {
        position: fixed;
        width: 100dvh;
        height: 100dvh;
        inset: 0;
        background-color: white;
        padding: 16px;
    }
</style>
