# HTML-Browser-Tricks
A list of tips / tricks / scripts for html or web based stuff for my personal use


#Extract-Text-From-Protected-HTML
Short Java Script to extract Text in HTML and output to console and Clipboard inspect webpage > console > run command > will copy the webpages "main content" prints it to the terminal and also copies it directly to your clipboard for convince

NOTE: "Main-Conent" may need to be chagned for some sites
```
let content = Array.from(document.querySelectorAll('.main-content'))
                   .map(el => el.innerText)
                   .join('\n============================\n') + '\n============================\n';

console.log(content);

let textarea = document.createElement('textarea');
textarea.textContent = content;
document.body.appendChild(textarea);
textarea.select();
try {
    let successful = document.execCommand('copy');
    let msg = successful ? 'successful' : 'unsuccessful';
    console.log('Copy command was ' + msg);
} catch(err) {
    console.log('Oops, unable to copy');
}
document.body.removeChild(textarea);
```


# Sonic-Playabck
increase playback speed of browser using browsers console.... Speed can be set from 1-16
Important part of the code 

``` 
document.querySelector('video').playbackRate = 16;
```
