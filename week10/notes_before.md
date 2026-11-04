# notes_before.md - week09 `tools.py` 분석

## 파일 개요
`week09/tools.py`는 영화진흥위원회(KOBIS) 오픈 API를 사용해 **박스오피스 정보를 가져오는 도구 모음**이다.

- 사용 라이브러리: `requests`
- API 키: `secret.py`의 `API_KEY`에서 불러온다.
- 요청 주소(`BASE_URL`): KOBIS 일별 박스오피스 조회 API
  (`searchDailyBoxOfficeList.json`)

## 함수 목록

현재 정의된 함수는 **1개**이다.

### `get_boxoffice_rank_1(date)`

그 날짜의 박스오피스 1위 영화 제목을 알려준다.

| 항목 | 내용 |
|------|------|
| 받는 것 | `date` (문자열) - 8자리 날짜. 예: `"20260824"` |
| 돌려주는 것 | (문자열) 1위 영화 제목. 예: `"오디세이"` |

**동작 순서**
1. `API_KEY`와 `date`로 요청 파라미터(`key`, `targetDt`)를 만든다.
2. `requests.get()`으로 KOBIS API를 호출한다. (timeout 10초)
3. 응답을 JSON으로 바꾼 뒤 `boxOfficeResult` → `dailyBoxOfficeList`에서 영화 목록을 꺼낸다.
4. 목록의 첫 번째 영화(`movies[0]`)의 제목(`movieNm`)을 돌려준다.

**참고할 점**
- docstring의 "받는 것"에 매개변수 이름이 `data`로 적혀 있지만, 실제 매개변수 이름은 `date`이다.
- 오류 처리가 없다. 날짜 형식이 틀리거나 API 키가 잘못되면 `KeyError`/`IndexError`가 날 수 있다.
