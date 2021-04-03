<h1 align="center">
<strong>gatsby-plugin-google-adsense</strong>
</h1>

<p align="center">
Add Google Adsense to your Gatsby site.
</p>

<p align="center">
<img alt="npm (scoped)" src="https://img.shields.io/npm/v/@isamrish/gatsby-plugin-google-adsense">
<img alt="npm" src="https://img.shields.io/npm/dt/@isamrish/gatsby-plugin-google-adsense">
</p>

## Install

```
npm install @isamrish/gatsby-plugin-google-adsense
```

or

```
yarn add @isamrish/gatsby-plugin-google-adsense
```

## Usage in Gatsby website

```javascript
// In your gatsby-config.js
module.exports = {
  plugins: [
    {
      resolve: `@isamrish/gatsby-plugin-google-adsense`,
      options: {
        googleAdClientId: "YOUR_GOOGLE_ADSENSE_TRACKING_ID",
        head: false // Optional
      }
    }
  ]
};
```

## Options

### `googleAdClientId`

Here you place your Google Adsense tracking id.

### `head`

Here you can define where to place the tracking script. With `head:true` it will placed in the header, with `head:false` it will placed in the body. Default is `false`.

Google adsense recommends to put script in [head tag](https://support.google.com/adsense/answer/9274516).

## Example of Adsense component

```javascript
// In your adsense component
import React from "react";

export default function AdSense() {
  React.useEffect(() => {
    if (process.env.NODE_ENV !== "development") {
      if (window) {
        try {
          (window.adsbygoogle = window.adsbygoogle || []).push({});
        } catch (error) {
          console.log(error, "adsenese error");
        }
      }
    }
  }, []);

  return (
    <ins
      className="adsbygoogle"
      data-ad-client="ca-pub-XXXXXX"
      data-ad-slot="XXXXXXX"
      style={{
        display: "block"
      }}
      data-ad-format="auto"
      data-full-width-responsive="true"
    ></ins>
  );
}
```
