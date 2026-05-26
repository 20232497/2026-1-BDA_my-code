# 2026-1-BDA
2026년 1학기 '빅데이터분석프로그래밍' 교과목

## 교재
- 주교재
  - 파이썬으로 배우는 데이터분석 입문, 강환수 저, 도서출판 홍릉
  - https://product.kyobobook.co.kr/detail/S000214156345

    > <img width="458" height="629" alt="image" src="https://github.com/user-attachments/assets/6913e3ab-5ed9-422e-b36e-9453c16e2f4e" />

- 보조교재
  - Do It 쉽게 배우는 파이썬 데이터분석, 김영우 저, 이지퍼블리싱 

---

## 수업 일정
| 주차 | 일자         | 요일  | 교재      | 주제        | 원일자        | 비고     |
| -- | ---------- | --- | ------- | --------- | ---------- | ------ |
| 1  | 2026-03-04 | 수요일 | 1장      |           |            |        |
| 2  | 2026-03-11 | 수요일 | 2장      |           |            |        |
| 3  | 2026-03-18 | 수요일 | 3장      |           |            |        |
| 4  | 2026-03-25 | 수요일 | 4장      |           |            |        |
| 5  | 2026-04-01 | 수요일 | 5~6장    |           |            |        |
| 6  | 2026-04-08 | 수요일 | 6~7장    |           |            |        |
| 7  | 2026-04-15 | 수요일 | 7~8장    |           |            |        |
| 8  | 2026-04-22 | 수요일 |         | 중간고사      |            |        |
| 9  | 2026-04-29 | 수요일 | 9장      | 데이터시각화 1  |            |        |
| 10 | 2026-05-06 | 수요일 | 9장      | 데이터시각화 2  |            |        |
| 11 | 2026-05-13 | 수요일 | 보조교재 6장 | - 그룹화와 집계함수 - merge |            |        |
| **12** | **2026-06-04** | **목요일** | [Pandas Cookbook](https://pandas.pydata.org/docs/user_guide/cookbook.html) | Pandas 레시피 | 2026-05-20 | 원격 수업(동영상 시청) |
| 13 | 2026-05-27 | 수요일 |         | 과제발표      |            | 팀 및 개인 과제 모두 마감  |
| 14 | 2026-06-10 | 수요일 | 보조교재 7장 | 결측값과 이상값  | 2026-06-03 |        |
| 15 | 2026-06-17 | 수요일 |         | 기말고사      |            |        |


## 온라인 출석과 수업 참여
- [A반(QA) 수요일 오전](https://docs.google.com/spreadsheets/d/1D6ayWWOMeVnYbkdMYzPTb6pRjdNcvLFk4VPmn_ylpus/edit?usp=sharing)
- [B반(QB) 수요일 오후](https://docs.google.com/spreadsheets/d/1eSEnDMEoiSUiUgyeKz_xyt1tmn8EPJ3cRPKXZdKE7i4/edit?usp=sharing)

## 시험 일정과 점수
- 중간고사
  - [QA 2026/4/22수 오전 11:00 ~ 11:50 6-406호](https://claude.ai/artifacts/latest/3c19a0fb-ec76-4a1c-b993-26b5f3806dcc)
  - QB 2026/4/22수 오후 14:00 ~ 14:50 6-406호
- 기말고사
  - QA 2026/6/17수 오후 12:00 ~ 12:50 
  - QB 2026/6/17수 오후 14:00 ~ 14:50 

## 타이타닉 열(변수) 설명
- survived : 0 = 사망, 1 = 생존
- pclass : 1 = 1등석, 2 = 2등석, 3 = 3등석
- sex : male = 남성, female = 여성
- age : 나이
- sibsp : 타이타닉 호에 동승한 자매 / 배우자의 수
- parch : 타이타닉 호에 동승한 부모 / 자식의 수
- fare : 티켓 요금
- embarked : 탑승지, C = 셰르부르, Q = 퀸즈타운, S = 사우샘프턴
- class : First = 1등석, Second = 2등석, Third = 3등석
- who : 남/여/아이, 'man', 'woman', 'child'
- adult_male : 남자 어른, True/False
- deck : 방 위치, 'A', 'B', 'C', 'D', 'E', 'F', 'G', NaN
- embark_town : 탑승지
- alive : 생존, yes/no
- alone : 1인 탑승, True/False

### deck(방 위치)
- ![image](https://github.com/user-attachments/assets/8be11782-751f-4934-ac37-57930fbbc1f3)

## 데이터분석 프로그래밍(4-5명 팀 과제)
- 다음 두 과제를 모두 수행
  - 과제1: 지정 데이터(titanic1309.csv) 분석: 타이타닉호 데이터 분석
  - 과제2: 자유 데이터 분석: 공공 데이터 분석 선택
- A반 5/27(수), B반 5/27(수) 수업에서 발표
  - 주피터노트북(발표 내용과 코드)으로 발표(발표시간은 약 10~15분)
- 데이터 공모전에 참가하는 방향으로 자유 데이터 활용
  - [교통데이터 공모전](https://www.bigdata-transportation.kr/pageant/dashboard/CMPE_000000000020041)

## 지도 시각화 수업 참조
- [웹참조](https://pjh09050.tistory.com/11)
  
## 가로로 여러 데이터프레임 출력 함수
```Python
from IPython.display import display_html
import inspect
import ast

def display_side_by_side(*dfs):
    titles = []

    try:
        caller_frame = inspect.currentframe().f_back
        call_line = inspect.getframeinfo(caller_frame).code_context[0].strip()

        tree = ast.parse(call_line)
        call = tree.body[0].value

        if isinstance(call, ast.Call):
            for arg in call.args:
                titles.append(ast.get_source_segment(call_line, arg))
    except:
        titles = [''] * len(dfs)

    if len(titles) < len(dfs):
        titles += [''] * (len(dfs) - len(titles))

    html_str = ''
    for df, title in zip(dfs, titles):
        html_str += f"""
        <div style="display:inline-block; vertical-align:top; margin-right:20px; text-align:center;">
            <div style="font-weight:bold; font-size:13px; margin-bottom:8px; text-align:center;">
                {title}
            </div>
            <div style="display:flex; justify-content:center;">
                {df.to_html()}
            </div>
        </div>
        """

    display_html(html_str, raw=True)
```

## 가로로 여러 시리즈 출력 함수
```Python
from IPython.display import display_html
import inspect
import ast

def display_series_side_by_side(*args):
    """여러 Series를 옆으로 나란히 표시하고,
    호출 시 사용한 표현식을 제목으로 위에 출력한다.
    """
    titles = []

    try:
        caller_frame = inspect.currentframe().f_back
        call_line = inspect.getframeinfo(caller_frame).code_context[0].strip()

        tree = ast.parse(call_line)
        call = tree.body[0].value

        if isinstance(call, ast.Call):
            for arg in call.args:
                titles.append(ast.get_source_segment(call_line, arg))
    except:
        titles = [''] * len(args)

    if len(titles) < len(args):
        titles += [''] * (len(args) - len(titles))

    html_str = ''
    for s, title in zip(args, titles):
        table_html = s.to_frame().to_html()

        html_str += f"""
        <div style="display:inline-block; vertical-align:top; margin-right:20px; text-align:center;">
            <div style="font-weight:bold; font-size:13px; margin-bottom:8px; text-align:center;">
                {title}
            </div>
            <div style="display:flex; justify-content:center;">
                {table_html}
            </div>
        </div>
        """

    display_html(html_str, raw=True)
```

## Google Colab 셀 복사 및 붙여넣기 단축키

- 🔹 셀 복사 & 붙여넣기 단축키

| 작업 | Windows / Linux | Mac |
|------|----------------|-----|
| **셀 복사** | `Ctrl + M, C` | `Cmd + M, C` |
| **셀 붙여넣기** | `Ctrl + M, V` | `Cmd + M, V` |

- 🔹 추가로 유용한 셀 관련 단축키

| 작업 | Windows / Linux | Mac |
|------|----------------|-----|
| **셀 잘라내기** | `Ctrl + M, X` | `Cmd + M, X` |
| **셀 삭제** | `Ctrl + M, D` | `Cmd + M, D` |
| **새 코드 셀 추가** | `Ctrl + M, B` | `Cmd + M, B` |
| **셀 실행** | `Shift + Enter` | `Shift + Enter` |
| **셀 실행 후 아래에 새 셀 추가** | `Alt + Enter` | `Alt + Enter` |

> 💡 `Ctrl + M` (`Cmd + M` on Mac)을 누른 후 해당 키를 입력하면 실행됩니다.  
> Colab에서 셀을 빠르게 조작할 때 활용해 보세요! 🚀


---

### numpy 소수 자릿 설정
```
# NumPy 라이브러리를 불러오고, 배열 출력 형식을 보기 좋게 설정합니다.
import numpy as np
# suppress=True는 과학적 표기법(예: 1.23e-10)을 억제하고
# 항상 고정 소수점 표기법(fixed point notation)을 사용
np.set_printoptions(suppress=True, precision=4)
```

### pandas 소수 자릿 설정
```Python
pd.set_option('display.float_format', '{:.2f}'.format)  # 전역 적용
pd.reset_option('display.float_format')                 # 초기화
```
