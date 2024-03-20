
## Goal

Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/17682/` ([link](https://jupiter.challenges.picoctf.org/problem/17682/)) or http://jupiter.challenges.picoctf.org:17682
## Solution
+ open link
+ ctr + u
+ The password is stored in the HTML file.
+ You just have to concatenate the password manually
function check() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '706c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_b') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == '5}') {
                  alert("Password verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
picoCTF{no_clients_plz_b706c5}
## Notes

In JavaScript, you can split a string into an array of substrings using the built-in method called `split()`

string.split(separator, limit)

- **`string`**: The string you want to split.
- **`separator`**: (Optional) The string or regular expression used to identify where to split the string. If omitted, the string is split by any whitespace character (space, tab, newline, etc.).
- **`limit`**: (Optional) An integer specifying the maximum number of splits to perform. If omitted, all possible splits are performed.
## References