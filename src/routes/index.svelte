<script>
	import SvelTable from '../SvelTable/SvelTable.svelte';
	import namor from 'namor';
	//adding more object will add rows
	//adding more key/value pair will add columns

	function newPerson(num) {
		return {
			id: num,
			firstName: namor.generate({ words: 1, numbers: 0 }),
			lastName: namor.generate({ words: 1, numbers: 0 }),
			age: Math.floor(Math.random() * 110),
			occupation: namor.generate({ words: 1, numbers: 0 })
		};
	}

	let userDefinedNum = 1000;

	let data = [];

	for (let i = 1; i < userDefinedNum + 1; i++) {
		let newP = newPerson(i);
		data.push(newP);
	}
</script>

<!-- <h1>Welcome to SvelTable</h1> -->
<SvelTable dataSet={data} />
