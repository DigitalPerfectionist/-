캐릭터에 광을 추가하는 기능을 추가한 코드입니다. 사용자가 선택한 광을 캐릭터 이미지에 추가하여 표시합니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>로블록스 프로필 생성기</title>
</head>
<body>

<header>
    <h1>로블록스 프로필 생성기</h1>
</header>

<section id="profile">
    <h2>로블록스 닉네임 입력</h2>
    <input type="text" id="username" placeholder="로블록스 닉네임을 입력하세요">
    <button id="generateBtn">프로필 생성</button>
</section>

<section id="character">
    <h2>로블록스 캐릭터</h2>
    <div id="characterPreview"></div>
</section>

<section id="background">
    <h2>배경 설정</h2>
    <select id="backgroundSelect">
        <option value="city.jpg">도시</option>
        <option value="forest.jpg">숲</option>
        <option value="beach.jpg">해변</option>
    </select>
</section>

<section id="lighting">
    <h2>광 설정</h2>
    <select id="lightingSelect">
        <option value="none">광 없음</option>
        <option value="sunshine">햇빛</option>
        <option value="moonlight">달빛</option>
        <option value="spotlight">스포트라이트</option>
    </select>
</section>

<script>
    document.getElementById('generateBtn').addEventListener('click', function() {
        var username = document.getElementById('username').value;
        var characterUrl = 'https://www.roblox.com/Thumbs/Avatar.ashx?username=' + username;
        var lighting = document.getElementById('lightingSelect').value;
        var characterPreview = document.getElementById('characterPreview');
        characterPreview.innerHTML = '<img src="' + characterUrl + '" alt="로블록스 캐릭터">';
        
        if (lighting !== 'none') {
            var lightingImage = document.createElement('img');
            lightingImage.src = lighting + '.png';
            lightingImage.alt = lighting;
            characterPreview.appendChild(lightingImage);
        }
    });

    document.getElementById('backgroundSelect').addEventListener('change', function() {
        var selectedBackground = document.getElementById('backgroundSelect').value;
        document.body.style.backgroundImage = 'url(' + selectedBackground + ')';
    });
</script>

</body>
</html>
```

이 코드를 사용하면 로블록스 닉네임을 입력하고 "프로필 생성" 버튼을 클릭하면 해당 사용자의 캐릭터를 표시하고, 배경을 선택하여 설정할 수 있습니다. 또한 광을 선택하여 캐릭터에 추가할 수 있습니다.
