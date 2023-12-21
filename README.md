# assignment1

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


# assignment2

function transformString(s) {
    let result = '';
    let prevCharChanged = false;  // To keep track of whether the previous character has been changed

    for (let i = 0; i < s.length; i++) {
        let char = s.charAt(i);
        let asciiValue = char.charCodeAt(0);

        if (asciiValue % 2 === 0) {
            let newAscii = asciiValue + (asciiValue % 7);
            result += String.fromCharCode(newAscii);
            prevCharChanged = false;
        } else {
            if (!prevCharChanged) {
                let newAscii = asciiValue - (asciiValue % 5);
                if (newAscii < 0 || newAscii > 127) {
                    result += String.fromCharCode(83);
                } else {
                    result += String.fromCharCode(newAscii);
                }
                prevCharChanged = true;
            } else {
                result += char;
            }
        }
    }

    return result;
}

// Example usage:
let inputString = "sHQen";
let outputString = transformString(inputString);
console.log("Original String:", inputString);
console.log("Transformed String:", outputString);




substrings.forEach(substring => {
    console.log(substring);
});

