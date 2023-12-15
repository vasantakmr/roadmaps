<script lang="ts">
  import { writable } from 'svelte/store';
  import {
    SvelteFlow,
    Controls,
    Background,
    Position,
    MiniMap,
    type Node,
    type Edge,
  } from '@xyflow/svelte';

  import '@xyflow/svelte/dist/style.css';

  const nodes = writable<Node[]>([
    {
      id: '1',
      data: { label: 'Command Prompt' },
      position: { x: 0, y: 25 },
      sourcePosition: Position.Right
    },
    {
      id: '2',
      data: { label: 'World' },
      position: { x: 240, y: 0 },
      targetPosition: Position.Left
    },
  ]);

  const edges = writable<Edge[]>([
    {
      id: '1-2',
      source: '1',
      target: '2',
    },
  ]);
</script>

<div style:height="100vh">
  <SvelteFlow {nodes} {edges} fitView>
    <Controls />
    <Background />
    <MiniMap />
  </SvelteFlow>
</div>


<!-- <div style:height="100vh">
  <SvelteFlow {nodes} {edges} minZoom={2.0} maxZoom={2.0} translateExtent={[[100, 100], [300, 300]]}  >
    <Controls />
    <MiniMap />
  </SvelteFlow>
</div> -->
