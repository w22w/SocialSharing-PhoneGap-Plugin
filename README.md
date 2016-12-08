# PhoneGap Social Sharing plugin for Android, iOS and Windows Phone

forked from https://github.com/EddyVerbruggen/SocialSharing-PhoneGap-Plugin

Extremely want to help? Please do it here:
[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=N6HK35MY4KFZ6&lc=UA&item_name=opensource%2edevelopment&item_number=development4opensource&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donate_SM%2egif%3aNonHosted)

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
    }else if(data == 'before-UI-init'){
      //do something
    } else if(data == 'after-UI-init'){
        hidePleaseWaitMessage();
    }
};


showPleaseWaitMessage();

window.plugins.socialsharing.shareWithOptions(
  options,
  onSuccess, // optional success function
  onError    // optional error function
);
```


