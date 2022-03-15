## AJAX(Asynchronous Javascript And XML)

### 1. AJAX란

서버와 통신하며 웹페이지를 전부 갱신하지 않고 부분 부분 수정할 수 있도록 하는 기술입니다.

JS와 XML을 통해 다양한 데이터 형식의 파일을 서버와 주고 받을 수 있습니다.

<br>

### 2. 사용법

```html
<button id="ajaxButton" type="button">Make a request</button>

<script>
(function() {
  var httpRequest;
  document.getElementById("ajaxButton").addEventListener('click', makeRequest);

  function makeRequest() {
    httpRequest = new XMLHttpRequest();

    if(!httpRequest) {
      alert('XMLHTTP 인스턴스를 만들 수가 없습니다');
      return false;
    }
    httpRequest.onreadystatechange = alertContents;
    httpRequest.open('GET', 'test.html', 'true');
    httpRequest.send();
  }

  function alertContents() {
    if (httpRequest.readyState === XMLHttpRequest.DONE) {
      if (httpRequest.status === 200) {
        alert(httpRequest.responseText);
      } else {
        alert('request에 문제가 있습니다.');
      }
    }
  }
})();
</script>
```

* XMLHttpRequest()

  >각 종 관련 기능을 제공하는 인스턴스를 생성하는 방식입니다.

* onreadystatechange

  >상태가 변화하면 호출이 되는 함수를 지정할 수 있습니다.

* readyState

  >readyState의 값은 다음과 같은 용도로 사용됩니다.
  >
  >| Value | State              | Description                                                  |
  >| :---- | :----------------- | :----------------------------------------------------------- |
  >| `0`   | `UNSENT`           | Client has been created. `open()` not called yet.            |
  >| `1`   | `OPENED`           | `open()` has been called.                                    |
  >| `2`   | `HEADERS_RECEIVED` | `send()` has been called, and headers and status are available. |
  >| `3`   | `LOADING`          | Downloading; `responseText` holds partial data.              |
  >| `4`   | `DONE`             | The operation is complete.                                   |
  >
  >해당 상황에 알맞은 행동을 하도록 함수를 구성하여 대응할 수 있습니다.

* status

  >status는 http의 응답 상태를 체크할 수 있는 변수입니다.
  >
  >https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html에서 관련된 내용을 확인할 수 있습니다.

* open

  >총 3개의 인자를 받아 작동하는 함수입니다. 
  >
  >1번째 인자는 http요구방식을 설정하며, 2번째 인자는 URL을 설정합니다.
  >
  >3번째 인자는 생략할 수 있으며, true일 경우 비동기, false일 경우 동기적으로 작동하게 됩니다.

* send

  >위 함수를 통해 서버로 데이터를 보내는 것이 가능하며 다양한 포맷으로 보내는 것이 가능합니다.
  >
  >다양한 포맷으로 보낼 경우 setRequestHeader()을 아래와 같이 사용하여 send()를 호출하기 전에 형식을 지정해야합니다.
  >
  >```html
  >httpRequest.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
  >```
