<<<<<<< HEAD
# week09 - 박스오피스 1위 조회

## 무엇을 하는 코드인가
영화진흥위원회(KOBIS) 오픈 API로 지정한 날짜의 일별 박스오피스 1위 영화 제목을 가져와 출력합니다.

## 설치
```
pip install -r requirements.txt
```
같은 폴더에 `secret.py`를 만들고 KOBIS API 키를 넣어야 합니다.
```python
API_KEY = "발급받은_키"
```

## 실행
```
python main.py
```
날짜를 바꾸려면 `main.py`의 `"20260824"`를 원하는 8자리 날짜로 고치면 됩니다.
=======
# week09 - 박스오피스 1위 영화 조회

## 무엇을 하는 코드인가
영화진흥위원회(KOBIS) 오픈 API로 특정 날짜의 일별 박스오피스 1위 영화 제목을 가져와 출력합니다.

## 설치
```bash
pip install -r requirements.txt
```
같은 폴더에 `secret.py`를 만들고 KOBIS API 키를 넣어 주세요.
```python
API_KEY = "발급받은_API_키"
```

## 실행
```bash
python main.py
```
조회할 날짜는 `main.py`에서 `"YYYYMMDD"` 형식으로 바꾸면 됩니다.
>>>>>>> d91df2010ff269de3b4e3117aae0b462fb62e573
