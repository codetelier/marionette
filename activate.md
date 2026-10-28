---
title: Activate Marionette Pro
---

# Activate Marionette Pro

[한국어](ko/activate)

Thank you for buying Marionette Pro. Your license key is in the **receipt email** from Lemon Squeezy.

## Activate in three steps

1. Copy the license key from the receipt email.
2. Open the Marionette window (double-click the Marionette icon in the notification area) and go to the **About** tab.
3. Paste the key in **License key** and press **Register**. The license line changes to **Pro**.

Marionette needs the internet once to register the key. Not installed yet? See [how to get it](./#get-it).

<div id="link" hidden markdown="0">
<p>This link carries a license key:</p>
<p><code id="key"></code> <button id="copy" type="button">Copy</button></p>
<p><a id="open" href="#"><strong>Open Marionette and activate</strong></a></p>
<p>Your browser asks once whether to open Marionette; allow it. If Marionette already has a key, it only fills the key in and waits for you to press <strong>Register</strong>.
The key stays in your browser: it is read from the part of the address after <code>#</code>, which browsers never send to a server.</p>
</div>

## Good to know

- One key activates one PC. To move it, press **Remove key** on the old PC first, then register the key on the new one.
- Lost the email? Your key is also in your Lemon Squeezy order history ([My Orders](https://app.lemonsqueezy.com/my-orders)).
- Questions: codetelier.support@gmail.com

<script>
(function () {
  var params = new URLSearchParams(location.hash.slice(1) || location.search.slice(1));
  var key = (params.get("key") || "").trim();
  if (!/^[A-Za-z0-9._-]{1,2048}$/.test(key)) return;
  document.getElementById("key").textContent = key;
  var link = "marionette://activate?key=" + encodeURIComponent(key);
  document.getElementById("open").href = link;
  var copy = document.getElementById("copy");
  copy.onclick = function () {
    navigator.clipboard.writeText(key).then(function () { copy.textContent = "Copied"; });
  };
  document.getElementById("link").hidden = false;
  location.href = link;
})();
</script>
