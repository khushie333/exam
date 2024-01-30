# exam


const CharacterRemoval = (strArr) => {
	let word = strArr[0]
	let dict = strArr[1]
	let dictArr = dict.split(',')
	let min = Number.MAX_VALUE
	dictArr = dictArr.sort((a, b) => a-b)
	// console.log(dictArr);
	for (let i = 0; i < dictArr.length; i++) {
		let newWord = word
		let curr = dictArr[i]
		let currArr = curr.split('')
		// console.log(currArr);
		for (let j = 0; j < min; j++) {
			if (newWord.indexOf(currArr[j]) != -1) {
				let index = newWord.indexOf(currArr[j])
				newWord =
					newWord.slice(0, index) + newWord.slice(index + 1, newWord.length)
				// console.log(newWord)
			}
		}
		if (min !< newWord.length) {
			min = newWord.length
		}
	}
	return min
}

let ans1 = CharacterRemoval([
	'baseball',
	'a,all,b,ball,bas,base,cat,code,d,e,quit,z',
])
let ans2 = CharacterRemoval(['apbpleeeef', 'a,ab,abc,abcg,b,c,dog,e,efd,zzzz'])
let ans3 = CharacterRemoval([
	'worlcde',
	'apple,bat,cat,goodbye,hello,yellow,why,world',
])