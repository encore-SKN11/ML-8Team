# 📺 애니메이션 평가 데이터를 활용한 평점 예측 및 추천 서비스

## 👤 팀 소개
#### SKN Family AI 캠프 11기 ML 미니 프로젝트 <br/>
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

- 다양한 추천 모델(kmeans, knn, 협업 필터링, 콘텐츠 기반 필터링, SVD, Hybrid) 를 사용하여 애니메이션과 고객별 평점을 분류하고 추후 사용자가 접하지 못했던 새로운 애니메이션을 추천하도록 한다.
- 이를 통해 사용자는 특정 장르나 유명 작품에 편중되지 않고 다양한 애니메이션을 접할 수 있다.

**2. 객관적인 평점 예측을 위한 시스템 구축**

- 기존의 추천 시스템은 단순히 사용자의 과거 선호도가 반영되었다.
- 본 프로젝트는 애니메이션의 다양한 특징(예: 장르, 방영 연도, 제작사, 인기 지표 등)을 기반으로 더욱 정교한 추천시스템을 구축하고자 했다.
<br/>

### ⭐ 프로젝트 필요성
| **주제**                       | **내용**                                                                                   |
|---------------------------------|--------------------------------------------------------------------------------------------|
| **고객의 취향 발견**            | 이미 접한 애니메이션만 반복적으로 추천하는 시스템은 흥미롭지 않다. 애니메이션 고객 평점 기반으로 다양한 추천을 제공하는 시스템이 필요하다. 시청 가능한 애니메이션의 범위를 넓히고, 새로운 취향을 발견해보자 |
| **시장 경쟁력 확보를 위한 추천 시스템** | 콘텐츠 과잉 시대에서 추천 시스템의 경쟁력은 매우 중요한 요소이다. 사용자의 취향을 분석하고 새로운 콘텐츠를 발견할 수 있는 서비스를 통해, 기존의 단순히 '인기 있는 콘텐츠'만 추천하는 시스템을 넘어 사용자 이용 경험을 개선할 수 있다. 이를 통해 서비스 제공자 또한 차별화된 경쟁력을 확보할 수 있다. |
<hr>

## 3️⃣ 기술 스택
#### [데이터 시각화]
<p>
  <img src="https://img.shields.io/badge/pandas-150458.svg?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/matplotlib-0077B5.svg?style=for-the-badge&logo=matplotlib&logoColor=white"> <br>
  <img src="https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white"> 
  <img src= "https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white">
  <img src= "https://img.shields.io/badge/surprise-%23013243.svg?style=for-the-badge&logo=surprise&logoColor=blue">
  <img src= "https://img.shields.io/badge/scikit-learn-%3178C6.svg?style=for-the-badge&logo=surprise&logoColor=blue">
  <img src= "https://img.shields.io/badge/nltk-%23013243.svg?style=for-the-badge&logo=surprise&logoColor=blue">
  <img src= "https://img.shields.io/badge/request-%23013243.svg?style=for-the-badge&logo=surprise&logoColor=blue">
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


-------

## 📚분석과정
## 1. Data Cleaning
- 누락 데이터 및 중복데이터 삭제

![aninme missing data](https://github.com/user-attachments/assets/b5489a8b-f9c3-4fd8-802c-409d548863f8)
![rating data count](https://github.com/user-attachments/assets/744d6281-ea7c-4e6f-8273-69cbfb207f40)
![duplicate](https://github.com/user-attachments/assets/359cf71c-7bdc-4f29-8853-f4507a3d2d49)

## 2. Data Preprocessing
- 데이터 merge & 컬럼 rename
  
[before cleaning]
![image](https://github.com/user-attachments/assets/3ae78178-be13-4d6d-85c1-2f3cf0c8296c)

[after cleaning]
![image](https://github.com/user-attachments/assets/f8371a41-d855-477e-8ac6-ee47d29e0154)

- rating -1은 애니메이션을 시청함에도 평가하지 않은 데이터이므로 삭제
![image](https://github.com/user-attachments/assets/a5bcb586-52cb-4118-933b-9f0418e44244)
![image](https://github.com/user-attachments/assets/743c2b2d-6e64-4645-89c1-e07d2ce59f14)


- 텍스트 정규화 (불용어 처리)
    - df[name] 컬럼의 모든 값에 clean_txt()을 지정해 텍스트 정규화 
![image](https://github.com/user-attachments/assets/12ab0cce-96f9-4e3f-9825-03ca630db19d)

![image](https://github.com/user-attachments/assets/a6072f75-e0c5-4b37-acfc-bf0d3745ae47)

- anime rating 별 순위

![image](https://github.com/user-attachments/assets/f1d0474c-35b9-4a2a-939c-cabf8c0bb400)

- user rating 별 애니메이션 순위
?? 다시..

---

## 3. 인기 기반 추천 모델 생성 

### [협업 필터링 추천 시스템]

: 사용자 또는 아이템 간의 유사성을 바탕으로 추천

![image](https://github.com/user-attachments/assets/f4b77413-9650-45c5-8c03-aa17144d4ab3)


#### (1) label encoding 
- 범주형 데이터를 숫자로 변환
![image](https://github.com/user-attachments/assets/048917ce-90ad-4823-a2cd-1a94fa6a6c0d)


#### (2) K-means model 
- 애니메이션 데이터를 6개의 군집으로 나누도록 설정 (n_cluster = 6, random_state = 42)
![image](https://github.com/user-attachments/assets/3b09bb5b-e093-4464-a602-8fdc8e38843f)
![image](https://github.com/user-attachments/assets/93355d90-41f9-4db9-92de-ccfbda180370)

#### (3) KNN model 
- 랜덤한 사용자 선택 후 해당 사용자가 속한 클러스터를 저장
- knn 모델(NearestNeighbors)로 cosine similarity 측정 후 모델 학습 후 가장 유사한 애니메이션 찾기 
![image](https://github.com/user-attachments/assets/ed3ee595-6a12-4dce-90c7-07a3e2dddfaa)

---

### [콘텐츠 기반 추천 시스템]

: 애니메이션 시청자가 선호하는 콘텐츠의 특징을 분석하여 유사한 아이템을 추천 

![image](https://github.com/user-attachments/assets/eac9313d-0e9a-4e30-8810-9b1320d9201f)

#### (1) 단어 단위 TF-IDf 가중치, 장르 간 코사인 유사도 행렬 계산
#### (2) K-means 군집 내 데이터 추출 후 장르 정보를 문자열로 반환 
#### (3) 추천 애니메이션 인덱스 저장 후 결과 가져오기 
![image](https://github.com/user-attachments/assets/c7131ed2-07f5-4342-994b-feea1e9a9477)

---

### [SVD (특이값 분해)를 이용한 추천 시스템]

: 대규모 행렬의 차원을 줄이면서 중요한 정보만 보존

![image](https://github.com/user-attachments/assets/f0c7a522-3e5d-47dc-9189-b87f788d2fe7)

### [Hybrid(K-Means + SVD를 이용한 추천 시스템]

: 비슷한 취향을 가진 사용자 그룹을 만든 후, 그룹 내에서 SVD 모델을 사용하여 추천 
![image](https://github.com/user-attachments/assets/f2daf03a-d2f7-46f9-b422-927ecd0f674e)

---

## 🕶️ Appendix
![image](https://github.com/user-attachments/assets/e1a77f69-ea25-4d9a-b6b6-efca9de19753)

![image](https://github.com/user-attachments/assets/552340b2-1282-48a7-ac31-eeea50903681)

![image](https://github.com/user-attachments/assets/fa032156-73b1-49d5-b9ed-43211a9f97b4)

![image](https://github.com/user-attachments/assets/e203bd54-1b57-4523-9b0c-7f5024f84e74)


## ⭐ 한 줄 회고
🧑🏻 형주


🧑🏻‍🦱 근


👱🏻‍♀️ 민정

추천 시스템이라는 주제가 어려웠지만, 팀원 모두가 관심있어하는 공통주제로 프로젝트를 진행해서 재밌었습니다

👨🏻‍🦰 종현
