# PhoneGap Social Sharing plugin for Android, iOS and Windows Phone

forked from https://github.com/EddyVerbruggen/SocialSharing-PhoneGap-Plugin

#### Adding extra calls for success callback (before and after showing widget) (iOS only currently)

```js
var options = {
    message: fileName, // not supported on some apps (Facebook, Instagram)
    subject: fileName, // fi. for email
    files: [file_url], // an array of filenames either locally or remotely
    "additional_callbacks": "true", //new option (optional) to generate additional calls for success callback
    chooserTitle: 'Pick an app' // Android only, you can override the default share sheet title
},
onSuccess = function(data){
    if( data && data.app ){
        //it is completely finished
    }else if(data == 'before UI init'){
      //do something
    } else if(data == 'after UI init'){
        hidePleaseWaitMessage();
    }
};


showPleaseWaitMessage();

window.plugins.socialsharing.shareWithOptions(
  ['https://www.google.nl/images/srpr/logo4w.png','www/image.gif'],
  onSuccess, // optional success function
  onError    // optional error function
);
```

