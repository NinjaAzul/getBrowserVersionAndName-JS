# getBrowserVersionAndName-JS
getBrowserVersionAndName JS


```ts

function getBrowserInfo() {
  const userAgent = navigator.userAgent;

  const getBrowserVersion = (regex) => {
    const match = userAgent.match(regex);
    return match && match[1] ? match[1] : "";
  };

  if (/opr\//i.test(userAgent) || !!window.opr) {
    return {
      name: 'Opera',
      version: getBrowserVersion(/(?:opr|opera)\/([\d.]+)/i)
    };
  } else if (/edg/i.test(userAgent)) {
    return {
      name: 'Microsoft Edge',
      version: getBrowserVersion(/edg(?:\/|\s)([\d.]+)/i)
    };
  } else if (/chrome|chromium|crios/i.test(userAgent)) {
    return {
      name: 'Google Chrome',
      version: getBrowserVersion(/(?:chrome|crios)\/([\d.]+)/i)
    };
  } else if (/firefox|fxios/i.test(userAgent)) {
    return {
      name: 'Mozilla Firefox',
      version: getBrowserVersion(/(?:firefox|fxios)\/([\d.]+)/i)
    };
  } else if (/safari/i.test(userAgent)) {
    return {
      name: 'Apple Safari',
      version: getBrowserVersion(/version\/([\d.]+)/i)
    };
  } else if (/trident/i.test(userAgent)) {
    return {
      name: 'Microsoft Internet Explorer',
      version: getBrowserVersion(/trident\/([\d.]+)/i)
    };
  } else if (/ucbrowser/i.test(userAgent)) {
    return {
      name: 'UC Browser',
      version: getBrowserVersion(/ucbrowser\/([\d.]+)/i)
    };
  } else if (/samsungbrowser/i.test(userAgent)) {
    return {
      name: 'Samsung Browser',
      version: getBrowserVersion(/samsungbrowser\/([\d.]+)/i)
    };
  } else {
    return {
      name: 'Unknown browser',
      version: ''
    };
  }
}

const browserInfo = getBrowserInfo();
console.log(browserInfo);
```
