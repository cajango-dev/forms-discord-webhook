📦 Google Forms to Discord Webhook Integration
This Google Apps Script connects your Google Forms responses directly to a Discord webhook, sending form submissions as formatted messages (either plain text or rich embeds) to your desired Discord channel.

📖 Features
✅ Sends new form responses automatically to a Discord channel.

✅ Supports plain text or rich embed format.

✅ Converts numeric 18-digit strings into Discord user mentions.

✅ Detects Google Drive file IDs and turns them into clickable links.

✅ Automatically displays the first image (from a direct link or Drive image) inside the embed.

✅ Validates URLs and limits message length to avoid exceeding Discord's 2000 character limit.

📝 How it works
When a new response is submitted to the Google Form, the script collects each response and sends it to one or more Discord webhooks. The message can be plain text or an embed with title, description, image, and colors.

📂 Files
Code.gs — main script file containing:

Webhook validation

Response formatting

Link, mention, and image processing

Message dispatch (plain text or embed)

⚙️ Configuration
Replace the webhook URL:
const webhooks = ["https://discord.com/api/webhooks/xxxxxxxxxxxxxxxx/yyyyyyyyyyyyyyyyyyyyyyyyyyyy"];

Customize optional settings:

const title = "Form Response";
const avatarImage = "https://example.com/avatar.png";
const shortDescription = "New form submission:";
const colour = "#2c006e";  // Hex color code
const mention = "<@!123456789012345678>";  // Discord user mention
const type = "";  // Leave empty or set to "text" for plain text

Bonus Features Toggle:

const bonusFeatures = {
  convert2Link: 'ON',
  convert2Mention: 'ON'
}

📸 Image Handling
If a form answer contains a Google Drive File ID (25+ character string), it automatically generates a public preview link and:

Adds a clickable link inside the message.

Shows the first image in the embed image field.

If a form answer contains a direct image URL (ending with .jpg, .png, .webp, etc.), it will be converted into a clickable link and displayed inside the embed as well.

🚀 Deployment
Open your Google Form.

Click on Extensions > Apps Script.

Replace the default code with this script.

Set up a trigger to run embedText or plainText on form submission.

Save and authorize the script.

📌 Notes
Only the first detected image (direct URL or Drive image) will be embedded per message.

Discord's message limit is 2000 characters per message.

Drive file links must have public or anyone with the link can view permission for Discord to preview them.
