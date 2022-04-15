# team-assignment-list
원티드 프리온보딩 FE 코스 8개 기업 팀 과제에서 달성한 역할과 성과

## 코스 소개
### 일정
- 2022.2.21 ~ 3.25(5주)
### 내용
- 웹 프론트엔드 심화(React, CSS), 서버 통신 심화(네트워크) 학습
- 팀 과제(8개 기업), 개인 과제(1개 기업)
### 안내
- [https://www.wanted.co.kr/events/pre_onboarding_course_8](https://www.wanted.co.kr/events/pre_onboarding_course_8)

## 과제 소개
## 1. 카트 라이더 랭킹 페이지
### 작업 성과
- Progress circle chart (파일위치: /src/components/atoms/ProgressCircle.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-2/blob/dev/src/components/atoms/ProgressCircle.js))
    - 컴포넌트 재사용성 고려하여 기능 구현<br>
    
      ```jsx
       ProgressCircle 컴포넌트는 부모 컴포넌트로 부터 2개의 파라미터를 인자로 받는다. 
       인자 1 color: 도너 차트 외곽선 색깔
       인자 2 percent: 도너 차트 
      ```
      ```jsx
       <ProgressCircle color="#07f" percent={RankingData[1].win} />
      ```
      <br>
      <img src="https://user-images.githubusercontent.com/87353284/158306214-c1dca079-44da-405b-bb0c-f11fe8c11876.gif" width=90%">
 <br>

- Top Ranker 영역 마크업과 스타일링 (파일위치: src/components/molecules/TopRank.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-2/blob/dev/src/components/molecules/TopRank.js))
    - DB에서 수신한 Ranker 정보와 연동하여 Top Ranker 데이터 랜더링<br>
      ```jsx
          topRank.map((obj) => {
            RankingData = [
              ...RankingData,
              {
                nickName: obj.nickName,
                character: `{API생략}/${obj.character}.png`,
                point: obj.points
                  .toString()
                  .replace(/\B(?<!\.\d*)(?=(\d{3})+(?!\d))/g, ','),
                win: obj.win,
                retire: obj.Retired,
              },
            ];
          });
      ```
      <img src="https://user-images.githubusercontent.com/87353284/158315125-db4cf4bb-7de1-48fe-ab7d-26d680d2be09.png" width="80%">

### 개선 필요사항
- topRank에 map함수로 적용하면 배열 전체를 순회하는 부분하기 때문에 1 ~ 3위까지만 배열을 자르고 그 데이터 map으로 순회하게 하여 리소스 효율화
### 배포 링크
[https://wanted-pre-onboarding-09.github.io/wanted-codestates-project-9-2](https://wanted-pre-onboarding-09.github.io/wanted-codestates-project-9-2)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-2](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-2)

## 2. 쇼피몰 리뷰 등록과 확인 페이지
### 작업 성과
- 상세 페이지 마크업과 스타일링 작업 (폴더위치: src/components/organisms/detail [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/tree/dev/src/components/organisms/detail))
  
  <img src="https://user-images.githubusercontent.com/87353284/157573743-18202d52-a16e-4dd1-a7b7-246f422454d8.png" width="20%"/>

- 상세 페이지 마우스 드래그에 따른 이미지 슬라이드 기능(feat. 슬라이딩 dot 연동) 
  - 이미지 슬라이드 기능 (파일위치: src/components/organisms/detail/DetailImg.js [코드보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/blob/dev/src/components/organisms/detail/DetailImg.js))
  - 슬라이딩 닷 기능 (파일위치: src/components/atmoms/SlideDots.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/blob/dev/src/components/atmoms/SlideDots.js))

  <img src="https://user-images.githubusercontent.com/87353284/157575419-ae705da4-8c79-48fc-8aaa-81f7b20da634.gif" width="20%"/>

- 좋아요 버튼 구현(feat. Redux 전역저장소와 연동, click에 따른 좋아요 count Number 갱신) (파일위치: src/components/atmoms/Likes.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/blob/dev/src/components/atmoms/Likes.js))

  <img src="https://user-images.githubusercontent.com/87353284/157575735-c6ba4893-edaa-4b38-baa4-0c9a3e41f1df.gif" width="20%"/>

- 공유링크 모달 구현 (파일위치: src/components/atmoms/ShareItems.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/blob/dev/src/components/atmoms/ShareItems.js))

  <img src="https://user-images.githubusercontent.com/87353284/157576370-3819910b-46c3-41dd-b87e-ad6311eb1376.gif" width="20%"/>

### 개선 필요사항
- 상세 페이지 이미지 슬라이드 기능 고도화(마우스 드래그에 따른 이미지 이동)
### 배포 링크
[https://balaan9.netlify.app](https://balaan9.netlify.app)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9)
    
## 3. 해시업 폼 구현하기
### 작업 성과
- (폴더위치: src/components/atoms/ [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-7-1/tree/dev/src/components/atoms))
- 폼 생성하기 페이지 마크업과 스타일링
  - 필수 옵션이 모두 채워지면 우측 하단 '폼 저장' 버튼이 활성화
    
  <img src="https://user-images.githubusercontent.com/87353284/158739152-0f2e500a-4a24-40e5-9821-8624185059ec.png" width="30%" />

- 필드 추가와 삭제
   - 리덕스 툴킷을 활용하여 전체 필드 리스트를 갱신
   - 개별 컴포넌트별로 옵션 관련 정보 전역에서 별도 관리(Redux-Toolkit)
    
    <img src="https://user-images.githubusercontent.com/87353284/158739879-e9f2fe91-ec10-4803-ad78-bbbe139eb4c9.gif" width="30%" />

- Drag & Drop
   - Drag&Drop API를 이용
    
    <img src="https://user-images.githubusercontent.com/87353284/158740442-dd388761-eec2-46ed-9ff8-5f11579feec5.gif" width="30%" />

- 폼 저장
   - 저장 후 전체 정보 초기화
    
    <img src="https://user-images.githubusercontent.com/87353284/158740545-53d43689-814f-491a-a7f0-d08e73850d2c.gif" width="30%" />

### 개선 필요사항
- 해시업 폼 UX 제고 위한 CSS 스타일링
- Drag & Drop에서 Drop 전 Drag만 해도 각 필드의 위치가 바뀌게 하는 기능 고도화
### 배포 링크
[https://datable-9.netlify.app](https://datable-9.netlify.app)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-7-1](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-7-1)
