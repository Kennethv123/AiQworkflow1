
document.addEventListener("DOMContentLoaded", () => {
    var HlsVideo = document.getElementById("Cvideo");
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

    var audio1 = new Howl({
        src: "https://dfflvukqjg5l4.cloudfront.net/4.%20Leo%20-%20Netflix%20-%20Vietnamese%20audio%20sound%20track.mp3",
        volume: 1
    })
    var audio2 = new Howl({
        src: "https://dfflvukqjg5l4.cloudfront.net/Leo1080p_English_with_CC.mp3",
        volume: 0.5
    })
   
    HlsVideo.addEventListener('play', function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            audio1.play();
            audio2.play();

            VideoB.play();
            MainVideo.play();
            VideoD.play();
        }
    })

    HlsVideo.addEventListener('pause', function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            audio1.pause();
            audio2.pause();

            VideoB.pause();
            MainVideo.pause();
            VideoD.pause();
        }
    })

    HlsVideo.addEventListener("seeked", async function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            var MT = HlsVideo.currentTime;
            VideoB.currentTime = MT;
            MainVideo.currentTime = MT;
            VideoD.currentTime = MT;
        }
    })
    HlsVideo.addEventListener('timeupdate', function() {
        if (HlsVideo.parentNode.id == "AScreenBox") {
            audio1.seek(HlsVideo.currentTime);
            audio2.seek(HlsVideo.currentTime)
        }
    })

    var observer = new MutationObserver(function(mutationsList, observer){
        if (HlsVideo.parentNode.id !== "AScreenNode") {
            audio1.pause();
            audio2.pause();
        }
    })

    observer.observe(HlsVideo, { attributes: true, childList: true, subtree: true });
    */
})


