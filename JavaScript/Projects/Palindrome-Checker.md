
function palindrome(str) {
  let originStr = str.replace(/[^a-zA-Z0-9]/g, '').toLowerCase(); 
  let reverseStr = originStr.split("").reverse().join("");
  if ( reverseStr === originStr ) {
    return true;
  } else {
    return false;
  }
}


palindrome("eye");