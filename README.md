# api-ai-facebook
Facebook bot sources for Api.ai integration

# Changes
This version allow to have multiple facebook pages using the same bot.

Format of FB_PAGES_TOKEN:
```javascript
{
 "recipient_id": "fb_token",
}
```

Example:

```javascript
{
 "1132314666210914": "BB2WeuNOq0LgBBC21ZBXZCEd3R4FhQEcCTQCe19vt6x1Fb1iXfuPxGBcIwZBy42sgqfZBnZARGMOXoJNxEDWZCjjuQWnJ1eSIDAsrRNWDf0aa4495VNkarbI3k4pZBE26zwlcxSHUAQ6tzCFdtM17OpuZAsxjuytDaIMzQBT8weQB4wZDAD",
 "2222223333333444": "ATQCe19vt6x1Fb1iXfuPxGBcIwZBy42sgqfZCe19vt6x1Fb1iXfuPxGBcIwZBy42sgqfZBnZARGMOXoJNxEDWZCjjuQWnJ1eSIDAsrRNWDf0aa4495VNkarbI3k4pZBE26zwlcxSHUAQ6tzCFdtM17OpuZAsxjuytDaIMzQBT8uPxGBcGJD",
 "1234567891234567": "7OpuZAsxjuytDaIMzQBT8uPxGBcGJATQCe19vt6x1Fb1iXfuPxGBccIwZBy42sgqfZBnZARGMOXoJNxEDWZCjjuQWnJ1eSIDAsrRNWDf0aa4495VNkarbI3kIwZBy42sgqfZCe19vt6x1Fb1iXfuPxGB4pZBE26zwlcxSHUAQ6tzCFdtM1D"
 }
```

You can find your recpient_id (Page ID) with this site: https://findmyfbid.com/


## Deploy with Heroku
Follow [these instructions](https://docs.api.ai/docs/facebook-integration#hosting-fb-messenger-bot-with-heroku).
Then,  
[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

## Deploy with Docker

```bash
docker run -it --name fb_bot \
           -p <your_desired_port>:5000 \
           -e APIAI_ACCESS_TOKEN="API.AI client access token" \
           -e FB_PAGES_TOKEN="{\"recipient_id\": \"fb_token\",\"recipient_id2\": \"fb_token2\"}" \
           -e FB_VERIFY_TOKEN="Facebook Verify Token" \
           -e APIAI_LANG="en" \
           xvir/api-ai-facebook
```

## Note about languages:
When you deploy the app manually to Heroku, the APIAI_LANG not filled with a value.
You need to provide language parameter according to your agent settings in the form of two-letters code.
 
 * "en"
 * "ru"
 * "de"
 * "pt"
 * "pt-BR"
 * "es"
 * "fr"
 * "it"
 * "ja"
 * "ko"
 * "zh-CN"
 * "zh-HK"
 * "zh-TW"
