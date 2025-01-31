# Shopify Crypto Wallet Integration

[More details here](https://forum.developerdao.com/t/shopify-metamask-app-idea/636)

## Project Components

1. **NextJS Frontend:**
   - Admin dashboard for shop owner to configure eligible contract holders for discounts/custom merch.

2. **NextJS Backend:**
   - Server to store data.
   - Dynamically create promo codes for discounts using Shopify API (research needed).

3. **Widget:**
   - Connects with [crypto wallet](https://twitter.com/developer_dao/status/1466080091327369225).
   - Verifies user eligibility for discounts/custom merch.
   - Fetches and applies promo code to user's cart.

## Requirements

- [Create a Shopify partner account](https://partners.shopify.com/signup) if you don’t have one.
- [Create a Development store](https://help.shopify.com/en/partners/dashboard/development-stores#create-a-development-store) for app installation and testing.
- In the Partner dashboard, [create a new app](https://help.shopify.com/en/api/tools/partner-dashboard/your-apps#create-a-new-app) and obtain API credentials.
- [Sign up for NGROK](https://ngrok.com/signup) to host your app in development.

## Development Steps

1. Clone the project and run `npm install`.
2. Create `.env` from `.env.example`.
3. Add `SHOPIFY_API_KEY=<your API key>` from your Shopify App settings.
4. Add `SHOPIFY_API_SECRET=<your API secret>`.
5. Add `SHOP=<your shop>.myshopify.com`.
6. Leave `SCOPES` as in the example for now.
7. Start NGROK and replace `HOST` with your `NGROK URL`.

### Shopify App Settings

- Set `App URL` to `NGROK URL`.
- Set `Allowed redirection URL(s)` to `<NGROK URL>/auth/callback` (e.g., https://1231231.ngrok.io/auth/callback).

> _Update `NGROK URL` every time it changes._

8. Run `npm run dev`.
9. Click `Select store` under `Test your app` in Shopify App settings.
10. Install the app in your development store and open it in the admin dashboard.

> _Common error: `The redirect URI is not whitelisted`. Update `NGROK URL` in `Allowed redirection URL(s)`._

## Theme App Extension

Example: [Theme App Extension](https://github.com/Shopify/theme-extension-getting-started)

1. Navigate to `theme-app-extension` and run `shopify extension register`, choose `THEME_APP_EXTENSION` type.
2. Run `npm run create-extension-js-bundle` to bundle `crypto-wallet.js` and place it in `theme-app-extension/assets`.
3. Run `shopify extension push` and follow instructions to install the extension on the Shopify theme.

Demo: [Loom Video](https://www.loom.com/share/9c21c12fc567417e9f3e6e910b65f874)

Demo Shopify Page: [sergey-metamask-test.myshopify.com](https://sergey-metamask-test.myshopify.com), store password: `rubado`.

WIP: [Loom Video](https://www.loom.com/share/9cb9caccd1494387937ae
