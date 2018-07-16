---
layout: post
title: "2018.07.16"
description: 노드 서버 및 socket.io 정리
tags:
 - etc
---

## Node Server
>server.js
{:.filename}
{% highlight javascript %}
//필요한 express,http,socket.io 선언 및 초기화
var app = require('express')();
var http = require('http').Server(app);
var io = require('socket.io')(http);


//express get방식 호출 매핑, 경로는 /
app.get('/', function(req, res){
    res.sendFile(__dirname+"/chat.html");
});
// http는 listen 함수에 초기 세팅(포트 번호)을 해주어야 한다.
http.listen(3000, function(){
    console.log('listening on *:3000');

});
require("./chat")(io);
{% endhighlight javascript %}


>server.js
{:.filename}
{% highlight javascript %}
{% endhighlight javascript %}

## Web socket & Socket.io & Ajax 차이점
통신은 결국 사용자와의 상호작용을 위해 필요한 부분이다.
단순하게 생각하면 Web socket과 Ajax의 차이점은 단방향 통신과 양방향 통신의
차이라고 볼 수 있다. ajax는 호출하지 않으면 서버와 데이터를 주고 받을 수 없는
구조이다. 서버의 변경된 데이터를 확인하려면 주기적인 호출이 이루어져야 한다.

Socket.io는 브라우저의 종류와 버전을 파악 하여 소켓통신을 이어주는 방식으로
AJAX Long Polling 등이 있다. 표준이 아니며 Node.js에 종속적이라고 볼 수 있다.




[참고 https://d2.naver.com/helloworld/1336](https://d2.naver.com/helloworld/1336)
