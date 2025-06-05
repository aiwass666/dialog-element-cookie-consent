# Dialog Element Cookie Consent
A simple, fast, easy and Cookie Consent using the HTML &lt;dialog> element instead of &lt;div> elements. The idea was to create something that will render as fast as possible and have as little impact as possible on the rendering process. It is faster than using 

### Code scippets 

### CSS
```CSS
body {font-family: sans-serif;margin: 0;padding: 0;display: flex;justify-content: center;align-items: center;min-height: 100vh;background-color: #f5f5f5;}
dialog {border: none;padding: 0;background: transparent;}
dialog::backdrop {background: rgba(0, 0, 0, 0.4);}
.cookie-banner {position: fixed;bottom: 20px;left: 50%;transform: translateX(-50%);width: calc(100% - 40px);max-width: 450px;padding: 20px;background-color: #fff;border: 1px solid #ddd;border-radius: 8px;box-shadow: 0 4px 15px rgba(0, 0, 0, .1);z-index: 9999;text-align: center;}
.cookie-banner p {margin-bottom: 15px;color: #333;line-height: 1.5;}
.cookie-banner button {padding: 10px 20px;border: none;border-radius: 5px;background-color: #007bff;color: white;cursor: pointer;font-size: 1rem;}
.cookie-banner button:hover {background-color: #0056b3;}
```
### HTML
```HTML
<dialog id="cookieConsentDialog">
<div class="cookie-banner">
<p>We use cookies to enhance your experience. By continuing to visit this site, you agree to our use of cookies.</p>
<button id="acceptCookies">Got it!</button>
</div>
</dialog>
```
### Javascript
```javascript
const cookieConsentDialog = document.getElementById('cookieConsentDialog');
const acceptCookiesBtn = document.getElementById('acceptCookies');
// Show the dialog when the page loads
cookieConsentDialog.showModal();
// Close the dialog when the button is clicked
acceptCookiesBtn.addEventListener('click', () => {
cookieConsentDialog.close();
// In a real app, you'd set a cookie/local storage item here
// to remember the user's consent and prevent showing it again.
});
```
