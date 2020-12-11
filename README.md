    # jquery_01_20201211
    제이쿼리_01


    <!-- 
    ~~~~~~~~~~~~~~~~~~~~~~~~	
    jquery_01.html
    ~~~~~~~~~~~~~~~~~~~~~~~~
    --------------------
    JQuery란?
    --------------------
      > 공개적으로 개발되고 무료로 제공되는 [사용자 정의 객체] 이름이다.
        > <참고> 누구나 버그 수정, 성능 향상 그리고 도움말 작성에 참여할 수 있다.
        > <참고> http://plugins.jquery.com/ 에 광범위한 라이브러리(~.js)가 있으며,
            꾸준히 업데이트 되고 있고 누구나 버그 수정, 성능향상,
            도움말 작성에 참여할 수 있다.
    --------------------
    JQuery 객체 기능
    --------------------
      > HTML 문서 내의 태그 및 출력 문자열을 삽입, 수정, 삭제를 할 수 있다.
      > 그 결과로 웹브라우저 UI에도 변화가 생긴다.
      > 웹브라우저에서 각종 [이벤트] 발생 시 실행할 코딩을 설정할 수 있다.
      > 웹 서버와 비동기 방식으로 통신할 수 있다.
      > CSS를 설정할 수 있다.
      > 애니메이션도 설정할 수 있다.
      > 기타 등등.

    --------------------
    JQuery 객체 장점
    --------------------
      > 대부분의 브라우저에서 동일한 결과를 생산한다.
        =cross browsing(크로스 브라우징이라고 한다.
          즉 브라우저에 따라 개발자가 다른 코딩을 할 필요가 없다.
      > html 코드와 javascript 코드를 분리할 수 있어 유지 보수가 편하다.
      > 디자이너, 퍼블리셔, 개발자 모두가 사용하기 편하고 ***강력한 기능을 가진 메소드를 제공한다.***
    --------------------
    JQuery 객체 수입 방법
    --------------------
      > jquery-x.x.x.min.js 다운 받고 HTML의 head 태그에 아래와 같이 수입하는 코드를 작성한다.
        (x는 임의의 버전 번호이다.
            <script src="jquery-1.11.0.min.js"></script>
      <주의> src="jquery-1.11.0.min.js" 경로는 호출하는 .html 파일과
          수입되는 jquery-1.11.0.mins.js가 같은 폴더에 있을 때 쓰는 경로이다.

    mmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmm
    *** JQuery 객체의 메위주를 얻는 방법 ***
    mmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmm
      > JQuery 객체의 메위주를 얻어내면 JQuery 객체의 메소드나 속성변수를 호출할 수 있다.
      --------------------------
      jQuery() 함수를 호출하면 JQuery 객체의 메위주를 얻을 수 있다.
      -------------------------- 
      <방법1> jQuery(선택자?) 

        =>	jQuery() 라는 함수를 호출하여 선택자(= 태그를 지칭하는 방법)가 가리키는 태그를 
          관리하는 JQuery 객체를 생성하고 JQuery 객체의 메위주를 리턴하기.
          선택자(selector)란 [HTML 문서] 내의 [태그를 가리키는 방법]을 말한다.
      -------------------------- 
      <방법2> $(선택자?)     <--(**제일 많이 쓰는 제이쿼리 메위주 얻는 방법이다**)

        => $() 라는 함수를 호출하여 선택자(= 태그를 지칭하는 방법)가 가리키는 태그를 
          관리하는 JQuery 객체를 생성하고 JQuery 객체의 메위주를 리턴하기.
          선택자(selector)란 [HTML 문서] 내의 [태그를 가리키는 방법]을 말한다.
      -------------------------- 
      <방법3> jQuery

        => jQuery 라는 변수에 JQuery 객체가 이미 저장되어 있다.
          (특정 태그를 가리키진 않는다.) 객체 메위주만 갖고 있다.
      -------------------------- 
      <방법4> $

        => $ 라는 변수에 JQuery 객체가 이미 저장되어 있다.
          (특정 태그를 가리키진 않는다.) 객체 메위주만 갖고 있다.

    mmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmm
    JQuery 객체의 메소드를 호출하는 방법
    mmmmmmmmmmmmmmmmmmmmmmmmmmmmmmmm
      --------------------------
      <방법1> jQuery(선택자).메소드(~)
      --------------------------
      <방법2> $(선택자).메소드(~)
      --------------------------
      <방법3> jQuery.메소드(~)
      --------------------------
      <방법4> $.메소드(~)
      --------------------------

     -->
     <!DOCTYPE html>
     <html>

     <head>
      <meta charset="utf-8">
      <script type="text/javascript" src="jquery-1.11.0.min.js"></script>
      <!--   ../  이뜻은 지금 폴더를 벗어나서 라는 뜻.-->
      <script type="text/javascript" src="common_js.js"></script>

      <script type="text/javascript">


        //*********************************
        //	$(document).ready( function(){ 자스코딩 } );
        //*********************************
          // body 태그 안의 요소들을 읽어들인 후 익명함수 내부의 자스코딩을 실행.
        $(document).ready(function(){
    //--------------------------------------------------------------------------------------

          //--------------------------------------
          // class=save_member 를 가진 태그를 [클릭]하면
          // checkForm 이란 함수호출 하도록 설정하기
          //--------------------------------------
    //-------------------------------------------------------------------------------------- 			
          $(".save_member").click(function(){


            checkForm();
          });
    //--------------------------------------------------------------------------------------

    //--------------------------------------------------------------------------------------
          var obj = $(".birth_year");
    //--------------------------------------------------------------------------------------
          for(var i = 2000; i <= new Date().getFullYear(); i++){	
            obj.append("<option value="+i+">"+i+"</option>");
          }

    //--------------------------------------------------------------------------------------
          var obj = $(".birth_month");
    //--------------------------------------------------------------------------------------
          for(var i = 1; i <= 12; i++){
            if(i<10){	
              obj.append("<option value=0"+i+">0"+i+"</option>");
            }else{
              obj.append("<option value="+i+">"+i+"</option>");
            }
          }

    //--------------------------------------------------------------------------------------
          var obj = $(".birth_date");
    //--------------------------------------------------------------------------------------			
          for(var i = 1; i <= 31; i++){	
            if(i<10){	
              obj.append("<option value=0"+i+">0"+i+"</option>");
            }else{
              obj.append("<option value="+i+">"+i+"</option>");
            }
          }

    //--------------------------------------------------------------------------------------

        });




        function checkForm(){

          //++++++++++++++++++++++++++++++++
          // [아이디 유효성 체크]하기
          //++++++++++++++++++++++++++++++++
          //--------------------------------
          // 사용자가 웹브라우저 화면에서 입력한 [아이디값]을 가져와 uid 변수에 저장
          //--------------------------------

          // var uid = $(".uid").val();
          var uid = $("[name='uid']").val();

          //--------------------------------
          // checkID 함수 호출로 아이디의 유효성 여부가 false 면 커서를 넣어주고 함수 중단하기.
          //--------------------------------
          if(checkID(uid)==false){

            $(".uid").val("");	
            $(".uid").focus();
            return;
          }

          //++++++++++++++++++++++++++++++++
          // [암호 유효성 체크]하기
          //++++++++++++++++++++++++++++++++

          // var pwd = $(".pwd").val();
          var pwd = $("[name='pwd']").val();


          if(checkPwd(pwd)==false){

            $(".pwd").val("");	
            $(".pwd").focus();
            return;

          }
          //++++++++++++++++++++++++++++++++
          // [skill 유효성 체크]하기
          //++++++++++++++++++++++++++++++++
          var skill_cnt = $(".skill:checked").length;

          alert(skill_cnt)

          if(skill_cnt==0){
            alert("스킬은 1개이상 선택 요망!");
            return;
          }


        }

      </script>

     </head>
     <body>
      <form name="memberRegForm">
        <table border="1" cellpadding="7" cellspacing="0">
          <tr>
            <th>아이디
            <td><input type="text" name="uid" class="uid" size=20>
          </tr>

          <tr>
            <th>암호
            <td><input type="password" name="pwd" class="pwd" size=20>
          </tr>

          <tr>
            <th>암호확인
            <td><input type="password" name="pwd_confirm" class="pwd_confirm" size=20>
          </tr>

          <tr>
            <th>소유스킬
            <td><input type="checkbox" name="skill" class="skill" value="Java">Java
              <input type="checkbox" name="skill" class="skill" value="JSP">JSP
              <input type="checkbox" name="skill" class="skill" value="Spring">Spring
              <input type="checkbox" name="skill" class="skill" value="Oracle">Oracle
              <input type="checkbox" name="skill" class="skill" value="mybatis">mybatis
          </tr>

          <tr>
            <th>최종학력
            <td><input type="radio" name="school" class="school" value="고졸">고졸
              <input type="radio" name="school" class="school" value="전문대졸">전문대졸
              <input type="radio" name="school" class="school" value="일반대졸">일반대졸
          </tr>

          <tr>
            <th>거주지역
            <td><select name="addr" class="addr">
                <option value="">--선택--
                <option value="서울">서울
                <option value="경기">경기
                <option value="인천">인천
                <option value="전라도">전라도
                <option value="경상도">경상도
                <option value="부산">부산
                <option value="충청도">충청도
                <option value="제주도">제주도
                <option value="기타">기타
              </select>
          </tr>

          <tr>
            <th>생일
            <td><select name="birth_year" class="birth_year">
                <option value="">

              </select>년

              <select name="birth_month" class="birth_month">
                <option value="">

              </select>월

              <select name="birth_date" class="birth_date">
                <option value="">

              </select>일
          </tr>

          <tr>
            <th>주민번호(7자리)
            <td>
              <input type="text" name="jumin_num" class="jumin_num" maxlength="7">

          </tr>

          <tr>
            <th>사진
            <td>
              <input type="file" name="pic" class="pic">

          </tr>

          <tr>
            <th>숙지사항
            <td>입력하신 개인 정보는 회사 소유 입니다.
              <input type="checkbox" name="is_confirm" class="is_confirm" value="확인">확인

          </tr>
        </table>
        <input type="button" value="저장" class="save_member">
        <input type="button" value="초기화">
      </form>


     </body>
     </html>

     <script>
      // $("div").append("박인선")
      // $("div").append("씨가 햄버거쏜대여~~!");
      for(var i = 0; i<100; i++){
        $("div").append("아이디" +(i+1)+": <input type=text name=uid><br><br>");
      }
    </script> 	

    <!--  
    ----------------------------------------------------  

    *** 선택자를 외우고 제이쿼리 객체의 메소드를 잘 활용하면 된다. ***

    ----------------------------------------------------  
      ----------------------------------------------------  
      <예> $("div").empty();  -> 태그 내부를 비워라.(안보이게 감추는 것)
        => 달라 함수를 호출해서(제이쿼리객체의 메위가 들어감) 제이쿼리 객체의 메위주를 리턴. 
      ----------------------------------------------------  
      <예> $("div").remove(); -> 태그 전체를 지워라.(제거되는 것)
      ----------------------------------------------------  
      <예> $("div span").empty();
      ----------------------------------------------------  
      <예> $( "body ").append("<div>인선</div>"); 태그 추가.(막내아들입양) 
        => 바디태그 내부의 맨 밑에다가 div가끌어안고있는 인선을 추가하라는 뜻
      ----------------------------------------------------  
      <예> $( "body ").prepend("<div>보민</div>"); 태그 추가. (첫째아들입양)
        => 내부 맨 앞 첫줄에다가 div가 끌어안고있는 보민을 추가하라는 뜻
      ----------------------------------------------------  
      <예> $( ".xxx" ).prepend("<div>보민</div>");
        => .xxx라는 클래스가 있다면 첫째아들로 내부태그 맨 앞줄에다가 <div>보민</div>을 추가하라.
      ----------------------------------------------------  
      <예> $(".xxx,.vvv").empty();
        => 클래스=xxx 를 가진 놈과 vvv를 가진 놈 그 두놈의 후손을 다 제거하라는 뜻.
      ----------------------------------------------------   
      <예> var str = $(".xxx").html();
        => 그 선택자가 가리키는 태부내부에 있는 태구 전부(html 코딩)을 문자로 담으란 얘기
      ---------------------------------------------------- 
      <예> var str = $(".xxx").text();
        가 가리키는 내부에 있는 모든코딩들이 실행 됐을 때 화면으로 나가는 문자열만 문자로 리턴
      ---------------------------------------------------- 

    -->
