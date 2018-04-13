## Channel

PlayChat currently supports channels such as Kakao, Facebook, Naver TalkTalk, Line, WeChat and etc. Users may connect the chatbots they have developed to these channels for personal services.

## Kakao

To distribute chatbots to Kakao, follow these procedures.

1. Sign-up “for Kakao Plus Friends” ([https://center-pf.kakao.com/login](https://center-pf.kakao.com/login))

1. Create a new plus friend.

2. Access through the plus friends management center.

3. Move to the smart chatting menu and click on “setting type of API”.

4. Enter the app name, URL, description, and phone number. Set the URL as the given Webhook URL.

## Facebook

PlayChat provides an automatic facebook connection. Click on “Connect” under the facebook logo and connect it to your PlayChat page. (If you have no page, create a new one)

## Naver TalkTalk

1. Access Naver TalkTalk partner center. (partner.talk.naver.com)

2. Log-in with a company group id or a representative personal id.

3. Click on “My account management” -> “Create new TalkTalk account”

4. Choose “later/not now” at the service selection page.

5. When creating a test account, select individual, when creating a service account select licensee or institution and then enter the profile picture, description and phone number to apply for usage.

6. The created account will be under examination, and when that is over it will be switched over to “being used” and will notify you via SMS.

7. In the registered account list of the account management page, click on “Home account by managing account”.

8. Through the API set-up page of the left screen menu, set up the terms and conditions agreement, and the chatbot itself. (a usage application is needed in beta period)

9. Once the API usage is approved by Naver, enter the URL provided by PlayChat and connect.

## LINE

To distribute chatbots to Line, follow these procedures.

1. Download and open the Line mobile app.

2. Settings menu -> Account -> E-mail

3. Enter your email address and password to register.

4. Access [https://developers.line.me/](https://developers.line.me/) to click on the “Start using Messaging API” button.

5. Log-in using the email you used in #3.

6. In the screen that appears after the verification process, enter the provider’s name and email address.

7. Create a channel following the procedures on the screen.

8. In the created channel, click on the “Configuration not yet complete” button.

9. In the messaging settings menu, set “Use webhooks” as “enable”.

10. Enter the Webhook URL.

11. Create a channel access token, and then enter it under  “ChannelId, Channel Secret, Access Token” and click save.
