# week09/tools.py 함수 설명

`tools.py`는 영화진흥위원회(KOBIS) 오픈 API에서 박스오피스 정보를 가져오는 도구 모음입니다.

## 공통 설정

- `requests` 라이브러리로 HTTP 요청을 보냅니다.
- API 키는 `secret.py`의 `API_KEY`에서 불러옵니다.
- `BASE_URL`은 KOBIS 일별 박스오피스 조회 API 주소입니다.

## 함수 목록

### `get_boxoffice_rank_1(date)`

지정한 날짜의 일별 박스오피스 1위 영화 제목을 돌려줍니다.

- **입력**: `date` (문자열) — 8자리 날짜. 예: `"20260824"`
- **출력**: (문자열) 1위 영화 제목. 예: `"오디세이"`

**동작 순서**

1. `key`(API 키)와 `targetDt`(조회 날짜)를 파라미터로 만듭니다.
2. `BASE_URL`에 GET 요청을 보냅니다. 타임아웃은 10초입니다.
3. 응답 JSON에서 `boxOfficeResult` → `dailyBoxOfficeList` 목록을 꺼냅니다.
4. 목록의 첫 번째 항목(1위)의 `movieNm`(영화 제목)을 돌려줍니다.

**참고**

- 함수 안 독스트링에는 매개변수 이름이 `data`로 적혀 있지만, 실제 이름은 `date`입니다.
- 요청 실패, 잘못된 날짜 형식, 빈 결과 목록 같은 경우를 따로 처리하지 않습니다. 이런 경우 `KeyError`나 `IndexError` 같은 예외가 날 수 있습니다.
