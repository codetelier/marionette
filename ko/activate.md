---
title: Marionette Pro 활성화
lang: ko
---

# Marionette Pro 활성화

[English](../activate)

Marionette Pro를 구매해 주셔서 감사합니다. 라이선스 키:

<p><code id="key">(이 링크에 키가 없습니다: 영수증 메일에서 복사하세요)</code>
<button id="copy" type="button" hidden>복사</button></p>

<p><a id="open" href="#" hidden><strong>Marionette 열고 활성화</strong></a></p>

브라우저가 Marionette를 열지 한 번 묻습니다. 허용하면 Marionette가 **정보** 탭을 열고 이 PC에서 키를 활성화합니다.
이미 등록된 키가 있으면 키를 칸에 채워 두기만 하고 **등록**을 누를 때까지 기다립니다(링크만으로 키가 바뀌지 않게).

아무것도 열리지 않으면:

1. Marionette가 설치되어 있는지 확인하세요([받는 방법](./)).
2. 위 키를 복사해 Marionette 창(알림 영역 아이콘 두 번 클릭) → **정보** → **라이선스 키**에 붙여 넣고 → **등록**.

키 하나로 PC 1대를 활성화합니다. 다른 PC로 옮기려면 먼저 쓰던 PC에서 **키 삭제**를 누르세요.
키는 이 페이지에만 있습니다. 주소의 `#` 뒷부분에서 읽으며, 브라우저는 이 부분을 서버로 보내지 않습니다.
키를 잃어버렸으면 영수증 메일과 Lemon Squeezy 주문 내역에 있습니다. 문의: codetelier.support@gmail.com

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
    navigator.clipboard.writeText(key).then(function () { copy.textContent = "복사함"; });
  };
  location.href = link;
})();
</script>
