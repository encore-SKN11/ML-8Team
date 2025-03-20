# 📺 애니메이션 평가 데이터를 활용한 평점 예측 및 추천 서비스

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

-------

## 📚분석과정
## 1. Data Load & Cleaning
#### (1) 데이터 로드 및 분포 확인
```python
rating = pd.read_csv('./data/rating.csv')
anime = pd.read_csv('./data/anime.csv')
```

```python
anime.head()
```
![image](https://github.com/user-attachments/assets/6ce8f835-1104-47fa-a5c9-f495efcd1c2f)

```python
rating.head()
```
![image](https://github.com/user-attachments/assets/1e095649-bf38-449a-be41-b23f01f3db66)


#### (2) 결측치 제거
- Check & Remove Missing Value
```python
anime.isna().sum()
anime.dropna(axis=0, inplace=True)
anime.isna().sum()
```
- Check Duplicates
```python
duplicated_rating = rating[rating.duplicated()].shape[0]
print(f'count of dupliacte anime: {duplicated_rating}')
```
- Remove Duplicates
```python
rating.drop_duplicates(keep='first', inplace=True) # 첫 번쨰 등장한 값 유지

duplicated_rating = rating[rating.duplicated()].shape[0]
print(f'count of duplicated anime after removing: {duplicated_rating}')
```

## 2. Data Preprocessing
#### 1. 데이터 merge
```python
df = pd.merge(anime, rating, on='anime_id')
df.to_csv("./data/anime_rating_merged.csv", index=False)
```
![image](https://github.com/user-attachments/assets/3ae78178-be13-4d6d-85c1-2f3cf0c8296c)



<hr>

## 3. 모델 학습 및 평가 
<h3>인기 기반 애니메이션 추천</h3>

- user rating 순위

- anime rating 순위

- first genre 생성

## ⭐ 한 줄 회고
🧑🏻 형주


🧑🏻‍🦱 근


👱🏻‍♀️ 민정


👨🏻‍🦰 종현
