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

    if (!response.ok) {
        tR += "> [!Error]\n> Failed to fetch YouTube video data.";
    } else {
        const videoData = await response.json();

        if (videoData.items.length === 0) {
            tR += "> [!Error]\n> No video found for the provided ID.";
        } else {
            tR += working

            const title = videoData.items[0].snippet.title; 
            const description = videoData.items[0].snippet.description; 
            const thumbnailUrl = videoData.items[0].snippet.thumbnails.medium.url;

-%>
