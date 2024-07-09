var HlsVideo;

document.addEventListener("DOMContentLoaded", () => {
    HlsVideo = document.getElementById("Dvideo");
    var HlsVideoSrc = "https://dfflvukqjg5l4.cloudfront.net/leo480p_no_audio.m3u8";
    const defaultOptions = {};

    if (Hls.isSupported()) {
        var hls = new Hls();
        hls.loadSource(HlsVideoSrc);
        hls.attachMedia(HlsVideo);

        updateHls(hls)
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
        src: "https://dfflvukqjg5l4.cloudfront.net/7.%20Leo%20-%20Netflix%20-%20Spanish%20audio%20sound%20track.wav"
    })


    HlsVideo.addEventListener('play', function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            audio.play();

            VideoB.play();
            VideoC.play();
            MainVideo.play();
        }
    })

    HlsVideo.addEventListener('pause', function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            audio.pause();

            VideoB.pause();
            VideoC.pause();
            MainVideo.pause();
        }
    })

    HlsVideo.addEventListener("seeked", async function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            var MT = HlsVideo.currentTime;
            VideoB.currentTime = MT;
            VideoC.currentTime = MT;
            MainVideo.currentTime = MT;
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

