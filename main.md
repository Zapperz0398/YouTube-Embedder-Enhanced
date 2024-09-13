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
            const title = videoData.items[0].snippet.title; 
            const description = videoData.items[0].snippet.description; 
            const thumbnailUrl = videoData.items[0].snippet.thumbnails.medium.url;

            const richPreview = ` <a href="https://example.com" style="text-decoration: none;">
    <div style="display: flex; align-items: center; max-width: 100vw; font-family: Arial, sans-serif; border-radius: 8px; overflow: hidden; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);">
        <div style="flex-shrink: 0; width: 250px; height: 135px;">
            <img src="${thumbnailUrl}" alt="${title}" style="width: 100%; height: 100%; object-fit: cover; border-radius: 4px;">
        </div>
        <div style="margin-left: 15px; padding: 10px;">
            <h2 style="margin: 0 0 5px; font-size: 16px; color: #333;">${title}</h2>
            <p style="margin: 0; font-size: 12px; color: #666;">${description.substring(0, 100)}...</p>
            <p style="font-size: 10px; color: #888;">Click to watch on YouTube</p>
        </div>
    </div>
</a>`
        tR += richPreview
            }
        }
    }
-%>
