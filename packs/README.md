# 하루체스 콘텐츠 팩

새 상점 아이템·배지·퍼즐을 앱 코드 수정 없이 추가합니다.

1. 팩 파일(예: `2027-01.json`)을 이 폴더에 올립니다. 형식은 `season-example.json` 참고.
2. `index.json` 의 `packs` 목록에 파일명을 추가합니다. 예: `{ "packs": ["2027-01.json"] }`
3. GitHub에 커밋하면 앱이 다음 실행 때 자동으로 읽습니다.

- `from`(날짜): 그 날짜부터 퍼즐이 매일 퍼즐 풀에 들어가고, 아이템은 그날부터 상점에 보입니다.
- 잘못된 항목(중복 id, 불법 수, 위험한 SVG 등)은 자동으로 무시되고 나머지는 정상 로드됩니다.
- slot: hat / face / neck (SVG, 100x100 좌표), board(vars l,d), piece(vars wf wl bf bl wd bd).
- 배지 m(지표): chap c3 basicAll earned streakMax games wins loss lvwin net level pz pzp rev ms wk buy

## 퍼즐 (v12)
- `k`: m1(1수 메이트) m2(2수 메이트) m3(3수 메이트) f(공짜 기물) t(최고의 한 수 찾기)
- `lv`: 난이도 1~5 (1 입문, 2 초급, 3 중급, 4 상급, 5 고수). 빠지면 종류별 기본값(m1·f=1, m2=2, m3·t=4)
- `ok`: 정답 첫 수 목록(UCI). m1·m2는 앱이 직접 메이트를 확인하고, f·m3·t는 이 목록으로 확인합니다.
- 설정 > 오늘의 퍼즐 난이도에서 자동/1~5단계를 고르면 그 단계의 퍼즐이 하루에 하나씩 나옵니다. (프로필마다 따로 저장)
- 파일 `puzzles-lv1.json` ~ `puzzles-lv5.json` 은 단계별로 나눈 기본 팩입니다.
