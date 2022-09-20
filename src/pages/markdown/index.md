---
title: Shiki demo
layout: ../../layouts/Markdown.astro
---
[↩️ Go Back](/why-astro/)
# 👋 Hello, this page will show you how the counters on my why-astro/ page are generated

# 🗒 See these code blocks below:

# React code
```tsx
import { useState } from 'react';
import './Counter.css';

export default function ReactCounter({
		children,
		count: initialCount,
}: {
	children: JSX.Element;
	count: number;
}) {
	const [count, setCount] = useState(initialCount);
	const add = () => setCount((i) => i + 1);
	const subtract = () => setCount((i) => i - 1);

	return (
		<>
			<div className="counter">
				<button onClick={subtract}>-</button>
				<pre>{count}</pre>
				<button onClick={add}>+</button>
			</div>
			<div className="counter-message">{children}</div>
		</>
   );
}
```
```tsx
.counter {
	display: grid;
	font-size: 2em;
	grid-template-columns: repeat(3, minmax(0, 1fr));
	place-items: center;
	background: #a8a29e;
	border-radius: 1rem;
	margin: 0.5em;
	padding: 0.5rem;
	color: #1c1917;
}

button {
	border: 1px solid black;
	padding: 0 0.75rem 0 0.75rem;
	border-radius: 1rem;
	background-color: #1e293b;
	color: #fafaf9;
}
button:hover {
	background-color: #334155;
}
button:active {
	padding: 0 0.5rem 0 0.5rem;
}

.section-heading {
	font-weight: bold;
	font-size: 1.5rem;
	padding: 0rem;
	margin: 0rem;
}
```

# Preact code
```tsx
import { h, Fragment } from 'preact';
import { useState } from 'preact/hooks';
import './Counter.css';

export default function PreactCounter({ children }) {
	const [count, setCount] = useState(0);
	const add = () => setCount((i) => i + 1);
	const subtract = () => setCount((i) => i - 1);

	return (
		<>
			<div class="counter">
				<button onClick={subtract}>-</button>
				<pre>{count}</pre>
				<button onClick={add}>+</button>
			</div>
			<div class="counter-message">{children}</div>
		</>
	);
}
```
```js
<B
```

# Vue code
```tsx
<template>
	<div class="counter">
		<button @click="subtract()">-</button>
		<pre>{{ count }}</pre>
		<button @click="add()">+</button>
	</div>
	<div class="counter-message">
		<slot />
	</div>
</template>

<script lang="ts">
import { ref } from 'vue';
export default {
	setup() {
		const count = ref(0);
		const add = () => (count.value = count.value + 1);
		const subtract = () => (count.value = count.value - 1);

		return {
			count,
			add,
			subtract,
		};
	},
};
</script>

<style>
.counter {                                                     
    display: grid; 
    font-size: 2em;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    place-items: center;  
    background: #a8a29e;
    border-radius: 1rem;
    margin: 0.5em;                                   
    padding: 0.5rem;
    color: #1c1917;         
}                                
                        
button {                      
    border: 1px solid black;
    padding: 0 0.75rem 0 0.75rem;
    border-radius: 1rem;    
    background-color: #1e293b;          
    color: #fafaf9;     
}                             
button:hover {                                 
    background-color: #334155;                
}                                           
button:active {                
    padding: 0 0.5rem 0 0.5rem;                
}                                             
                                            
.section-heading {                               
    font-weight: bold;
    font-size: 1.5rem;
    padding: 0rem;
    margin: 0rem;
}
</style>
```

# Solid code
```tsx
import { createSignal } from 'solid-js';
import './Counter.css';

export default function Counter({ children }) {
	const [count, setCount] = createSignal(0);
	const add = () => setCount(count() + 1);
	const subtract = () => setCount(count() - 1);

	return (
		<>
			<div class="counter">
				<button onClick={subtract}>-</button>
				<pre>{count()}</pre>
				<button onClick={add}>+</button>
			</div>
			<div class="counter-message">{children}</div>
		</>
	);
}
```
```js
.counter {                                                     
    display: grid; 
    font-size: 2em;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    place-items: center;  
    background: #a8a29e;
    border-radius: 1rem;
    margin: 0.5em;                                   
    padding: 0.5rem;
    color: #1c1917;         
}                                
                        
button {                      
    border: 1px solid black;
    padding: 0 0.75rem 0 0.75rem;
    border-radius: 1rem;    
    background-color: #1e293b;          
    color: #fafaf9;     
}                             
button:hover {                                 
    background-color: #334155;                
}                                           
button:active {                
    padding: 0 0.5rem 0 0.5rem;                
}                                             
                                            
.section-heading {                               
    font-weight: bold;
    font-size: 1.5rem;
    padding: 0rem;
    margin: 0rem;
}
```

# Svelte code
```tsx
<script lang="ts">
	let count = 0;

	function add() {
		count += 1;
	}

	function subtract() {
		count -= 1;
	}
</script>

<div class="counter">
	<button on:click={subtract}>-</button>
	<pre>{count}</pre>
	<button on:click={add}>+</button>
</div>
<div class="message">
	<slot />
</div>

<style>
.counter {                                                     
    display: grid; 
    font-size: 2em;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    place-items: center;  
    background: #a8a29e;
    border-radius: 1rem;
    margin: 0.5em;                                   
    padding: 0.5rem;
    color: #1c1917;         
}                                
                        
button {                      
    border: 1px solid black;
    padding: 0 0.75rem 0 0.75rem;
    border-radius: 1rem;    
    background-color: #1e293b;          
    color: #fafaf9;     
}                             
button:hover {                                 
    background-color: #334155;                
}                                           
button:active {                
    padding: 0 0.5rem 0 0.5rem;                
}                                             
                                            
.section-heading {                               
    font-weight: bold;
    font-size: 1.5rem;
    padding: 0rem;
    margin: 0rem;
}
</style>
```
