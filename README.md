![스크린샷 2025-03-19 210350](https://github.com/user-attachments/assets/d07b4930-acf1-456b-9cab-b62bb38d82ff)# 📺 애니메이션 평가 데이터를 활용한 평점 예측 및 추천 서비스

## 👤 팀 소개
#### SKN Family AI 캠프 11기  ML 미니 프로젝트 <br/>
#### 기간: 2025.03.12 - 2025.03.21 <br/><br/>

### 팀원
<table>
  <thead>
    <td align="center">
      <a href="https://github.com/KimHyeongJu">
        <img src="https://github.com/Kim-Hyeong-Ju.png" width="150" alt="Hyeong Ju"/><br /><hr/>
        김형주
      </a><br />
    </td>
    <td align="center">
      <a href="https://github.com/REROUN">
        <img src="https://github.com/REROUN.png" width="150" alt="Keun"/><br /><hr/>
        이 근
      </a><br />
    </td>
    <td align="center">
      <a href="https://github.com/minjung2266">
        <img src="https://github.com/minjung2266.png" width="150" alt="minjung"/><br /><hr/>
        이민정
      </a><br />
    </td>
    <td align="center">
      <a href="https://github.com/hyunahn23">
        <img src="https://github.com/hyunahn23.png" width="150" alt="jonghyun"/><br /><hr/>
        안종현
      </a><br />
    </td>
  </thead>
</table>

<br/><br/>
<hr>

## 2️⃣ 프로젝트 소개
![Your Name](https://github.com/user-attachments/assets/6921be0b-0fb6-4592-8dd4-f8eedf11f68a)


### 📖 프로젝트 목표
**1. 사용자의 취향을 반영 할 수 있는 서비스 제공**

- kmeans를 사용하여 애니메이션과 고객별 평점을 분류하고 추후 사용자가 접하지 못했던 새로운 애니메이션을 추천하도록 한다.
- 이를 통해 사용자는 특정 장르나 유명 작품에 편중되지 않고 다양한 애니메이션을 접할 수 있다.

**2. 객관적인 평점 예측을 위한 시스템 구축**

- 기존의 추천 시스템은 단순히 사용자의 과거 선호도가 반영되었다.
- 본 프로젝트는 애니메이션의 다양한 특징(예: 장르, 방영 연도, 제작사, 인기 지표 등)을 기반으로 더욱 정교한 추천시스템을 구축하고자 했다.
<br/>

### ⭐ 프로젝트 필요성
| **주제**                       | **내용**                                                                                   |
|---------------------------------|--------------------------------------------------------------------------------------------|
| **고객의 취향 발견**            | 이미 접한 애니메이션만 반복적으로 추천하는 시스템은 흥미롭지 않다. 애니메이션 고객 평점 기반으로 다양한 추천을 제공하는 시스템이 필요하다. 경험할 수 있는 애니메이션의 범위를 넓히고, 새로운 취향을 발견할 수 있다. |
| **시장 경쟁력 확보를 위한 추천 시스템** | 콘텐츠 과잉 시대에서 추천 시스템의 경쟁력은 매우 중요한 요소이다. 사용자의 취향을 분석하고 새로운 콘텐츠를 발견할 수 있는 서비스를 통해, 기존의 단순히 '인기 있는 콘텐츠'만 추천하는 시스템을 넘어 사용자 이용 경험을 개선할 수 있다. 서비스 제공자는 차별화된 경쟁력을 확보할 수 있다. |
<hr>

## 3️⃣ 기술 스택
#### [데이터 시각화]
<p>
  <img src="https://img.shields.io/badge/pandas-150458.svg?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/matplotlib-0077B5.svg?style=for-the-badge&logo=matplotlib&logoColor=white"> <br>
  <img src="https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white"> 
  <img src= "https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white">
  <img src= "https://img.shields.io/badge/surprise-%23013243.svg?style=for-the-badge&logo=surprise&logoColor=blue">
</p>

<hr>

## 🔎 데이터

### Anime Dataset
* 12994 rows

| anime_id  | name            | genre        | type    | episodes | rating | members |
|-----------|-----------------|--------------|---------|----------|--------|---------|
| Unique ID | 애니메이션 이름 | 애니메이션 장르 | 방영 유형 | 에피소드 수 | 평균 평점 (10점 만점) | 커뮤니티 멤버 수 |


### Rating Dataset
* 7813737 rows

| user_id  | anime_id | rating |
|----------|----------|--------|
| 무작위 생성된 사용자 ID | 사용자가 평가한 애니메이션 ID | 사용자 평가 (10점 만점, -1은 미평가) |


<hr>

## 🤓 분석 내용
1. 데이터의 속성별 의미<br>

2. 고객별 애니메이션 시청 경향

3. ...
4. 
<hr>

## 📚분석과정
<h3>데이터 탐색 후 Merge</h3>
#### 1. 데이터 로드 및 분포 확인
- 라이브러리 호출 및 데이터 로드

![라이브러리 호출 ](https://github.com/encore-SKN11/ML-8Team/blob/main/asset/%EB%9D%BC%EC%9D%B4%EB%B8%8C%EB%9F%AC%EB%A6%AC1.png)

![라이브러리 호출2](https://github.com/encore-SKN11/ML-8Team/blob/main/asset/%EB%9D%BC%EC%9D%B4%EB%B8%8C%EB%9F%AC%EB%A6%AC2.png)

![데이터로드](https://github.com/encore-SKN11/ML-8Team/blob/main/asset/data_load.png)

- Data Summary
![스크린샷 2025-03-19 205628](https://github.com/user-attachments/assets/ad3310d6-3fcc-479c-bd50-d85dd83948f2)
![스크린샷 2025-03-19 205642](https://github.com/user-attachments/assets/4aec8044-e9fd-4adc-afeb-9766082d93d5)

![스크린샷 2025-03-19 205802](https://github.com/user-attachments/assets/d22fcfd4-a3dd-499c-bc8a-a63035af5399)
![info](https://github.com/user-attachments/assets/5f1ffe67-af0a-486d-88ee-91bb7987d791)

![스크린샷 2025-03-19 205914](https://github.com/user-attachments/assets/59db429e-3daf-462c-8aa3-e0d228eea2bd)


#### 2. NaN 값 제거 및 결측값 제거
- Check Missing Value
![스크린샷 2025-03-19 205418](https://github.com/user-attachments/assets/ea545619-3850-4a64-a9eb-472cc40e74b5)

- Remove Missing Rows
![스크린샷 2025-03-19 205449](https://github.com/user-attachments/assets/1dff67de-b9e8-4a58-aa71-fb3f6ed39585)

- Check Duplicates
![스크린샷 2025-03-19 210253](https://github.com/user-attachments/assets/3d8a9b95-e339-43e7-9621-dbbded64ced4)

- Remove Duplicates
![스크린샷 2025-03-19 210350](https://github.com/user-attachments/assets/acdb686d-5b91-4ee9-8e9f-a1e48c18f8ed)

#### 3. 데이터 merge & rating -1값 제거 
![스크린샷 2025-03-19 210453](https://github.com/user-attachments/assets/9cb7d4b9-a10c-4063-9eb7-f21ef97cc2d4)
![스크린샷 2025-03-19 210555](https://github.com/user-attachments/assets/7d617a59-3530-46a7-941e-9bf6dd1ccf5c)
![스크린샷 2025-03-19 211040](https://github.com/user-attachments/assets/ffe670ed-6ad6-43ab-9d39-52692a1770be)
![스크린샷 2025-03-19 211116](https://github.com/user-attachments/assets/23ad0494-164d-4a78-859c-5e75063e4a1a)
<hr>

<h3>merge 데이터 전처리</h3>

#### 1. 전처리 함수 생성

![스크린샷 2025-03-19 211446](https://github.com/user-attachments/assets/1019d8d5-6bc9-4900-a155-ec95cd8e7f2f)
![image](https://github.com/user-attachments/assets/17e210df-726d-4fa8-9f2a-9e020b34c6fd)
![image](https://github.com/user-attachments/assets/b51bc43a-c491-4e95-8746-f862381b6dc7)

#### 2. 전처리 프로세스 시간복잡도 계산
![image](https://github.com/user-attachments/assets/8ec55253-e8da-4320-968f-367e928c4c83)

<hr>
<h3>인기 기반 애니메이션 추천</h3>

- user rating 순위
![image](https://github.com/user-attachments/assets/a9e78b95-bc1c-4add-a4ce-6768ce56348b)
![image](https://github.com/user-attachments/assets/4796b62c-707f-42fc-a42f-b2f75539cdbc)

![image](https://github.com/user-attachments/assets/5cb98be6-45d8-440f-ac75-293f7bcda3c4)
![image](https://github.com/user-attachments/assets/d3b9ea88-802b-4c49-bb89-680c2a8be6ee)

- anime rating 순위
![image](https://github.com/user-attachments/assets/6d61fcbb-2403-475e-ae6d-b8e7e9ab36f1)
![image](https://github.com/user-attachments/assets/fea261f5-9d76-4d18-b9ae-058123a33921)
![image](https://github.com/user-attachments/assets/6de0434b-d42e-4679-a951-6335ddf079bb)

- first genre 생성
![image](https://github.com/user-attachments/assets/9b90b24b-f4ba-4cfe-9742-e9a2f8a361f8)
![image](https://github.com/user-attachments/assets/8dbf4d16-e4c0-4bbc-b387-705e6ebd2f84)
![image](https://github.com/user-attachments/assets/fda6abab-0ead-4439-ab6c-dd792538f303)
![image](https://github.com/user-attachments/assets/fd9427b9-f1d3-4f9b-a3bb-4ac0c89ea936)

## ⭐ 한 줄 회고
🧑🏻 형주


🧑🏻‍🦱 근


👱🏻‍♀️ 민정


👨🏻‍🦰 종현
