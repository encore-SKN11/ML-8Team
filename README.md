# 📺 애니메이션 평가 데이터를 활용한 평점 예측

## 1️⃣ 팀 소개
#### SKN Family AI 캠프 11기  ML 미니 프로젝트 <br/>
#### 기간: 2025.03.12 - 2025.03.21 <br/><br/>

### 👤 팀원
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
      <a href="https://github.com/minjung2266">
        <img src="https://github.com/minjung2266.png" width="150" alt="minjung"/><br /><hr/>
        안종현
      </a><br />
    </td>
  </thead>
</table>

<br/><br/>
<hr>

## 2️⃣ 프로젝트 소개




### 📖 프로젝트 목표
**객관적인 평점 예측을 위한 시스템 구축**

- 기존의 추천 시스템은 단순히 사용자의 과거 선호도가 반영되었다.
- 본 프로젝트는 애니메이션의 다양한 특징(예: 장르, 방영 연도, 제작사, 인기 지표 등)을 기반으로 더욱 정교한 추천시스템을 구축하고자 했다.

**사용자의 취향을 반영 할 수 있는 서비스 제공**

- kmeans를 사용하여 애니메이션과 고객별 평점을 분류하고 추후 사용자가 접하지 못했던 새로운 애니메이션을 추천하도록 한다.
- 이를 통해 사용자는 특정 장르나 유명 작품에 편중되지 않고 다양한 애니메이션을 접할 수 있다.
<br/>

### ⭐ 프로젝트 필요성



<hr>

## 3️⃣ 기술 스택
#### [데이터 시각화]
<p>
  <img src="https://img.shields.io/badge/pandas-150458.svg?style=for-the-badge&logo=pandas&logoColor=white"> <br>
  <img src="https://img.shields.io/badge/matplotlib-0077B5.svg?style=for-the-badge&logo=matplotlib&logoColor=white"> <br>
  <img src="https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white"> <br>
  <img src= "https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white">
</p>

<hr>
## 🔎 데이터
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anime & Rating Data</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            font-size: 18px;
            text-align: left;
        }
        th, td {
            padding: 12px;
            border: 1px solid #ddd;
        }
        th {
            background-color: #f4f4f4;
        }
    </style>
</head>
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anime & Rating Data</title>
    <style>
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            font-size: 18px;
            text-align: left;
        }
        th, td {
            padding: 12px;
            border: 1px solid #ddd;
        }
        th {
            background-color: #f4f4f4;
        }
    </style>
</head>
<body>
    <h2>Anime Dataset</h2>
    <h3>12994 rows</h3>
    <table>
        <tr>
            <th>anime_id</th>
            <th>name</th>
            <th>genre</th>
            <th>type</th>
            <th>episodes</th>
            <th>rating</th>
            <th>members</th>
        </tr>
        <tr>
            <td>Unique ID</td>
            <td>애니메이션 이름</td>
            <td>애니메이션 장르</td>
            <td>방영 유형</td>
            <td>에피소드 수</td>
            <td>평균 평점 (10점 만점)</td>
            <td>커뮤니티 멤버 수</td>
        </tr>
    </table>
    <h2>Rating Dataset</h2>
    <h3>7813737 rows</h3>
    <table>
        <tr>
            <th>user_id</th>
            <th>anime_id</th>
            <th>rating</th>
        </tr>
        <tr>
            <td>무작위 생성된 사용자 ID</td>
            <td>사용자가 평가한 애니메이션 ID</td>
            <td>사용자 평가 (10점 만점, -1은 미평가)</td>
        </tr>
    </table>
</body>
</html>

<hr>

## 🤓 분석 내용
1. 데이터의 속성별 의미<br>

2. 고객별 애니메이션 시청 경향

3. ...

<hr>

## 📚 분석 과정
### 1. 데이터 로드


#### 2. NaN 값 제거 및 결측값 제거


#### 3. 이상치 값 변경


#### 4. 데이터 비율의 편차가 큰 행 제거

#### 5. One-Hot-Encoding, Label Encording

### 3. 데이터 시각화


<hr>

## ⭐ 한 줄 회고
🧑🏻 형주


🧑🏻‍🦱 근


👱🏻‍♀️ 민정


👨🏻‍🦰 종현
