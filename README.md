# FRONTEND

## 📌 메인페이지
<img width="906" alt="main" src="https://user-images.githubusercontent.com/114130942/228764796-549cdc32-bb68-46b8-9951-d8558c289e8c.png">

#### 📍 Header
<img width="896" alt="header" src="https://user-images.githubusercontent.com/114130942/228764985-3fb8e75f-2177-438d-84a7-6b61b2d64bd4.png">

#### 📍 Header 알림
<img width="352" alt="noti" src="https://user-images.githubusercontent.com/114130942/228766386-98310bce-945f-4ac8-b5c7-86856285c734.png">

##### (header 세부메뉴 : 커서 올렸을 때만 display) HTML
    <div class="categoryMenu">
        <span>스터디원</span>
        <div class="dropTable">
            <a class="dropRecruitStudy dropMenu" href="/recruitstudy">스터디원 모집</a>
            <a class="dropRecruitMentor dropMenu" href="/recruitmentorlist">멘토 모집</a>
            <a class="dropMentorProfile dropMenu" href="/mentorprofilelist">멘토 프로필</a>
        </div>
    </div>
    
##### (header 세부메뉴 : 커서 올렸을 때만 display) CSS 
    .categoryMenu{
        width: auto;
        height: 40px;
        padding: 20px 10px;
        text-align: center;
        font-size: 19px;
        cursor : pointer;
        position : relative;
        display : inline-block;
        white-space: nowrap;
    }
    .categoryMenu:hover{
        color: #507e2d;
    }
    .categoryMenu a:hover{
        color: #507e2d;
    }
    .dropTable{
        margin: 14px 0px;
        cursor : pointer;
        position : absolute;
        z-index : 1;
        font-size: 15px;
        text-align: left;
        width: 150px;
        background-color: #f5f5f5;
        display: none;
    }
    .dropTable a{
        display : block;
        padding: 15px 10px;
    }
    .categoryMenu:hover .dropTable{
        display: block;
    }
    .dropTable a:hover{
        background-color : #ececec;
        font-weight: bold;
    }

##### (알림창 : 클릭을 했을 때, display) JS
    const icon = document.querySelector('.icon');
    const notiDrop = document.querySelector('.notiDrop');
    let status = 0; //0이면 클릭 안된 상태, 1이면 클릭 된 상태

    function open(e){
        if ( e == 1 ){
            notiDrop.style.display = "block";
        } else {
            notiDrop.style.display = "none";
        }
    }
    icon.addEventListener('click', function () {
        if( status == 0 ){
            status = 1;
            open(status);
        } else{
            status = 0;
            open(status);
        }
    });

#### 📍 광고 배너(이미지 슬라이드 Image Slide)
<img width="889" alt="imgslide" src="https://user-images.githubusercontent.com/114130942/228769308-4e1e37df-a67a-424f-9ca7-45e02d0bf0cf.png">

##### (이미지 슬라이드 Image Slide) HTML
    <div class="advertisingDiv">
        <ul class="slides">
            <li><img src="/img/ad1.png" alt="/img/ad11.png"></li>
            <li><img src="/img/ad2.png" alt="/img/ad22.png"></li>
        </ul>
        <p class="controller">
            <span class="prev"><</span>
            <span class="next">></span>
        </p>
    </div>
    
##### (이미지 슬라이드 Image Slide) JS
    const bestStudySlides = document.querySelector('.bestStudySlides'); //전체 슬라이드 컨테이너
    const studySlideImg = document.querySelectorAll('.bestStudySlides li'); //모든 슬라이드들
    let studyCurrentIdx = 0; //현재 슬라이드 index
    const studySlideCount = 2; // 슬라이드 개수
    const studyPrev = document.querySelector('.studyPrev'); //이전 버튼
    const studyNext = document.querySelector('.studyNext'); //다음 버튼
    const studySlideWidth = 1184; //한개의 슬라이드 넓이

    //전체 슬라이드 컨테이너 넓이 설정
    bestStudySlides.style.width = studySlideWidth * studySlideCount + 'px';

    function studyMoveSlide(num) {
        bestStudySlides.style.left = -num * 1184 + 'px';
        studyCurrentIdx = num;
    }

    studyPrev.addEventListener('click', function () {
        if (studyCurrentIdx !== 0) {
        studyMoveSlide(studyCurrentIdx - 1);
        }
        //첫번째 슬라이드가 아닐 때, 이전 버튼을 누르면 전 슬라이드로 이동
    });

    studyNext.addEventListener('click', function () {
        if (studyCurrentIdx !== studySlideCount - 1) {
            studyMoveSlide(studyCurrentIdx + 1);
        }
        //마지막 슬라이드가 아닐 때,  다음 버튼을 누르면 다음 슬라이드로 이동
    });

#### 📍 Best Study / Mentor
<img width="893" alt="beststudy" src="https://user-images.githubusercontent.com/114130942/228770330-a8dd46bf-bb31-4536-a7c3-425715d076fd.png">
##### 광고배너에 사용했던 이미지 슬라이드와 같은 방식

#### 📍 Footer
<img width="896" alt="footer" src="https://user-images.githubusercontent.com/114130942/228769079-5e16bc71-9a68-4fe9-99fa-f5771df4f6db.png">

## 📌 로그인 페이지
<img width="1277" alt="login" src="https://user-images.githubusercontent.com/114130942/228770682-efc0af76-9fc5-4e0f-bd62-5e0fc25fc2f1.png">

#### 📍 회원가입(기본 서버 / 구글 / 네이버) 폼 : 각 소셜별로 요구하는 정보만 다름
<img width="506" alt="join" src="https://user-images.githubusercontent.com/114130942/228771115-63e65f3b-821c-461e-be33-711fd5a780fc.png">

#### 📍ID 찾기 / PWD 찾기 (구성동일 아래 사진은 ID 찾)
<img width="512" alt="findIdd" src="https://user-images.githubusercontent.com/114130942/228771311-6aa69221-5a3b-4d43-99b9-c72044ea8d08.png">

#### 📍 아이디 찾기 결과
<img width="395" alt="findid" src="https://user-images.githubusercontent.com/114130942/220035658-e262c80d-248a-4434-97f8-0484a658e287.png">

## 📌 마이페이지 (기본 이동은 '내 프로필')
<img width="911" alt="profile" src="https://user-images.githubusercontent.com/114130942/228771752-066be7cf-e4f8-4dc4-b5fb-5e97b89c7c7e.png">

#### 📍 마이페이지 메뉴
<img width="136" alt="mypagemenu" src="https://user-images.githubusercontent.com/114130942/228772045-5a64fc4c-a43b-4108-add5-9ca7624b33a2.png">

##### 마이페이지 메뉴 HTML
    <div class="containerLeft">
        <h2 class="my">My Page</h2>
        <input type="button" class="memberInfo mypageBtn accordion" value="개인정보 관리">
        <div class="memberInfoList panel">
            <a class="profile content" href="/mypage">내 프로필</a>
            <a class="modifyMemberInfo content" href="/mypage/modifyform">개인정보 수정</a>
            <a class="modifyPwd content" href="/mypage/modifyform/editpwd">비밀번호 수정</a>
            <a class="withdraw content" href="/mypage/modifyform/withdrawalcheck">탈퇴하기</a>
        </div>
        <div class="menu">
            <input type="button" class="likeList mypageBtn" onclick="location.href='/mypage';" value="찜목록">
            <input type="button" class="studying mypageBtn" onclick="location.href='/mypage';" value="현재 Mate">
            <input type="button" class="chatList mypageBtn" onclick="location.href='/mypage';" value="채팅목록">
            <input type="button" class="purchaseList mypageBtn" onclick="location.href='/mypage';" value="구매내역">
        </div>
    </div>
    
##### 마이페이지 메뉴 JS
    var acc = document.getElementsByClassName("accordion");
    var i;

    for (i = 0; i < acc.length; i++) {
        acc[i].addEventListener("click", function () {
            this.classList.toggle("active");
            var panel = this.nextElementSibling;
            if (panel.style.maxHeight) {
                panel.style.maxHeight = null;
            } else {
                panel.style.maxHeight = panel.scrollHeight + "px";
            }
        });
    }

#### 📍 개인정보 수정
<img width="610" alt="mymodify" src="https://user-images.githubusercontent.com/114130942/228772074-0829fdb4-f648-4575-905f-d51f46cc6cb5.png">

#### 📍 비밀번호 변경
<img width="890" alt="modipwd" src="https://user-images.githubusercontent.com/114130942/228772145-bf47d8cf-4986-4741-b72d-4107d4d3710f.png">
