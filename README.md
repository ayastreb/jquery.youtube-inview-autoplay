# YouTube in-view auto-play plugin

This plugin is using https://github.com/protonet/jquery.inview and [YouTube Iframe API](https://developers.google.com/youtube/iframe_api_reference) to setup multiple embeded YouTube players and starts playing them once the player is scrolled in browser view.

* **Author:** Anatoliy Yastreb
* **Live Demo:** https://11route.com/en/menorca-spain
* **Requires:** jQuery 1.8+

## Usage

In page markup videos can be stored as `<div>` elements with data attributes, e.g:
```html
<div class="youtube-video" 
     id="menorca-faro-de-favarix" 
     data-video-id="o2Fs6SoRHCk" 
     width="1000" 
     height="563"></div>
```
First, you need to load YouTube API. Then you need to apply plugin to all video elements:
```javascript
<script type="text/javascript">
  // Load the IFrame Player API code asynchronously.
  var tag = document.createElement('script');
  tag.src = "https://www.youtube.com/player_api";
  var firstScriptTag = document.getElementsByTagName('script')[0];
  firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

  function onYouTubeIframeAPIReady() {
    $('.youtube-video').inViewAutoplay({
      autohide: 1,
      modestbranding: 1,
      rel: 0,
      quality: 'hd720'
    });
  }
</script>
```

In plugin call you can pass player parameters object, for a list of supported parameters see: https://developers.google.com/youtube/player_parameters#Parameters
