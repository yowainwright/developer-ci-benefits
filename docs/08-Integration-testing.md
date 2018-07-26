# Acceptance Testing

This document discusses acceptance testing.

---

### Difference between Acceptance Testing and End-to-end Testing Aside

[Integration tests](https://en.wikipedia.org/wiki/Integration_testing) work similarly to [End-to-end tests](https://medium.freecodecamp.org/why-end-to-end-testing-is-important-for-your-team-cb7eb0ec1504). They go through particular tests flows to define passing or failing scenarios.

For example, if we have a repository that contains a chunk of code that has a browser testable interface but is not a full interface, an Integration test can test that block of code using similar tooling as an End-to-end test would use. The difference that an End-to-end test is meant to test a complete interface as if it is in production. The Integration test only tests a chunk of the interface.

---

## Integration Testing Example

The example below is an Integration test. The test assumes a local server is running.

```javascript
/**
 * Integration Test
 * An iframe exists
 */

import puppeteer from 'puppeteer'

const APP = 'http://localhost:3000/sandbox/'
const IFRAME = 'http://localhost:3001/<location>/assets/iframe/'

describe('confirm that the <iframe/> loads', () => {
  let browser
  const width = 1920
  const height = 1080
  beforeAll(async () => {
    browser = await puppeteer.launch({
      headless: false,
      slowMo: 80,
      args: [`--window-size=${width},${height}`],
    })
    page = await browser.newPage()
    await page.setViewport({ width, height })
  })
  afterAll(() => browser.close())
  test('the iframe exists', async () => {
      await page.goto(APP)
      await page.waitForSelector('iframe')
      const frames = await page.frames()
      frames.find(frame =>if (frame.url().includes(IFRAME)) frame.click())
    }, 16000)
  })
})
```

---

The code above spins up a browser instance using Puppeteer. Once the browser is running, Puppeteer goes to `APP`, looks for an `iframe`, and "clicks" it. Tests such as this can be very useful to testing parts of compiled bit of a codes interface. In the test above, the code tests if the `<iframe>` loads. This is useful to catching compilation errors before committing updates for full end-to-end tests.
