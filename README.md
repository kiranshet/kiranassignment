# kiranassignment

function findShortestSubstrings(s, x) {
    let shortestLength = Infinity;
    let result = [];

    for (let i = 0; i < s.length; i++) {
        for (let j = i + x - 1; j < s.length; j++) {
            if (s[i] === s[j]) {
                let substringLength = j - i + 1;
                if (substringLength >= x && substringLength <= shortestLength) {
                    if (substringLength < shortestLength) {
                        result = [];
                        shortestLength = substringLength;
                    }
                    result.push(s.substring(i, j + 1));
                }
            }
        }
    }

    return result;
}

// Example usage:
let inputString = "abcbadefgaba";
let minLength = 3;
let substrings = findShortestSubstrings(inputString, minLength);

console.log(`Shortest substrings of length ${minLength} or greater:`);
substrings.forEach(substring => {
    console.log(substring);
});

