# swf2js.js

swf2js.js is a JavaScript FlashPlayer emulator that analyzes SWF files
of Adobe Animate (Flash) in real time and converts them to HTML.

Content
=======

[Background](#Background)

[Basic usage](#Basic_usage)

[Options](#Options)

[Examples](#Examples)

[Known problems](#Known_problems)

[Information](#Information)

[Background](#Background)
===========

This version of swf2js is an adaption based on swf2js.js version 0.7.8 from
[https://github.com/swf2js/swf2js.com/blob/master/assets/js/swf2js.js](https://github.com/swf2js/swf2js.com/blob/master/assets/js/swf2js.js)

swf2js.min.js is the minified version created with [Google Closure Compiler)(https://developers.google.com/closure/compiler).

Added support for sounds and soundstreams

-   Sounds : mp3, raw (wave), ADPCM, NellyMoser.
-   Soundstreams : mp3, raw (wave), ADPCM.

Warning : no support for [Actionscript 3](https://en.wikipedia.org/wiki/ActionScript) which is introduced in Flash Player 9 (initially called 8.5).

Newer swf-files (version 9 and up) will probably still work, if you didn't useActionscript 3

If you have (or can find) Flash MX 2004 or Flash (Professional) 8, you can stil create sfw-files and use them with swf2js.js

Licenses for Adobe Flash can be found on [https://helpx.adobe.com/en/x-productkb/policy-pricing/macromedia-legacy-activation-error.html](https://helpx.adobe.com/en/x-productkb/policy-pricing/macromedia-legacy-activation-error.html)

See [https://github.com/swf2js/swf2js](https://github.com/swf2js/swf2js)
and [https://swf2js.com/en/](https://swf2js.com/en/) for a commercial
version that supports [Actionscript 3](https://en.wikipedia.org/wiki/ActionScript).


[Basic usage](#Basic_usage)
===========

    <script type="text/javascript" src="swf2js.min.js"></script>
    <script type="text/javascript">
        swf2js.load('SET SWF PATH');
    </script>  
            

[Options](#Options)
=======

  Option|Description|Additional information
  -----------|---------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------
  tagId       |Place swf-player in element with tag 'tagId'|                                
  width       |Set width of swf-player|                                                     
  height      |Set height of swf-player|                                                    
  callback    |Function to be called when swf-player has loaded the swf-file |              
  FlashVars   |                                       |                                     
  quality     |Values : "low", use devicePixelRatio\*0.5 or "high", use devicePixelRatio|See [devicePixelRatio](https://developer.mozilla.org/en-US/docs/Web/API/Window/devicePixelRatio)
  bgcolor     |Set background color |                                                       

Example usage of options.
```
   swf2js.load('tiger.swf', {tagId: "swf_2", width: "320", height: "320", callback : informMe, bgcolor: "black"});
```        

See [example\_options.html](https://music4classicalguitar.github.io/swf2js/example_options.html)

[Examples](#Examples)
========

[Examples](https://music4classicalguitar.github.io/swf2js/examples.html)

[Animated music](https://music4classicalguitar.github.io/animatedmusic/animatedmusic.html)

[Known problems](#Known_problems)
==============

-   More than one swf-file in a page does not work properly.
-   Obviously Adobe FlashPlayer knows the exact frame size, even if
    bigger than the specified framesize in the header. \
    See examples : mogura and PlayPauseStop5
-   Video (mp4 and flv) not supported.

See also [https://swf2js.com/en/\#skills](https://swf2js.com/en/#skills)
for the differences between the free and the commercial version.

[Information](#Information)
=============

[SWF FILE FORMAT SPECIFICATION VERSION
19](https://www.adobe.com/content/dam/acom/en/devnet/pdf/swf-file-format-spec.pdf)
at https://www.adobe.com/content/dam/acom/en/devnet/pdf/swf-file-format-spec.pdf

This gives information on the internal format of swf-files, but no information how Adobe FlashPlayer uses (was using) it to display the content.
