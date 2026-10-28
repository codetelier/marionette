---
title: Activate Marionette Pro
---

# Activate Marionette Pro

[한국어](ko/activate)

Thank you for buying Marionette Pro. Your license key:

<p><code id="key">(no key in this link: copy it from your receipt email)</code>
<button id="copy" type="button" hidden>Copy</button></p>

<p><a id="open" href="#" hidden><strong>Open Marionette and activate</strong></a></p>

Your browser asks once whether to open Marionette; allow it. Marionette shows its **About** tab and activates the key on this PC.
If Marionette already has a key, it fills the key in and waits for you to press **Register** (so a link alone never replaces your key).

If nothing opens:

1. Make sure Marionette is installed ([how to get it](./#get-it)).
2. Copy the key above, open the Marionette window (double-click the tray icon) → **About** → paste it in **License key** → **Register**.

One key activates one PC. To move it, press **Remove key** on the old PC first.
The key stays on this page only: it is read from the part of the address after `#`, which your browser never sends to a server.
Lost the key? It is in your receipt email and in your Lemon Squeezy order history. Questions: codetelier.support@gmail.com

<script>
(function () {
  var params = new URLSearchParams(location.hash.slice(1) || location.search.slice(1));
  var key = (params.get("key") || "").trim();
  if (!/^[A-Za-z0-9._-]{1,2048}$/.test(key)) return;
  document.getElementById("key").textContent = key;
  var link = "marionette://activate?key=" + encodeURIComponent(key);
  var open = document.getElementById("open");
  open.href = link;
  open.hidden = false;
  var copy = document.getElementById("copy");
  copy.hidden = false;
  copy.onclick = function () {
    navigator.clipboard.writeText(key).then(function () { copy.textContent = "Copied"; });
  };
  location.href = link;
})();
</script>
