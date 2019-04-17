# twitter_clean

1. Open Browser
2. Go to https://twitter.com/i/likes for likes remove or https://twitter.com/youraccount/following for following remove
3. Press F12
4. Open the ‘Console’ tab
5. Copy one of the following scripts
6. In the bottom of the debug console, next to the blue arrow, paste it in
7. Press enter the run the script
Note – you may need to refresh the page and run the script again, several times, to completely clear your list.

## For likes remove
```
setInterval(
    function() {
        t = $( 'button.ProfileTweet-action--unfavorite' ); // get unfavourite buttons
        for ( i = 0; true; i++ ) { // count
            if ( i >= t.length ) { // if items remain to unfavourite
                window.scrollTo( 0, $( document ).height() ); // scroll to bottom of page - loads more
                return
            }
           $( t[i] ).trigger( 'click' ).remove(); // click and remove button from dom
        }
    }, 2000
)
```

## For following remove
```
setInterval(
    function() {
        t = $( 'button.unfollow-text' ); // get unfavourite buttons
        for ( i = 0; true; i++ ) { // count
            if ( i >= t.length ) { // if items remain to unfavourite
                window.scrollTo( 0, $( document ).height() ); // scroll to bottom of page - loads more
                return
            }
           $( t[i] ).trigger( 'click' ).remove(); // click and remove button from dom
        }
    }, 2000
)
```
