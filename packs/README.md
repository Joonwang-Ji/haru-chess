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
- v18: `puzzles-lv1b.json`, `puzzles-lv2b.json` (각 100개, `from` 2026-10-12)를 추가했습니다. 모든 퍼즐은 엔진으로 만들고 앱 규칙 엔진으로 다시 검증했습니다.
- v20: `puzzles-lv3b.json`(58) `puzzles-lv4b.json`(60) `puzzles-lv5b.json`(55)를 추가했습니다 (`from` 2026-10-13). 레벨 3 = 2수 메이트 35 + 최선의 한 수 23, 레벨 4·5 = 3수 메이트 각 45 + 최선의 한 수 15·10. 사람처럼 실수하는 엔진 자기대국(약한 쪽·강한 쪽)에서 뽑았고, 정답이 하나뿐인 위치만 남긴 뒤 앱 규칙 엔진으로 다시 검증했습니다.
- v20: 기존 `puzzles-lv2~5.json`의 "최선의 한 수" 중 23개는 막연한 `advantage`/`material`/`checkwin`/`trade` 대신 구체적인 `fork`(포크)·`pin`(핀)·`skewer`(스큐어)·`discover`(발견 공격) 태그로 바꿨습니다.
- v21: `puzzles-lv3c.json`(56) `puzzles-lv4c.json`(55) `puzzles-lv5c.json`(53)를 추가했습니다 (`from` 2026-10-14). 모두 "최선의 한 수"(`t`)이고, 자기대국 1,200판에서 새로 채굴해 앱 규칙 엔진으로 재검증했습니다. 레벨은 태그로 정했습니다(체크·교환=3, 포크·핀·발견=4, 재료 획득=5).
- `th` 키: fork pin skewer discover hang trade sac checkwin promo defmate escape material advantage

