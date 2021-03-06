HTML
============
1.doctype이 무엇을 하는 것인가요?

  마크업언어(DTD, document Type Definition)에서 웹표준 문서의 버전을 지정합니다. 웹 브라우저에게 어떤 버전의 문서로 해석하면 되는지를 알려주며, 최상단에 위치해야합니다.
  HTML,XHTML,HTML5 3가지 형식이 존재합니다. 만약에 생략을 하는 경우에는 [쿼크모드(Quirks Mode)]로 렌더링이 됩니다. 
  필수사항은 아니지만 하위 브라우저와 호환을위해, 선언하는것을 추천하고 있습니다.
  
  * XHTML
      - Transitional
      ```
       <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
      ``` 
       기존에 문서들과 호환성을 위해서 사용됨. iframe과 target="_blank"를 사용할 수 있다.
      - Strict
      ```
      <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1-strict.dtd">
      ```
      말 그대로 엄격한 규격이며, center,u,font,iframe,새창띄우기등이 제한된다.
      - frameset
      ```
      <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" "http://www.w3.org/TR/xhtml1-frameset.dtd">
      ```
      지금은 거의 사용하지않는다.
  
  * HTML5
      ```
      <!DOCTYPE html>
      ```
   SGMLd을 기반으로하지않기 때문에, DTD참조가 필요 없다
  * HTML
    - 최근에는 작성되는 경우가 없다.
      + strict
      ```
      <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
      ```
      + transitional
      ```
      <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
      ```
      + frameset
      ```
      <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">
      ```
참고 링크1: [WEBDIR](https://webdir.tistory.com/40)

참고 링크2: [C.M.A API](http://chongmoa.com/html/441)
</hr>
2. 표준모드(standards mode)와 쿽크모드(quirks mode)의 다른 점은 무엇인가요?

   위에 2가지 모드는 HTML 문서에 맨 위에 선언된 DOCTYPE 에 따라 렌더링 모드를 선택하게 되는데, 이 과정을 Doctype Sniffing 또는 Doctype Switching 이라고 한다.

   * 표준모드(standards mode)로 랜더링이 되어있는 경우
   
      1.DOCTYPE이 선언되어있을때
   
      2.브라우저가 선언된 DOCTYPE에 따라 최신(W3C 표준)에 문서가 맞다고 판단 될때
   
      3.DTD에  FPI(formal public identifier) 와 FSI(formal system identifier) 가 DOCTYPE 에 동시에 기술되어 있을 경우
   
      ```
      <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">

      ```
   
   * 쿼크모드(quirks mode)로랜더링이 되어있는 경우
   
      1.DOCTYPE이 선언되어있지 않을 때
   
      2.브라우저가 선언된 DOCTYPE에 따라 예전문서라고 판단 될때,
   
      3.DTD에 FPI(formal public identifier) 만 기술되어 있을 경우
      ```
      <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">
      ```
      즉, 이전 세대의 브라우저에 맞는 비표준의 CSS를 적용합니다. 쿼크모드의 목적은 오래된 페이지들이 최신 브라우저에서 깨지지 않게 하기위함이 목적입니다.
 
 참고 링크1 : [C.M.A API](http://chongmoa.com/html/441)
 
 참고 링크2 : [A to Z](https://a-tothe-z.tistory.com/4)
 </hr>
 
 3.HTML과 XHTML의 다른 점은 무엇인가요
   
   * HTML(HyperText Mark-up Language)
   
     웹(WWW, World Wide Web)을 통해, 문서를 볼때, 사용되는 언어.
     
   * XHTML(Extensible HyperText Mark-up Language)
   
    HTML을 XML 바탕으로  새롭게 구성 단어 그대로 HTML규격의 문제점을 극복한 문서규격입니다. xML 문법을 따르므로, HTML과 문법규칙이 조금씩 다릅니다.
    HTML보다 엄격합니다.

   * 차이점
   
      1.CSS를 이해하는 방식이 다릅니다.
      
        + CSS 선택자의 대소문자를 가립니다.
        
        + HTML에서는 background-color, background-image, overflow 속성이 최상위 요소(HTML)에도 적용되지만 XHTML에서는 적용되지 않는다.
        
        + HTML에서는 tbody 태그를 마크업하지 않아도 CSS스타일이 적용되지만, XHTML은 적용되지 않는다.
        
        ```
        tbody th { text-align: left }
        ```
        
      2.클라이언트의 스크립트(Javascript)를 다루는 방식이 다릅니다.
      
        + document.write() 메소드가 적용되지 않습니다.
        
        + 표준이 아닌 .innerHTML 속성을 사용할 수 없습니다.
        
      3.태그 입력
      
        + HTML은 태그가 닫히지 않아도 허용이 되지만, XHTML은 무조건 종료 태그가 있어야합니다.
        
        ```
          <!-- HTML -->
          <p>blah blah blah

          <!-- XHTML -->
          <p>blah blah blah</p>  
        ```
        
        + 빈 요소 태그인 img, br, link, hr, input 태그는 XHTML에서는 무조건 '/>'로 닫아야합니다.
        
          ```
          <!-- HTML -->
          <img src="test.png">

          <!-- XHTML -->
          <img src="test.png" />
          ```
        
        + HTML은 태그명과 속성에 대소문자 둘다 사용가능, XHTML은 불가능.
        
        + HTML은 속성값 생략 가능, XHTML은 불가능.
        
        ```
          <!-- HTML -->
          <input type="text" readonly>

          <!-- XHTML -->
          <input type="text" readonly="readonly" />
          ```
      
      
참고 링크1 : [HTML 기초(markup, 브라우저 종류/XHTML,XML,HTML5 DHTML차이)](https://aboooks.tistory.com/38)

참고 링크2 : [wystan's tales](http://blog.wystan.net/2007/05/24/xhtml-vs-html)

참고 링크3 : [개발자의 길](https://jang8584.tistory.com/249)

 4.XHTML을 이용한 페이지의 한계점은 무엇이 있나요?
 
 5.application/xhtml+xml으로 지정한 페이지에 어떠한 문제가 있나요?
 
 6.다국어가 포함된 페이지는 어떤 방식으로 제공하나요?
 
 7.다국어 페이지를 제공하는 여러 방법에 관해 설명해주세요.
 
 8.data-속성은 무엇을 하는 것인가요? 사용했을 때 이점은 무엇인가요?

  * HTML5에 도입이 되어 input hidden 태그에 데이터를 넣는 방법외에 데이터를 넣고 싶을때 사용하는 방법입니다. 
  
  * 태그 어느 곳에서 data-속성을 통해 input hidden 태그를 쓰지 않고도 해당하는 데이터를 저장할 수 있는 이점이 있습니다.
  
  * script에서 불러올때는 속성명이 CamelCase로 변경되어 조회됩니다. 태그안에 저장되는 데이터이기 때문에, 민감한 데이터는 넣지 않는것이 좋습니다.
  
  ```
  <ul>
    <li data-age="30" data-eng-name="HONG GIL DONG">홍길동</li>
  </ul>
  
  /*접근 방법*/
  document.getElementById('uls').getElementsByTagName('li')[0].dataset //결과 "{"age":"30","engName":"HONG GIL DONG"}"
  //데이터 INSERT
  document.getElementById('uls').getElementsByTagName('li')[0].dataset.hasPet=true;//camelCase로 INSERT한다.
  결과
  <!-- <li data-age="30" data-eng-name="HONG GIL DONG" data-has-pet="true">홍길동</li> -->
  ```

 9.HTML5를 오픈 웹 플랫폼(open web platform)으로 생각해본다면, 어떤 것들로 구성돼 있을까요?

 10.쿠키(Cookies)와 세션저장소(sessionStorage)와 로컬저장소(localStorage)의 차이점을 설명해주세요.
 
   * 쿠키
     + HTML5 STORAGE가 나오기 이전에 브라우저에서 사용했던 저장소 역할을 했습니다. 
     
     + 유효기간이 있으며. Key-value방식으로 데이터가 저장됩니다. 4KB의 용량제한이 있습니다. 
     
     + 쿠키를 통해 특정 데이터를 저장해두었다가 서버요청이 올때, 쿠키는 서버를 통해 전송이 됩니다.
     
     + 서버요청을 할때마다 쿠키를 전송하기때문에 성능이 떨어질수있는 요인이 있기때문에, 웹스토리지 API(SESSION, LOCAL STORAGE)를 권장합니다.
     
     + 일반적으로는 세션 쿠키가 생성되며, 브라우져가 종료되면 소멸이 됩니다. Expires나 Max-Age를 명시하면 닫히더라도 기간동안 유지되는 쿠키가 생성됩니다.
     ```
     <!-- 쿠키 설정-->
     Set-Cookie : name : LEE; Expires=Thu, 16 Jul 2020 07:28:00 GMT;
     
     /*script 상에서 Cookie 접근*/
     document.cookie //"name : LEE"
     ```
    
   * 로컬저장소(localStorage)
   
     + window 객체 안에 있으며, window.localStorage(localStorage)로 접근이 가능합니다.
     
     + cookie와 똑같이 key-value 방식으로 저장이 됩니다.
     
     + 표준 스팩은 최대 5MB까지 저장할수 있습니다만, 도메인별 용량 제한이 있습니다.
     
     ```
     /* storage data set */
     localStorage.setItem('name','LEE');
     localStorage.setItem('human',{name : 'JOHN',age: 30, hasPet : true});
     
     //object add
     localStorage.setItem('humanObj',JSON.stringfy({name : 'JOHN',age: 30, hasPet : true}));
     
     /*storage get data*/
      localStorage.getItem('name');//결과 LEE
      localStorage.getItem('human')//"[object Object]"
      
      //object get
      JSON.parse(localStorage.getItem('humanObj'))//{name: "JOHN", age: 30, hasPet: true}
      
     /*storage item remove*/
     localStorage.removeItem('name');
     
     /*storage item clear*/
     localStorage.clear()
     ```
     
   * 세션저장소(sessionStorage)  
     
     + window 객체 안에 있으며, window.sessionStorage(sessionStorage)로 접근이 가능합니다.
     
     + 로컬 저장소와 동일한 메소드를 가지고 있으며, 데이터가 영구적으로 보관되어있는점을 제외하고는 똑같은 기능입니다.
     
  참고 링크1 : [ZeroCho Blog](https://www.zerocho.com/category/HTML&DOM/post/5918515b1ed39f00182d3048)
  
  참고 링크2 : [MDN HTTP 쿠키](https://developer.mozilla.org/ko/docs/Web/HTTP/Cookies)
  
  참고 링크3 : [박종명의 아름다운 개발 since 2010.06](https://m.mkexdev.net/111)
  
 11. <script>, <script async>와 <script defer>의 차이점에 관해 설명해주세요.
   
   * HTML는 실행을 위에서 아래로 내려가면서 실행합니다.(<html>태그 시작부터 닫히는 시점(/html)순서로 파싱이 됨.) 
  script를 body 태그 종료전에 넣었다면, 파싱이 끝났기때문에, async/defer를 넣어도 의미가 없습니다.
  
   * async
      + 스크립트 파일이 비동기적으로 실행될 수 있음을 나타내기 위해 사용됩니다. 즉 페이지를 파싱되는 중간에도 실행된다는 의미입니다. 
      다른 파일과 종속되어있지 않고, 실행순서가 랜더링에 영향이 없을때 사용하는것이 유용합니다.
      
   * defer
      + 브라우저가 페이지 파싱이 완료된다음에 실행이 됩니다. DOM의 제어에 영향이 있다면, 파싱이 완료된 후에 정상적인 작업을 수행해야 하기때문에 이속성을 사용합니다.
      
   * script
      + 브라우저가 페이지를 파싱하기 전에 스크립트를 가져와 바로 실행시킵니다. 즉, script의 인라인 내용은 즉시 해석되고 실행되고, 외부에서 가져오는경우는 가져올때까지 HTML 구문해석이 되지 않습니다.
      
  참고 링크1 : [이 세상에 하나는 남기고 가자](https://blog.asamaru.net/2017/05/04/script-async-defer/)
  
  참고 링크2 : [코딩의 시작 Tcp School](http://tcpschool.com/html-tag-attrs/script-async)
  
  참고 링크3 : [기본기를 쌓는 정아마추어 코딩블로그](https://jeong-pro.tistory.com/90)
  
   12. CSS<link>를 <head></head>사이에 쓰는 것과 JS<script>를 '/body'뒤에 사용하는 것은 좋은 사용법일까요? 어디에 배치하는 게 좋을까요?
  
  * CSS<link>를 <head></head>사이에 쓰는 것
  
   + css의 경우는 HTML과 CSS를 동시에 랜더링 하는데 필요한 정보를 담고 있으므로 해당 내용을 출력하기 전에 해석되는 것이 당연히 유리다고 생각합니다.
   
  * JS<script>를 <body></body>뒤에 사용하는 것
  
  기본적으로 HTML은 순차적으로 위에서 아래로 실행이 되는데, DOM 중간에 인라인 스크립트, 외부 스크립트가 있으면, PARSING을 멈추고 실행을 되기 때문에 페이지가 다운되는것처럼 보일수도있기때문에, 모든 DOM 랜더링을 완료한 후에 JS코드를 아래에 두는것이 좋습니다. 만약에 head 태그사이에 두어야한다면 defer속성을 사용하는것이 좋습니다.

 참고 링크1 : [이 세상에 하나는 남기고 가자](https://blog.asamaru.net/2017/05/04/script-async-defer/)
 
 참고 링크2 : [Sungmin Chris Yang](https://velog.io/@chris/front-end-interview-handbook-html#doctype%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%84-%ED%95%98%EB%82%98%EC%9A%94)
  
  13.Progressive rendering이란 무엇인가요?

   * 콘텐츠를 최대한 빠르게 뿌리기 위해 웹 페이지 향상을 위해 사용하는 기법입니다. 
   
     + 이미지 레이지로딩(LazyLoading)
        - 이미지를 한번에 로딩하지 않고, 스크롤할때마다 이미지를 로딩하는 기법입니다.
        
     + 보이는 콘텐츠의 우선순위 설정 (또는 스크롤 없이 볼 수 있는 렌더링)
        - 맨처음 실행될때 스크롤없이 볼수있는 최소한의 HTML,CSS,JS 파일을 먼저랜더링. 이후 Defer속성을 이용하여, DOMContentLoaded/load 이벤트를 사용하여 다른 리소스와 내용을 로드할 수 있습니다. 
     
     + 비동기 HTML 프래그먼트
        - 페이지의 백엔드에서 HTML의 일부를 브라우저로 가져온다.

   14.이미지 태그에 srcset 속성을 사용하는 이유는 무엇인가요? 브라우저가 이 속성을 가진 콘텐츠를 평가할 때 사용하는 과정을 설명해보세요.
   
   * srcset 속성
     + src속성과 다르게 브라우저에 사용될 이미지와 이미지의 크기들을 지정합니다. 단 이미지 크기는 px 단위가 아닌, w(Width 너비 디스크립터),x(이미지 크기 비율)디스크립터로 작성을 하는 것이 특징입니다.
     
     ```
     <!-- srcset 예시-->
     <img
      srcset="SAMPLE_400.jpg 400w,
              SAMPLE_600.jpg 600w,
              SAMPLE_900.jpg 900w"
      src="SAMPLE.jpg"
      alt="SAMPLE" class="sample_img" 
      width="400" <!-- 이미지가 400으로 고정 이때는 srcset 속성이 통하지 않음. -->
      />
      
      <!-- 
      결과 뷰포트의 너비가 400px 이하일떄 sample_400.jpg 이미지가 사용됩니다.
      결과 뷰포트의 너비가 401px~600px 일떄 sample_600.jpg 이미지가 사용됩니다.
      결과 뷰포트의 너비가 601px 이상일떄 sample_900.jpg 이미지가 사용됩니다.
      -->
     ```
     
     + CSS의 미디어조건과 비슷하다고 생각하면 될꺼같습니다.
     
     ```
      /*srcset을 media조건으로 표현*/
     .sample_img {
      width: 400px;
      height: 400px;
      background-image: url("SAMPLE_400.jpg");   
      background-repeat: no-repeat;
      }
      @media (min-width: 401px) {
       .sample_img {
          width: 600px;
          height: 600px;
          background-image: url("SAMPLE_600.jpg");   
        }
      }
      @media (min-width: 701px) {
        .sample_img {
          width: 900px;
          height: 900px;
          background-image: url("SAMPLE_900.jpg");   
        }
      }
      
    ```
     
  참고 링크 1: [HEROPY TECH](https://heropy.blog/2019/06/16/html-img-srcset-and-sizes/)

-----

문제 참고 : [프론트엔드 면접 문제 은행](https://h5bp.org/Front-end-Developer-Interview-Questions/translations/korean/)

