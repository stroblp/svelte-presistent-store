<script>
	import  presistentStore  from "../lib/presistent-store";
	let countlocalStorage = presistentStore("counter-value",0,{driver:"LOCALSTORAGE"});
	let countWebSQL = presistentStore("counter-value",0,{driver:"WEBSQL"});
	let countIndexedDB = presistentStore("counter-value",0,{dbName:"test-test",driver:"INDEXEDDB"});
</script>

<p>localstorage:</p>
<button on:click={() => ($countlocalStorage -= 1)}>-</button>
<span>{$countlocalStorage}</span>
<button on:click={() => ($countlocalStorage += 1)}>+</button>
<button on:click={() => ($countlocalStorage =0)}>Clear</button>

<p>websql:</p>
<button on:click={() => ($countWebSQL -= 1)}>-</button>
<span>{$countWebSQL}</span>
<button on:click={() => ($countWebSQL += 1)}>+</button>
<button on:click={() => ($countWebSQL =0)}>Clear</button>

<p>indexeddb:</p>
<button on:click={() => ($countIndexedDB -= 1)}>-</button>
<span>{$countIndexedDB}</span>
<button on:click={() => ($countIndexedDB += 1)}>+</button>
<button on:click={() => ($countIndexedDB =0)}>Clear</button>

<div>
	<button on:click={() => (location.reload())}>Reload Page</button>
</div>
<style>
	div{
		padding:10px 0px;
	}
</style>
