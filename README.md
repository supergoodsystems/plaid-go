# Supergood GoLang Example Code

This is a simple example of how to integrate the Supergood GoLang client on the Plaid Quickstart Server. This example is meant to be used as a reference and not as a production-ready application.

## Running the Example Code

1. Navigate to `./go/.env` and add the following env variables. Reach out to alex@supergood.ai if you need any of these keys:
   - `PLAID_CLIENT_ID` (at the top of the file)
   - `PLAID_SECRET` (at the top of the file)
   - `SUPERGOOD_CLIENT_ID` (at the bottom of the file)
   - `SUPERGOOD_CLIENT_SECRET` (at the bottom of the file)
2. Navigate to `./frontend` and run `yarn install` and then `yarn start` to start the frontend.
3. Navigate to `./go` run `go build` and then `./start.sh` to start the backend.
4. Refresh the local server browser and you should see a prompt to log in with Plaid. Click the button and choose any bank to connect. The username and password for every integration is `user_good` and `pass_good`.
5. Make some API calls and you should start seeing them populate in the [Supergood dashboard](https://dashboard.supergood.ai/).

## How it Works

The Supergood library is included in `./go/server.go` on line 22 and the initialization call is done on lines 50-53.

On line 52, the native HTTP client is replaced with the Supergood client. The clients are exactly the same, except for the Supergood client running a light interceptor on each outbound request that is made.

There are several optional configuration options that can be passed into the Supergood client. These are documented in the [GoLang SDK](https://docs.supergood.ai/integrate-with-clients/golang). The options included in this demonstration allow the request bodies to be logged for billing tracking and debugging purposes, but all data is completely redacted on the client.

