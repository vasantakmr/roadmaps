<script lang="ts">
  import { writable } from "svelte/store";
  import {
    SvelteFlow,
    Controls,
    Background,
    Position,
    MiniMap,
    type Node,
    type Edge,
  } from "@xyflow/svelte";

  import "@xyflow/svelte/dist/style.css";

  const nodes = writable<Node[]>([
    {
      id: "1",
      data: { label: "Command Prompt" },
      position: { x: 0, y: 240 },
      sourcePosition: Position.Right,
    },
    {
      id: "2",
      data: { label: "History" },
      position: { x: 240, y: 0 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "3",
      data: { label: "OS Types" },
      position: { x: 480, y: 0 },
      targetPosition: Position.Left,
    },
    {
      id: "4",
      data: { label: "Why do Servers prefer CLI?" },
      position: { x: 480, y: 80 },
      targetPosition: Position.Left,
    },
    {
      id: "5",
      data: { label: "Why you should learn Command Prompt?" },
      position: { x: 240, y: 120 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "6",
      data: { label: "How CMD is same as using a full OS?" },
      position: { x: 240, y: 220 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "7",
      data: { label: "A Command: Command + arguments" },
      position: { x: 240, y: 320 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "8",
      data: { label: "Working with folders : Creating, moving, and deleting folders" },
      position: { x: 240, y: 420 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "9",
      data: { label: "Moving around folders" },
      position: { x: 480, y: 380 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "10",
      data: { label: "Working with files : 1. Creating updating and deleting files." },
      position: { x: 240, y: 500 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "11",
      data: { label: "Listing files from folders" },
      position: { x: 480, y: 460 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "12",
      data: { label: "Miscellaneous " },
      position: { x: 240, y: 580 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "13",
      data: { label: "Grepping" },
      position: { x: 480, y: 540 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "14",
      data: { label: "Batch files" },
      position: { x: 480, y: 620 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
    {
      id: "15",
      data: { label: "Networking commands & tool " },
      position: { x: 480, y: 700 },
      targetPosition: Position.Left,
      sourcePosition: Position.Right,
    },
  ]);

  const edges = writable<Edge[]>([
    {
      id: "1-2",
      source: "1",
      target: "2",
    },
    {
      id: "2-3",
      source: "2",
      target: "3",
    },
    {
      id: "2-4",
      source: "2",
      target: "4",
    },
    {
      id: "1-5",
      source: "1",
      target: "5",
    },
    {
      id: "1-6",
      source: "1",
      target: "6",
    },
    {
      id: "1-7",
      source: "1",
      target: "7",
    },
    {
      id: "1-8",
      source: "1",
      target: "8",
    },
    {
      id: "8-9",
      source: "8",
      target: "9",
    },
    {
      id: "1-10",
      source: "1",
      target: "10",
    },
    {
      id: "8-11",
      source: "8",
      target: "11",
    },
    {
      id: "1-12",
      source: "1",
      target: "12",
    },
    {
      id: "12-13",
      source: "12",
      target: "13",
    },
    {
      id: "12-14",
      source: "12",
      target: "14",
    },
    {
      id: "12-15",
      source: "12",
      target: "15",
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
