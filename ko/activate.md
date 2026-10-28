---
title: Marionette Pro 활성화
lang: ko
---

# Marionette Pro 활성화

[English](../activate)

Marionette Pro를 구매해 주셔서 감사합니다. 라이선스 키는 Lemon Squeezy가 보낸 **영수증 메일**에 있습니다.

## 세 단계로 활성화

1. 영수증 메일에서 라이선스 키를 복사합니다.
2. Marionette 창을 엽니다(알림 영역의 Marionette 아이콘 두 번 클릭) → **정보** 탭.
3. **라이선스 키** 칸에 붙여 넣고 **등록**을 누릅니다. 라이선스 줄이 **Pro**로 바뀝니다.

키를 등록할 때 한 번 인터넷이 필요합니다. 아직 설치하지 않았다면 [받는 방법](./)을 보세요.

<div id="link" hidden markdown="0">
<p>이 링크에 라이선스 키가 들어 있습니다:</p>
<p><code id="key"></code> <button id="copy" type="button">복사</button></p>
<p><a id="open" href="#"><strong>Marionette 열고 활성화</strong></a></p>
<p>브라우저가 Marionette를 열지 한 번 묻습니다. 허용하세요. 이미 등록된 키가 있으면 키를 칸에 채워 두기만 하고 <strong>등록</strong>을 누를 때까지 기다립니다.
키는 브라우저 안에만 있습니다. 주소의 <code>#</code> 뒷부분에서 읽으며, 브라우저는 이 부분을 서버로 보내지 않습니다.</p>
</div>

## 알아 둘 것

- 키 하나로 PC 1대를 활성화합니다. 다른 PC로 옮기려면 쓰던 PC에서 먼저 **키 삭제**를 누른 뒤 새 PC에서 등록하세요.
- 메일을 잃어버렸으면 Lemon Squeezy 주문 내역([My Orders](https://app.lemonsqueezy.com/my-orders))에도 키가 있습니다.
- 문의: codetelier.support@gmail.com

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
    navigator.clipboard.writeText(key).then(function () { copy.textContent = "복사함"; });
  };
  document.getElementById("link").hidden = false;
  location.href = link;
})();
</script>
