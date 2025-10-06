# Resonate - An Open Source Social Voice Platform

### This project is divided into two repositories:

1. [Resonate Flutter App](https://github.com/AOSSIE-Org/Resonate)
2. Resonate Backend (You are here)

Go to [this repository](https://github.com/AOSSIE-Org/Resonate) to know more about the project.

## Environment Setup

1. Pre-requisites

    (a) Fork the Repo

    (b) Clone the Repo: `git clone https://github.com/AOSSIE-Org/Resonate-Backend`

2. Set up environment variables

```bash
cp .env.example .env
```

Then fill in the values in `.env`:
   - Leave the database/collection IDs as they are (they match the project structure)
   - Add your Livekit credentials (see step 3)
   - Add your email credentials (see step 5)

3. Obtain Livekit credentials

- Follow this guide to get your credentials.
- Add `LIVEKIT_HOST`, `LIVEKIT_API_KEY`, `LIVEKIT_API_SECRET` to your `.env` file.

4. Set up Appwrite

- Create a project on Appwrite Cloud or self-host.
- Create an API key with necessary scopes.
- Import the database structure: `appwrite deploy collection`.
- Copy the generated database and collection IDs into your `.env` file.

5. Email configuration (for OTP functionality)

- Set `SENDER_MAIL` to your email address.
- Set `SENDER_PASSWORD` to your app password (Gmail guide).

6. Security note

- Do not hardcode secrets in `appwrite.json`. Use environment variables. The template `.env.example` lists all variables required across functions.

## Functions :

(a) [Room Creation function](functions/create-room) : Function to create rooms in Appwrite and Livekit.

(b) [Room Deletion function](functions/delete-room) : Function to remove rooms from Appwrite and Livekit.

(c) [Room Joining function](functions/join-room) : Function to join room in Livekit.

(d) [Livekit Webhook Receiver function](functions/livekit-webhook) : Function to receive webhooks from Livekit.

(e) [Match Maker function](functions/match-maker) : Function to pair users for pair-chat feature.

(f) [Send OTP function](functions/send-otp) : Function to send OTPs.

(g) [Verify OTP function](functions/verify-otp) : Function to verify OTPs.

(h) [Verify Email function](functions/verify-email) : Function to verify email ID of users.

(i) [discussion-isTime-checker](functions/discussion-isTime-checker/) : A Cron Function to check all the existent Discussion scheduled timings and comparing to current time in order to activate a discussion if the current time is less than 5 minutes away from the scheduled time

(j) [database-cleaner](functions/database-cleaner/) : Function to cleanup active pairs and participants collections in the database.

## Communication Channels

If you have any questions, need clarifications, or want to discuss ideas, feel free to reach out through the following channels:

-   [Discord Server](https://discord.com/invite/6mFZ2S846n)
-   [Email](mailto:aossie.oss@gmail.com)

We appreciate your contributions and look forward to working with you to make this project even better!
