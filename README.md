# Progressive web apps
## What is this? 

Progressive Web Apps are web applications that have been designed so they are capable, reliable, and installable. These three pillars transform them into an experience that feels like a platform-specific application.

Installed Progressive Web Apps run in a standalone window instead of a browser tab.

**Native apps** have many capabilities. They can read and write files from the local file system, access hardware connected via USB, serial or bluetooth, and even interact with data stored on your device, like contacts and calendar events.

**Web apps** can reach anyone, anywhere, on any device with a single codebase.

**Progressive web apps** are mix of both

*(PWA) are built and enhanced with modern APIs to deliver enhanced capabilities, reliability, and installability while reaching anyone, anywhere, on any device with a single codebase.*

![What is PWA](https://web-dev.imgix.net/image/tcFciHGuF3MxnTr1y5ue01OGLBn2/1DKtUFjXLJbiiruKA9P1.svg)


## Why PWA?

- Fast,
- 50% of users don't want to download an app,
- Native apps are heavy, an installed PWA usually takes less than 1MB,
- Users are more likely to purchase from mobile sites that offer relevant recommendations and 85% of smartphone users say mobile notifications are useful.
- The app can be added to your home screen (A2HS, aka “installed”),
- PWA has a name and an icon that can be customized,
- There’s a splash screen displayed to the user as the app starts up (UX)

![PWA pros](https://web-dev.imgix.net/image/admin/u1jcKrBBOHEzSz3SqhEB.jpg?auto=format&w=1600)
![PWA ideas](https://web-dev.imgix.net/image/admin/ubglZLCoddAfB5cl8JSz.jpg?auto=format&w=1600)
![PWA ideas](https://web-dev.imgix.net/image/admin/UfjYsWQWJjVIk2sp5bnE.jpg?auto=format&w=1600)


## Examples of PWAs
Twitter, Uber, Instagram, Forbes, Pinterest, BMW, Starbucks, Spotify, much much more 🙃

## PWA requirements
- **Valid secure HTTPS connection** (*doesn't apply to localhost*)

Security reasons but also SEO indexing

- **Valid installed JSON manifest**

Each time a visitor loads a new page, the service worker will cache the JSON extract and store it physically in the shell app. This shell is an autonomous container with all the style sheets, scripts, images, fonts and HTML outputs necessary to enable a user to represent a complete page without loading anything else.

- **Installed service worker**

*With CRA Service Worker is only enabled in the **production environment***

Service worker is responsible for caching all the files, push notifications, content updates, data handling and much more.

It will handle requests with appropriate responses depending on whether there is an Internet connection or not, allowing customized pages offline.


## What is Service Worker?

A service worker is a script that your browser runs in the background, separate from a web page, opening the door to features that don't need a web page or user interaction. Today, they already include features like push notifications and background sync and have ability to intercept and handle network requests, including programmatically managing a cache of responses.

In the future, service workers might support other things like periodic sync or geofencing.


## Turn CRA to PWA
1) npx create-react-app my-app --template cra-template-pwa
2) Create manifest.json file in root directory
3) Add ```serviceWorker.register()``` line to index.tsx which will result with:

Ad 3) All static site assets are cached so that your page loads fast on subsequent visits, regardless of network connectivity (such as 2G or 3G). Updates are downloaded in the background.
   Your app will work regardless of network state, even if offline. This means your users will be able to use your app at 10,000 feet and on the subway.


## What you need to remember about

Use a browser that supports service workers — like Chrome, Firefox, Opera, Samsung Internet, Safari, or Edge. (Note: service workers aren’t supported by any browser when in private or incognito mode).

Be aware of when the app is working offline. Once the service worker has initially populated the caches, show your users a message informing them that the app can now be used offline.

Close existing browser tabs to see the latest updates. By default, a service worker is kept on standby after it fetches content updates. As a result, users won’t be able to see the changes until after they close all open tabs and load a fresh page.
