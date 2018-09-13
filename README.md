# elflord-slack-theme
My attempt at bringing elflord (from vim's colorscheme) to slack

## Install
To apply a theme to slack desktop's right panel (the text area), you have to edit an installation file.
On Arch this file is located on 
```
/usr/lib/slack/resources/app.asar.unpacked/src/static/ssb-interop.js
```

Append the following lines towards the end:
```
document.addEventListener('DOMContentLoaded', function() {
 $.ajax({
   url: 'https://raw.githubusercontent.com/raulvc/elflord-slack-theme/master/elflord.css',
   success: function(css) {
     $("<style></style>").appendTo('head').html(css);
   }
 });
});
```
