<script>
	import SvelTable from '../SvelTable/SvelTable.svelte';
	import namor from 'namor';
	//adding more object will add rows
	//adding more key/value pair will add columns

  function newPerson(num= 'number') {
	const sexAssigner = Math.random()
  	return {
	  id: num,
      firstName: namor.generate({ words: 1, numbers: 0 }),
      lastName: namor.generate({ words: 1, numbers: 0 }),
	  sex: 
		sexAssigner > .75
		? 'prefer not to say'
		: sexAssigner > .25
		? 'male'
		: 'female',
      age: Math.floor(Math.random() * 110),
	  occupation: namor.generate({ words: 1, numbers: 0 }),
  }
}

    let userDefinedNum = 200;

    let data = [];

	const colSetting = {
		width: 200
	};

	const rowSetting = {
		width: 100
	};

for (let i=0; i < userDefinedNum; i+= 1){
	let newbie = newPerson(i);
	data.push(newbie)
}

</script>

<h1>Welcome to SvelTable</h1>
<SvelTable dataSet={data} {colSetting} {rowSetting} />
