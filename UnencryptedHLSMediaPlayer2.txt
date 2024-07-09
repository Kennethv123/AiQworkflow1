document.addEventListener("DOMContentLoaded", () => {
    var HlsVideo = document.getElementById("Bvideo");
    var HlsVideoSrc = "https://dfflvukqjg5l4.cloudfront.net/leo480p_no_audio.m3u8";

    
    const defaultOptions = {};

    try {
        if (Hls.isSupported()) {
            var hls = new Hls();
            hls.loadSource(HlsVideoSrc);
    
            HlsVideo.controlsList = "noplaybackrate";
            HlsVideo.disablePictureInPicture = true;

            hls.attachMedia(HlsVideo);
    
            updateHls(hls)
    
        }
    } catch (error) {
        window.alert(error);
    }


    function updateQuality(newQuality) {
        window.hls.levels.forEach((level, levelIndex) => {
            
            if(level.height === newQuality){
                window.hls.currentLevel = levelIndex
            }
        })
    }
    function updateHls(hls) {
        window.hls = hls
    }

    /*
    var audio = new Howl({
        src: "https://dfflvukqjg5l4.cloudfront.net/4.%20Leo%20-%20Netflix%20-%20Vietnamese%20audio%20sound%20track.mp3"
    })
    
    HlsVideo.addEventListener('play', function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            audio.play();

            MainVideo.play();
            VideoC.play();
            VideoD.play();
        }
    })

    HlsVideo.addEventListener('pause', function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            audio.pause();

            MainVideo.pause();
            VideoC.pause();
            VideoD.pause();
        }
    })

    HlsVideo.addEventListener("seeked", async function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            var MT = HlsVideo.currentTime;
            MainVideo.currentTime = MT;
            VideoC.currentTime = MT;
            VideoD.currentTime = MT;
        }
    })
    HlsVideo.addEventListener('timeupdate', function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            audio.seek(HlsVideo.currentTime);
        }
    })

    var observer = new MutationObserver(function(mutationsList, observer){
        if (HlsVideo.parentNode.id !== "AScreenNode") {
            audio.pause();
        }
    })

    observer.observe(HlsVideo, { attributes: true, childList: true, subtree: true });
    */
})

