# kiranassignment

function shortestSubstrings(s,x)
{
 let result = [];
  
  for(let i = 0; i < s.length; i++) {
      let startChar = s[i];
      
      for(let j = s.length - 1; j >= i+x-1; j--)
      {
          if(s[j] === startChar) {
              let substring = s.substring(i, j+1);
              if(substring.length >= x && isPalindrome(substring)) {
                  result.push(substring);
                  break;
              }
          }
      }
  }
  console.log(result);
}

function isPalindrome(str) {
    return str === str.split("").reverse().join("");
}


let s = "abbcbba";
let x = 3;
shortestSubstrings(s,x);
