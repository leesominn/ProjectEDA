# ProjectEDA : [Python]시각화 라이브러리 활용한 데이터 EDA 프로젝트
## 주제 : 부산시 다회용컵 수거함 사업 참여 지역 및 수거함 위치 제안

## 프로젝트 소개
최근 환경 문제로 일회용품 사용을 적극적으로 줄이는 정책이 시행되며 대안책으로 다회용 공유컵이 제시되고 있음. 지속적으로 순환시키기 위해서는 '회수율'이 높아야하기 때문에 수거함 위치가 중요함. 이번 프로젝트를 통해 최적의 위치 장소를 제안하고자 함<br>
[발표 자료](https://github.com/leesominn/ProjectEDA/blob/main/python%EC%9D%84%20%EC%9D%B4%EC%9A%A9%ED%95%9C%20%EB%B9%85%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B6%84%EC%84%9D%20%EB%AF%B8%EB%8B%88%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8(5%EC%A1%B0).pdf)

## 개발 기간
* 22.08.10일 - 22.08.17일

## 프로젝트 과정
1. 상권 데이터 분석
    - pandas, numpy 이용 > 부산시 구별로 상권 수 및 상권 분포 확인
    - folium 이용 > 상권 수를 기준으로 상권 밀집지역 도출

2. 카페 데이터 분석
    - pandas, matplotlib, seaborn 이용 > 부산시 구별로 카페 수 확인 
    - folium 이용 > 카페 분포 지역 확인 
    - DBSCAN 이용 > 카페 밀집지역 도출

3. 구 단위의 후보군 선정
    - 수거함 후보군 제안
       - 버스데이터 : 부산광역시 최다 이용 정류장 10곳의 총 이용인원 표출
       - 지하철데이터 : 2022년 7월까지 부산지하철역 상위 15곳의 총 이용객 표출
       - 공원데이터 : 부산광역시 내 공원위치 표출
       - 현대카드 연간매출 합계 데이터 : 부산시 구별로 구역을 나눈 후 위 후보군 전체 표출
    - 후보군 : 1순위)부산진구, 2순위)중구, 3순위)동래구

4. 1순위 후보군에서 최종 후보지 선정
    - pandas, matplotlib 이용 > 부산 진구 전체 CCTV 좌표를 초기 후보군으로 선정
    - 카페와 50m 이내 거리에 있는 후보군 제외
    - 평균 보행속도 기준으로 15분 이상의 거리에 있는 후보군 제외
    - 추출된 후보군과 부산진구 지하철 위치를 비교하여 최종 후보군 설정
    
    - 최종 수거함 후보지: 동의대역, 양정역, 부전역
