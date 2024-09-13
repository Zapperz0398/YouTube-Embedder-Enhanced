# Youtube Embedder Enhanced

This is an Obsidian [templater](https://github.com/SilentVoid13/Templater) template designed to embed YouTube videos with additional metadata. It utilizes HTML, CSS, and JavaScript to create a rich-embed for your YouTube video within Obsidian.

![preview.png](preview.png)

## Why I Designed This Template

I designed this template because there was no plugin that was reliable in retrieving the correct data from YouTube. There would always be placeholder values, or no customization options for the look and feel of the embed.

Therefore, I created this template

## Features

- **Full-Width div**: The rich link spans the entire width of the page
- **Responsive Design**: adjusts to different device screen sizes
- **YouTube Integration**: Embeds the YouTube video with a clickable link
- **Metadata Display**: Shows the video title and description.

## Prerequisites

In order to use this template, you will need the following:

- A basic understanding of Obsidian, as well as a grasp on how templates work
- The [templater plugin](https://github.com/SilentVoid13/Templater) must be installed and enabled in your vault
- An internet connection must be active on the device, as the template makes web requests to the YouTube API to retrieve the video data

Additionally, you will need a personal YouTube API key, as discussed in the next section.

## Getting A Youtube API Key

In order to use this template, an API key for the YouTube API needs to be generated and used. I have designed it this way to ensure that the proper data from YouTube is retrieved.

To get a YouTube API key, do the following

1. **Go To The Google Developers Console:**
   - Open your web browser and go to [Google Developers Console](https://console.developers.google.com/).

2. **Create a New Project:**
   - Click on the **project dropdown** at the top of the page.
   - Click **New Project**.
   - Give your project a name (like "**Obsidian YouTube Embedder**") and click **Create**.

3. **Enable The YouTube Data API:**
   - In the search bar at the top, type **YouTube Data API v3** and press Enter.
   - Click on **YouTube Data API v3** from the results.
   - Click the **Enable** button.

4. **Get Your API Key:**
   - Go to the **Credentials** tab on the left menu.
   - Click **Create Credentials** and select **API key**.
   - Your new API key will appear. You can copy this key to use in your app. If you forget it, you can head back to the credentials section, and retrieve it again.

Done. You can now add this API key in the `<API_KEY>` section within the templater template

## Installation

1. Go to the `main.md` file in this repository:
2. Click on the `main.md` file
3. Click on the `raw` button - located at the top right of the page with the template
4. Copy the code and paste it into your Templater folder in your Obsidian Vault
5. Replace the `API_KEY` placeholder in the template with your actual API key
6. Voila, you can now call the template, and follow the popups to embed a YouTube video into your notes.

## Contributing

Contributions are welcome on this project! Please refer to [contributing.md](contributing.md).

## License

This project will be licensed shortly

## Contact

If you would like to get into contact with me, for whatever reason, please shoot me an email at [here](mailto:zapperz0398@gmail.com).
