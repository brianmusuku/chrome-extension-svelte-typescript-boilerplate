<script lang="ts">
  import { onMount } from "svelte";
  import { storage } from "../storage";
  import Options from "./Options.svelte";
  import { Input } from "$lib/components/ui/input";

  import "../tailwind.css";

  let count = 0;

  onMount(() => {
    storage.get().then((storage) => (count = storage.count));
  });
</script>

<div class="fixed w-80 top-4 left-4 bg-white border border-indigo-600 p-4">
  <Options {count} />

  <Input />
</div>
