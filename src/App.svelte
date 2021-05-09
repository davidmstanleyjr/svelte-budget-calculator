<script>
	import {setContext } from 'svelte';
	//components
	import Navbar from './Navbar.svelte';
	import ExpensesList from './ExpensesList.svelte';
	//data
	import expensesData from './expenses';
	//variables
	let expenses = [...expensesData];
	//functions
	//this functio removes individual expenses from the expense list
	function removeExpense(id) {
		expenses = expenses.filter(item => item.id !== id);
	}
	//this function clears all expenses from the page
	function clearExpenses () {
		expenses = [];
	}

// setContext
setContext('remove', removeExpense)	

</script>

<Navbar />
<main class='content'>
	<ExpensesList expenses={expenses} />
	<button type='button' class='btn btn-primary btn-block' on:click={clearExpenses}>clear expenses</button>
</main>
