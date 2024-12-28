---
project: Follow
stars: 21247
description: 🧡 Follow your favorites in one inbox
url: https://github.com/RSSNext/Follow
---

### Follow

Discord · Twitter · Releases  
  

As they say, your thoughts are what you read—and we’ve been consuming noisy feeds for too long! Follow organizes content into one timeline, keeping you updated on what matters, noise-free. Share lists, explore collections, and enjoy distraction-free browsing.

👋🏻 Getting Started & Join Our Community
-----------------------------------------

Whether for users or professional developers, Follow will be your open information playground. Please be aware that Follow is currently under active development, and feedback is welcome for any issue encountered.

Feel free to try it using the following methods:

No installation necessary! Visit our web app to experience it firsthand.

Download and install the desktop client for a smoother experience and enhanced features.

You can also install using the following methods maintained by our community:

-   If you are using Arch Linux, you can install package follow-appimage that maintained by timochan.
-   If you are using Nix, you can install package follow that maintained by iosmanthus.
-   If you are using macOS with Homebrew, you can install cask follow (also @alpha and @nightly) that maintained by realSunyz.

Join our Discord server to connect with developers, request features, and receive support.

Follow us on X/Twitter for product updates and to join in on reward activities.

Important

**Star Us**, You will receive all release notifications from GitHub without any delay ~

✨ Features
----------

### Customized Information Hub

Subscribe to a vast range of feeds and curated lists. Curate your favorites and keep track of what matters most to you.

### AI At Your Fingertips

A smarter and more efficient browsing with AI-powered features like translation, summary, and more.

### Dynamic Content Support

Because we know content is more than just text. From articles to videos, images to audio — Follow gets it all covered.

### $POWER An Ownership Economy

Tip creators across instantly with $POWER, support content you love, and unlock value in your own work. Your content, your power.

### More Than Just An App

This isn’t just another app. Follow is a community — introducing a new era of openness and community-driven experience.

🤝 Contributing
---------------

If you are eligible to use Follow, you are welcome to join the open source community to build together.

Before you start, make sure you have enabled Corepack. Corepack makes sure you are using the correct version (`packageManager` field in `package.json`) for package manager when you run corresponding commands.

corepack enable

Install dependencies.

pnpm install

### Develop in the browser

pnpm run dev:web

Then the browser opens `https://app.follow.is/__debug_proxy`，you can access the online API environment to development and debugging.

### Develop in the electron

You need to fill in the required environment variables first.

cp .env.example .env

Then set `VITE_API_URL` to `https://api.follow.is` and run:

pnpm run dev

Since it is not very convenient to develop in Electron, the first way to develop and contribute is recommended at this stage.

Tip

If you can't log in to the app, copy the `__Secure-better-auth.session_token` in the cookie from your browser into the app.

📝 License
----------

Follow is licensed under the GNU General Public License version 3 with the addition of the following special exception:

All content in the `icons/mgc` directory is copyrighted by https://mgc.mingcute.com/ and cannot be redistributed.

All content in the `lottie` directory is distributed under the Lottie Simple License.
