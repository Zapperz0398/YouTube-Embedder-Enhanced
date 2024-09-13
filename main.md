<%*
youtubeUrl = await tp.system.prompt("Enter YouTube URL")

const videoIdMatch = youtubeUrl.match(/v=([a-zA-Z0-9_-]+)/);
const videoId = videoIdMatch ? videoIdMatch[1] : null;

if (videoId === null) {
    const message = "> [!Error]\n> Invalid YouTube URL. Please make sure the URL contains a valid video ID.";
    tR += message
} else {
    const apiKey = "<API KEY>";
    const response = await fetch(`https://www.googleapis.com/youtube/v3/videos?part=snippet&id=${videoId}&key=${apiKey}`);

-%>
