# 12개 모드 상세 조사 보고서
> 상태: 현행 | 최종 수정: 2026-03-08

## 비교 기준: 현재 설치된 모드 목록
Terralith, BiomesOPlenty, YungsBetterDungeons, YungsBetterMineshafts, YungsBetterStrongholds, Explorify, FarmersDelight, bettercombat, simplyswords, artifacts, supplementaries, deeperdarker, aether, TechReborn, minecells, friendsandfoes, chipped, mcw-bridges/doors/furniture/fences/windows/roofs, immersive_aircraft, immersive_armors, travelersbackpack, waystones, gravestones, Jade, REI, xaerominimap, xaeroworldmap, appleskin, IronChests, tide, lovely_snails, mythic_mounts

---

## 1. LuckPerms (럭펌스)

**한줄 요약**: 서버 권한 관리 플러그인으로, 그룹/유저별로 명령어와 기능 접근 권한을 세밀하게 제어.

### 추가 콘텐츠 상세
- **블록**: 없음
- **아이템/무기/방어구**: 없음
- **몹/보스**: 없음
- **구조물**: 없음
- **바이옴**: 없음
- **시스템/메카닉**:
  - 명령어 기반 권한 시스템: `/lp user`, `/lp group`, `/lp track`
  - 그룹 생성/상속 (예: default → vip → admin)
  - 퍼미션 노드 시스템 (예: `minecraft.command.teleport`)
  - 웹 에디터 (https://luckperms.net/editor)로 GUI 기반 권한 편집
  - 데이터 저장: H2/MySQL/MariaDB/PostgreSQL/MongoDB/YAML 지원
  - Fabric Permission API 연동
  - Prefix/Suffix 설정 (채팅/탭리스트 표시용)
  - 컨텍스트 기반 권한 (월드, 서버, 바이옴별 조건부 적용)

### 성능 영향
- **최소**. 순수 서버사이드 권한 체크 모듈이므로 TPS에 거의 영향 없음. DB 백엔드 사용 시 초기 로딩에만 약간의 오버헤드.

### 다른 모드와 중복
- 없음. 현재 설치 목록에 권한 관리 모드가 없음.

### 제거 시 영향
- 게임 내 블록/아이템 변경 없으므로 월드 손상 없음.
- 모든 권한 설정이 초기화되어 모든 플레이어가 기본 권한(OP 기반)으로 복귀.
- 다른 모드가 Fabric Permission API에 의존하는 경우 해당 권한 체크가 무효화됨.

---

## 2. Spectrum (스펙트럼)

**한줄 요약**: 색상의 힘을 활용하는 스토리 기반 탐험/마법 모드. 독자적 진행 체계, 커스텀 차원, 수백 개의 블록/아이템 추가.

### 추가 콘텐츠 상세
- **블록** (~200개 이상):
  - 보석 블록: Topaz Block, Amethyst Block, Citrine Block, Onyx Block, Moonstone Block
  - 광석: Shimmerstone Ore, Azurite Ore, Stratine Ore, Paltaeria Ore
  - 기능 블록: Preservation Stone, Memory Manifesting Block, Mob Blocks (몹별 특수 효과 블록)
  - 장식 블록: Basalt & Calcite 변형, Gemstone Lamp, Colored Planks/Wool/Glass 등
  - 식물: Quitoxic Reeds, Mermaids Brush, Sawblade Holly 등

- **아이템/무기/방어구**:
  - **Bedrock Armor Set** (투구/흉갑/각반/부츠) — 파괴불가, 네더라이트보다 약간 높은 스탯, 최대 레벨 초과 인챈트 1개 내장
  - **Bedrock Tools** (검/곡괭이/도끼/삽/괭이) — 파괴불가
  - 보석 도구: Topaz/Amethyst/Citrine 등급별 도구 세트
  - 특수 아이템: Midnight Solution (지형 부식), Bottle of Ruin (베드락 파괴), Perfect Compound, Soul Gems, Ink Flasks (16색)
  - Guidebook: "Colorful World" (인게임 가이드북, 첫 보석 발견 시 자동 지급)

- **몹/보스**:
  - **Monstrosity** — Deeper Down 차원의 보스 (개발 진행 중, 현재 스폰 비활성)
  - 기존 몹 변형 시스템: Spirit Instiller로 액솔로틀 색상 변경, 스켈레톤 호스 생성 등
  - Mob Head 변환 시스템

- **구조물**:
  - Gemstone Geodes (보석 지오드) — 지하에 자연 생성
  - Deeper Down 차원 포탈 공간

- **바이옴**:
  - Deeper Down 차원 내 커스텀 바이옴 (개발 중)

- **시스템/메카닉** (제작대 10종):
  | 제작대 | 기능 |
  |--------|------|
  | Pigment Pedestal (Topaz/Amethyst/Citrine/CMY/Onyx) | 메인 제작대, 등급별 업그레이드 |
  | Fusion Shrine | 크리스탈 + 용암으로 융합 제작 |
  | Enchanter | 인챈트 적용 (앤빌 전용 인챈트도 가능) |
  | Potion Workshop | 커스텀 포션 제작 |
  | Spirit Instiller | 몹 변형, 고급 제작 |
  | Cinderhearth | Ink 연료 용광로 (속도/복제/경험치 업그레이드) |
  | Crystallarieum | 보석 자동 재배 |
  | Titration Barrel | 발효/숙성 시스템 |
  | Anvil Crushing | 모루 낙하 제작 |
  | Liquid Dipping | 액체 담금 제작 |

  - **Ink 시스템**: 16색 Ink를 수집/저장하여 장비/기계에 연료로 사용
  - **Revelations 시스템**: 진행도에 따라 새로운 광석/식물/현상이 월드에 점진적으로 가시화
  - **Deeper Down 차원**: 베드락 아래 차원, Bottle of Ruin으로 진입

### 성능 영향
- **중간~높음**. 이유:
  - Revelations 시스템이 플레이어 진행도에 따라 월드 생성을 동적으로 변경 → 청크 로딩 시 추가 연산
  - 다수의 멀티블록 구조 + Ink 시스템 tick 처리
  - Crystallarieum 자동 재배 블록이 많으면 tick 부하 증가
  - Deeper Down 차원 추가로 메모리 사용량 증가

### 다른 모드와 중복
- **TechReborn**: 양쪽 모두 광석/제련/자동화 시스템 보유. Spectrum의 Cinderhearth vs TechReborn의 전기 용광로
- **deeperdarker**: 양쪽 모두 "깊은 곳" 탐험 콘텐츠. Deeper Down vs Otherside 차원
- **artifacts**: 양쪽 모두 특수 장신구/아이템 추가
- **supplementaries**: 장식 블록 일부 중복 가능
- **simplyswords**: 무기 체계 일부 중복 (Bedrock Sword vs Simply Swords 무기류)

### 제거 시 영향
- **심각**. 모든 Spectrum 블록이 공기로 변환 (제작대, 장식 블록, 광석 전부)
- Bedrock 장비/도구 소멸
- Deeper Down 차원 데이터 무효화
- Guidebook 아이템 소실
- Ink 시스템 관련 인벤토리 아이템 전부 소실
- Gemstone Geodes 내부의 커스텀 블록 소실

---

## 3. AdditionalStructures (추가 구조물)

**한줄 요약**: 약 250개의 소~중형 구조물을 오버월드/네더/엔드에 추가하는 경량 구조물 모드.

### 추가 콘텐츠 상세
- **블록**: 없음 (바닐라 블록만 사용)
- **아이템/무기/방어구**: 없음 (바닐라 전리품 테이블 사용)
- **몹/보스**: 없음
- **구조물** (~250개):
  - **자연물**: Big Cacti, Rock Formations, Trees, Bushes, Dead Trees
  - **소형 건축물**: Scarecrows, Camps, Totems, Oasis, Pillars, Skulls
  - **중형 건축물**: Altars, Temples (Maya Temple 등), Houses, Dungeons
  - **트랩 구조물**: 함정이 있는 사원류
  - 오버월드/네더/엔드 전 차원에 분포
  - Terralith, BOP, Biome Bundle 등 바이옴 모드와 호환
- **바이옴**: 없음
- **시스템/메카닉**: 없음

### 성능 영향
- **낮음~중간**. 이유:
  - 구조물이 월드 생성 시에만 배치되므로 TPS에 직접 영향은 적음
  - 다만 250개의 구조물 템플릿이 청크 생성 시 체크되므로 새 청크 탐험 시 약간의 지연
  - 다른 구조물 모드와 함께 사용 시 구조물 겹침으로 인한 생성 충돌 가능

### 다른 모드와 중복
- **YungsBetterDungeons**: 던전 구조물 중복 (지하 던전, 사원류)
- **YungsBetterMineshafts**: 폐광 관련 구조물 가능 중복
- **Explorify**: 소형 구조물(캠프, 폐허 등) 직접적으로 중복
- **When Dungeons Arise** (설치 검토 중): 대형 구조물 겹침 가능
- **supplementaries**: 일부 장식 구조물 겹침 가능

### 제거 시 영향
- **낮음**. 바닐라 블록으로만 구성되므로 이미 생성된 구조물은 그대로 유지됨.
- 구조물 자체는 바닐라 블록이라 깨지지 않음.
- 새로운 청크에 더 이상 해당 구조물이 생성되지 않을 뿐.

---

## 4. When Dungeons Arise (던전스 어라이즈)

**한줄 요약**: 30개 이상의 거대하고 정교한 구조물을 오버월드/네더/엔드에 추가. 수백~수천 블록 규모의 대형 던전.

### 추가 콘텐츠 상세
- **블록**: 없음 (바닐라 블록 사용)
- **아이템/무기/방어구**: 없음 (바닐라 전리품 테이블)
- **몹/보스**: 없음 (바닐라 몹 스포너 활용, 주로 일리저 계열)
- **구조물** (30개+):

  | 구조물 | 생성 바이옴 | 규모 |
  |--------|------------|------|
  | Abandoned Temple | 타이가, 산악 | 중형 |
  | Bandit Village | 평원, 사바나 | 중형 |
  | Ceryneian Hind | 숲 | 소형 |
  | Coliseum | 사막, 평원 | 대형 |
  | Desert City | 사막 | 초대형 |
  | Fishing Hut | 강/호수 인접 | 소형 |
  | Foundry (WIP) | 산악 | 대형 |
  | Giant Mushroom | 버섯섬 | 중형 |
  | Heavenly Riders | 하늘 | 대형 |
  | Heavenly Challengers | 하늘 | 대형 |
  | Heavenly Conquerors | 하늘 | 대형 |
  | Illager Campsite | 다양한 바이옴 | 소형 |
  | Illager Fort | 설원, 눈덮인 타이가 | 대형 |
  | Illager Galley | 바다 | 대형 |
  | Illager Corsair | 바다 | 중형 |
  | Illager Castle (WIP) | 평원 | 초대형 |
  | Illager Hall (WIP) | 숲 | 대형 |
  | Infested Temple | 정글 | 대형 |
  | Keep Kayra | 평원, 숲 | 대형 |
  | Lighthouse | 해안 | 중형 |
  | Merchant Campsite | 평원, 초원 | 소형 |
  | Mining System | 지하 | 대형 |
  | Monastery | 산악, 숲 | 대형 |
  | Mushroom House | 버섯섬, 늪 | 소형 |
  | Mushroom Mine | 늪지대 | 중형 |
  | Mushroom Village | 버섯섬 | 중형 |
  | Plague Asylum | 늪, 어두운 숲 | 대형 |
  | Scorched Mine | 네더 | 대형 |
  | Shiraz Palace | 사막, 메사 | 초대형 |
  | Small Blimp | 하늘 | 소형 |
  | Small Prairie House | 평원, 초원 | 소형 |
  | Thornborn Towers | 다양한 바이옴 | 대형 |
  | Typhon | 바다/해안 | 대형 |
  | Undead Pirate Ship | 바다 | 대형 |
  | Wishing Well | 다양한 바이옴 | 소형 |

- **바이옴**: 없음
- **시스템/메카닉**: 없음. Forge Biome Dictionary 기반 모드 바이옴 자동 호환.

### 성능 영향
- **중간**. 이유:
  - 초대형 구조물(Shiraz Palace, Desert City 등)이 수천 블록 규모 → 생성 시 청크 로딩 급증
  - 구조물 내부에 대량의 바닐라 몹 스포너 → 해당 청크 로드 시 TPS 감소
  - 하늘 구조물(Heavenly 시리즈)이 높이 제한까지 차지 → 라이트 엔진 부하

### 다른 모드와 중복
- **YungsBetterDungeons**: 던전/사원 구조물 주제 중복
- **YungsBetterMineshafts**: Mining System과 폐광 테마 중복
- **YungsBetterStrongholds**: 지하 요새 테마 유사
- **Explorify**: 소형 구조물(캠프, 오두막) 중복
- **AdditionalStructures** (설치 검토 중): 사원, 제단, 집 등 카테고리 중복

### 제거 시 영향
- **낮음**. 바닐라 블록만 사용하므로 이미 생성된 구조물은 온전히 유지됨.
- 구조물 내 스포너/체스트도 바닐라라 정상 작동.
- 새 청크에 더 이상 생성되지 않을 뿐.

---

## 5. IllagerInvasion (일리저 인베이전)

**한줄 요약**: 11종의 신규 일리저 몹, 전용 구조물, 인챈트 업그레이드 시스템 추가.

### 추가 콘텐츠 상세
- **블록**:
  - Imbuing Table (인챈트 업그레이드 전용 워크벤치)

- **아이템/무기/방어구**:
  - **Hallowed Gem**: Invoker 드롭, Imbuing Table 사용에 필요
  - **Unusual Dust**: Sorcerer 드롭
  - **Lost Candle**: 근처 광석 위치 표시
  - **Horn of Sight**: 주변 몬스터에 발광 효과 부여
  - **Hatchet**: Marauder 투척 무기

- **몹** (11종):

  | 몹 이름 | 역할 | 공격 패턴 |
  |---------|------|----------|
  | Marauder | 원거리 딜러 | 손도끼(Hatchet) 투척 |
  | Basher | 돌격 전사 | 방패 들고 돌진 공격 |
  | Provoker | 지원/버프 | 활 사용 + 버프 주문 |
  | Sorcerer | 마법사 | 보라색 불꽃 소환, 순간이동 |
  | Necromancer | 소환사 | 언데드 소환 마법 |
  | Inquisitor | 중전사 | 강력한 방패 전투 (방패 파괴 후 공격 가능) |
  | Firecaller | 화염 마법사 | 겉보기 무해, 강력한 화염 마법 |
  | Alchemist | 연금술사 | 활 + 잔류 포션 투척 |
  | Archivist | 기록관 | 마법 공격 |
  | Invoker | 보스급 | 최강 일리저, Hallowed Gem 드롭 |
  | Illusioner | 환영술사 | 바닐라 미사용 몹 활성화, 환영 공격 |

- **구조물**:
  - Illager Fort (어두운 숲/타이가에 생성)
  - Illager Tower (다양한 바이옴)
  - Sorcerer Hut (어두운 숲, 소형 오두막)
  - Firecaller Hut

- **바이옴**: 없음
- **시스템/메카닉**:
  - **Imbuing Table**: Hallowed Gem을 소비하여 인챈트를 최대 레벨 이상으로 업그레이드 (예: 날카로움 V → VI)

### 성능 영향
- **중간**. 이유:
  - 11종의 신규 몹이 바닐라 일리저 스폰 로직 위에 추가됨 → 일리저 순찰대/습격에 신규 몹 포함 시 엔티티 수 증가
  - 특히 Necromancer의 언데드 소환과 Sorcerer의 불꽃 파티클이 서버/클라 양쪽에 부하
  - 습격(Raid) 이벤트에 신규 몹 추가 시 습격 난이도와 엔티티 수 동시 증가

### 다른 모드와 중복
- **friendsandfoes**: 양쪽 모두 바닐라 몹 확장. Friends and Foes는 투표 탈락 몹 추가, IllagerInvasion은 일리저 확장
- **bettercombat**: 전투 시스템 위에 Imbuing Table 인챈트 강화가 밸런스에 영향
- **simplyswords**: Hatchet 등 커스텀 무기와 Simply Swords 무기 체계 공존
- **When Dungeons Arise** (설치 검토 중): Illager Fort/Castle 등 일리저 구조물 주제 중복

### 제거 시 영향
- **중간**.
  - Imbuing Table 블록 소실
  - Hallowed Gem, Unusual Dust, Lost Candle, Horn of Sight 등 커스텀 아이템 소실
  - 이미 적용된 초과 레벨 인챈트는 유지될 가능성 높음 (바닐라 NBT에 저장)
  - 커스텀 몹이 로드되지 않아 해당 엔티티 데이터 오류 로그 발생
  - 구조물 자체는 바닐라 블록이라 유지

---

## 6. Bosses of Mass Destruction / BOMD (대량파괴의 보스들)

**한줄 요약**: 4종의 고난이도 보스와 전용 구조물/전리품을 오버월드/네더/엔드에 추가.

### 추가 콘텐츠 상세
- **블록**: 보스 구조물 전용 장식 블록 일부

- **아이템/무기/방어구**:
  - **Soul Star**: Night Lich 타워 위치 추적용 아이템
  - **Ancient Anima**: Night Lich 드롭
  - **Obsidian Heart**: Obsidilith 드롭
  - **Blazing Eye**: Nether Gauntlet 드롭 → Table of Elevation, Blast Amplifier 제작
  - **Crystal Fruit**: Void Blossom 드롭
  - **Void Thorns**: Void Blossom 드롭 → Charged Ender Pearl, Earthdive Spear 제작
  - **Void Lily**: Void Blossom 위치 추적용 식물
  - **Earthdive Spear**: 지면 관통 투척 무기
  - **Charged Ender Pearl**: 강화된 엔더 진주

- **몹/보스** (4종):

  | 보스 | 체력 | 위치 | 주요 공격 | 드롭 |
  |------|------|------|----------|------|
  | Night Lich | 300 HP | 오버월드 한랭 바이옴 (Lich Tower) | 마법 구체 투사, 레이저, 팬텀 소환 | Ancient Anima, 인챈트 책 |
  | Obsidilith | 300 HP | 엔드 (Obsidilith Arena) | 순간이동 + 폭발, 룬 블록 소환 자가강화 | Obsidian Heart, 인챈트 다이아 곡괭이 |
  | Nether Gauntlet | 250 HP | 네더 (전용 구조물) | 눈만 약점, 주먹 공격, 레이저, 실명 부여 | Blazing Eye |
  | Void Blossom | 300 HP (추정) | 오버월드 최하층 동굴 (Lush Cave 외형) | 영구 가시 효과, 가시 덤불 소환, 범위 공격 | Crystal Fruit, Void Thorns |

- **구조물**:
  - **Lich Tower**: 한랭 바이옴 지표면, Soul Star로 추적
  - **Obsidilith Arena**: 엔드 외곽 섬, 거대 부유 구조물
  - **Nether Gauntlet Arena**: 네더 내 희귀 구조물
  - **Void Blossom Cave**: 오버월드 Y=-50 부근, Void Lily로 추적

- **바이옴**: 없음
- **시스템/메카닉**:
  - 보스 추적 시스템 (Soul Star, Void Lily)
  - Table of Elevation: Blazing Eye로 제작하는 유틸리티 블록

### 성능 영향
- **낮음** (보스 전투 중에만 **높음**). 이유:
  - 보스 구조물은 희귀 생성이므로 평상시 TPS 영향 미미
  - Night Lich 전투: 팬텀 대량 소환 → 일시적 엔티티 폭증
  - Obsidilith 전투: 룬 블록 대량 생성/파괴 → 블록 업데이트 폭증
  - Void Blossom 전투: 가시 덤불 대량 배치 → 블록 업데이트 + 엔티티 피해 계산

### 다른 모드와 중복
- **minecells**: 양쪽 모두 보스전 콘텐츠. 다만 MineCells는 로그라이크 던전, BOMD는 오픈월드 보스
- **aether**: 엔드게임 보스 콘텐츠 일부 주제 중복
- **deeperdarker**: Void Blossom의 "깊은 동굴 보스" 컨셉이 Deeper Darker의 Otherside와 유사

### 제거 시 영향
- **중간**.
  - 보스 구조물의 커스텀 블록 소실 (장식 블록 부분)
  - Soul Star, Earthdive Spear, Charged Ender Pearl 등 커스텀 아이템 소실
  - 보스 엔티티 데이터 오류 로그 (이미 소환된 보스가 있었다면)
  - 구조물의 바닐라 블록 부분은 유지

---

## 7. Incendium (인센디움)

**한줄 요약**: 네더를 완전히 개편하는 데이터팩. 9개 신규 바이옴, 9개 구조물, 25개 이상의 커스텀 무기/아이템 추가.

### 추가 콘텐츠 상세
- **블록**: 없음 (커스텀 블록 없이 바닐라 블록만 활용, 데이터팩 특성)

- **아이템/무기/방어구** (25개+):
  - **무기 (17종)**: Blazing Hatchet, Multiplex Crossbow, Chilling Blade, Holy Wrath, Torch of Lunacy, Daybreaker, Sentry's Wrath, Warping Witherblade, Firestorm, Withersbane, Ragnarok, Scarlet Dagger, Voltaic Trident, Piglin Slayer, Greatsword of Sacrifice, Trailblazer (화염 방사 활), Restless Nature
  - **도구**: Hefty Pickaxe
  - **방어구/방패**: Scout's Battle Helm, Infernal Wings, Infernal Feather, Hazmat Suit, Radiation Shield, Prismatic Shield, Necrotic Shield
  - **포션**: Miner's Ale, Suspicious Brew, Elixir of Undying, Death Potion
  - **기타**: Unstable Powder, Scroll of Returning

- **몹/보스**: 없음 (바닐라 몹 활용, 커스텀 전리품 부여)

- **구조물** (9개):
  | 구조물 | 바이옴 | 설명 |
  |--------|--------|------|
  | Forbidden Castle | Ash Barrens | 최대 규모, 피글린 수비대 |
  | Sanctum | 다양한 바이옴 | 종교적 구조물 |
  | Infernal Altar | Volcanic Deltas | 제단 |
  | Ruined Lab | Toxic Heap | 폐연구소 |
  | Nether Reactor | Quartz Flats | 반응기 |
  | Abandoned Tower | 다양한 바이옴 | 버려진 탑 |
  | Quartz Kitchen | Quartz Flats | 소형 건물 |
  | Piglin Village | 다양한 바이옴 | 피글린 마을 |
  | Pipeline | Infernal Dunes | 파이프라인 |

- **바이옴** (9개):
  1. Ash Barrens — 재로 뒤덮인 황무지
  2. Infernal Dunes — 지옥 사막
  3. Inverted Forest — 거꾸로 된 숲
  4. Quartz Flats — 석영 평원
  5. Toxic Heap — 독성 폐기물 지대
  6. Volcanic Deltas — 화산 삼각주
  7. Weeping Valley — 울음의 계곡
  8. Withered Forest — 시든 숲
  9. (바닐라 바이옴 변형 포함)

- **시스템/메카닉**: 없음 (순수 월드젠 + 전리품 데이터팩)

### 성능 영향
- **낮음~중간**. 이유:
  - 데이터팩이므로 모드 대비 가벼움
  - 네더 지형 생성이 복잡해짐 → 네더 최초 진입/탐험 시 청크 생성 지연
  - 구조물 내 몹 밀집도가 높으면 TPS 영향

### 다른 모드와 중복
- **없음** (네더 전용 모드). 현재 설치 목록에 네더 개편 모드가 없으므로 직접적 중복 없음.
- Terralith과는 차원이 다르므로 충돌 없음 (Terralith=오버월드, Incendium=네더)
- 참고: Terralith, Incendium, Nullscape는 모두 Stardust Labs 제작으로 상호 완벽 호환.

### 제거 시 영향
- **중간~높음**.
  - 네더의 커스텀 바이옴이 바닐라 바이옴으로 대체 → 이미 생성된 청크와 새 청크 사이 경계에 급격한 지형 단절
  - 커스텀 무기/방어구/포션은 커스텀 모델 데이터(CustomModelData NBT)로 구현 → 제거 시 일반 아이템 외형으로 변경되지만 사라지지는 않음
  - 구조물 자체는 바닐라 블록이라 유지
  - 네더 리셋 없이 제거하면 바이옴 경계 문제 지속

---

## 8. Nullscape (널스케이프)

**한줄 요약**: 엔드 차원의 지형을 384블록 높이로 확장하고 3개 신규 바이옴을 추가하는 데이터팩.

### 추가 콘텐츠 상세
- **블록**: 없음 (바닐라 블록만 사용)
- **아이템/무기/방어구**: 없음
- **몹/보스**: 없음
- **구조물**: 없음 (지형 생성만 변경)
- **바이옴** (3개 신규):
  1. **Crystal Peaks** — 수정 봉우리 지형
  2. **Shadowlands** — 그림자 평원
  3. **Void Barrens** — 공허 황무지

  바닐라 엔드 바이옴도 지형 개선:
  - 메인 아일랜드: 웜홀 형태로 재설계
  - 산악/고원 지형, 균열 패턴, 파도 패턴
  - 운석 필드, 보텍 힙(글로우스톤 번개 지형)
  - 코러스 숲 구역

- **시스템/메카닉**: 없음

### 성능 영향
- **낮음~중간**. 이유:
  - 높이 384블록으로 확장 → 청크당 메모리 사용량 증가
  - 1.18+ 노이즈 기반 지형 생성 활용이므로 효율적이나, 복잡한 지형일수록 청크 생성 시간 증가
  - 엔드 자체가 자주 방문하지 않는 차원이므로 실질적 영향은 낮음

### 다른 모드와 중복
- **없음**. 현재 설치 목록에 엔드 개편 모드 없음.
- Terralith(오버월드)/Incendium(네더)과 같은 Stardust Labs 제작 → 완벽 호환.

### 제거 시 영향
- **중간**.
  - 엔드의 높이가 384 → 256으로 축소되면서 높은 곳에 있던 블록/구조물이 잘릴 수 있음
  - 커스텀 바이옴이 바닐라로 대체 → 바이옴 경계 단절
  - 이미 생성된 청크의 지형 자체는 유지되나, 새 청크와의 연결부에서 급격한 지형 차이
  - 엔드 리셋 없이 제거하면 시각적으로 불쾌한 청크 경계 발생

---

## 9. Many More Ores and Crafts (더 많은 광석과 제작)

**한줄 요약**: 14종 신규 광석과 각 광석별 검/방어구/도구/블록 레시피 추가.

### 추가 콘텐츠 상세
- **블록**:
  - 광석 블록 14종 (각 오버월드/네더 변형)
  - 금속 블록 14종 (Tin Block, Lead Block, Silver Block 등)
  - Deepslate 변형 광석

- **아이템/무기/방어구** (광석 14종 x 각 도구/무기/방어구 세트):

  | 광석 | 희귀도 | 생성 높이 | 도구/무기/방어구 |
  |------|--------|----------|----------------|
  | Tin (주석) | 흔함 | Y 0~256 | 풀 세트 |
  | Lead (납) | 흔함 | Y 0~112 | 풀 세트 |
  | Silver (은) | 흔함 | Y 0~64 | 풀 세트 |
  | Tungsten (텅스텐) | 흔함 | Y 0~64 | 풀 세트 |
  | Platinum (백금) | 비흔함 | Y 0~64 | 풀 세트 |
  | Infernal (지옥석) | 희귀 | 네더 Y 0~112 | 풀 세트 |
  | Cobalt (코발트) | 비흔함 | Y 0~32 | 풀 세트 |
  | Palladium (팔라듐) | 비흔함 | Y 0~32 | 풀 세트 |
  | Adamantite (아다만타이트) | 희귀 | Y -32~0 | 풀 세트 |
  | Orichalcum (오리칼쿰) | 희귀 | Y -32~0 | 풀 세트 |
  | Titanium (티타늄) | 에픽 | Y -64~-32 | 풀 세트 |
  | Mythril (미스릴) | 에픽 | Y -64~-32 | 풀 세트 |
  | Amethyst (자수정) | - | 지오드 | 풀 세트 |
  | Obsidian (흑요석) | - | 용암층 | 풀 세트 |

  - "풀 세트" = 검, 곡괭이, 도끼, 삽, 괭이, 투구, 흉갑, 각반, 부츠, 금속 블록
  - 총 아이템 수: 약 14 x 10 = **140개+**

- **몹/보스**: 없음
- **구조물**: 없음
- **바이옴**: 없음
- **시스템/메카닉**: 용광로 제련 레시피 (금속 블록 ↔ 잉곳 변환)

### 성능 영향
- **중간**. 이유:
  - 14종 광석이 모든 청크에 추가 생성 → 청크 생성 시 ore feature 14개 추가 실행
  - 월드 생성 시간 증가 (특히 탐험이 많은 서버)
  - REI(레시피 뷰어)에 140개+ 아이템 추가 → REI 로딩/검색 시 약간의 지연

### 다른 모드와 중복
- **TechReborn**: 직접적 충돌! TechReborn도 Tin, Lead, Silver, Platinum, Tungsten 등 동일 이름 광석 추가. 양쪽 광석이 별도로 생성되어 **광석 인플레이션** 발생.
- **Spectrum**: Spectrum의 커스텀 광석(Shimmerstone, Azurite 등)과 지하 광석 밀도 경쟁
- **deeperdarker**: 딥 다크 영역 광석과 Y -64 ~ -32 영역에서 겹침

### 제거 시 영향
- **높음**.
  - 14종 광석 블록이 전부 공기/에러 블록으로 변환 → 월드 곳곳에 구멍 발생
  - 모든 커스텀 도구/무기/방어구/금속 블록 소실
  - 플레이어 인벤토리의 해당 아이템 전부 소실
  - 광석 블록으로 건축한 경우 구조물 손상

---

## 10. Chipped (치핑)

**한줄 요약**: 바닐라 블록의 장식 변형 11,000개 이상을 추가하는 빌딩 특화 모드. 7종의 전용 워크벤치로 제작.

### 추가 콘텐츠 상세
- **블록** (11,000개+):
  - 유리 변형: 스테인드 글라스의 수십 가지 패턴 변형
  - 돌 변형: Stone, Cobblestone, Andesite, Diorite, Granite, Blackstone, Deepslate 등의 수십 가지 텍스처 변형
  - 나무 변형: 각 나무 종류별 수십 가지 패턴
  - 양모 변형: 16색 양모의 패턴 변형
  - 식물/버섯 변형: 꽃, 버섯류의 다양한 변형
  - 프리즈마린, 길트 블랙스톤, 콘크리트 변형
  - 연결 텍스처 지원 (Athena 라이브러리)

- **아이템/무기/방어구**: 없음

- **몹/보스**: 없음
- **구조물**: 없음
- **바이옴**: 없음

- **시스템/메카닉** — 전용 워크벤치 7종:
  | 워크벤치 | 용도 |
  |---------|------|
  | Botanist's Workbench | 식물, 꽃, 버섯 변형 |
  | Glassblower's Workbench | 유리 블록 변형 |
  | Carpenter's Workbench | 나무 블록 변형 |
  | Loomer's Workbench | 양모 블록 변형 |
  | Mason's Workbench | 돌 블록 변형 |
  | Alchemy Bench | 기타 블록 변형 |
  | Tinkering Table | 금속/기타 블록 변형 |

### 성능 영향
- **중간~높음**. 이유:
  - 11,000개 블록 등록 → 게임 초기 로딩 시간 크게 증가 (블록 모델/텍스처 로딩)
  - 클라이언트 메모리 사용량 증가 (수천 개의 텍스처 에셋)
  - REI에 11,000개 아이템 추가 → REI 검색/스크롤 시 프레임 저하
  - 연결 텍스처 시스템(Athena) 추가 렌더링 부하
  - 서버 TPS에는 큰 영향 없음 (장식 블록이라 tick 없음)

### 다른 모드와 중복
- **mcw 시리즈** (bridges/doors/furniture/fences/windows/roofs): 양쪽 모두 장식/빌딩 블록 추가. Chipped는 바닐라 블록 변형, mcw는 새로운 가구/건축 요소로 성격은 다르나 "빌딩 모드" 카테고리 중복
- **supplementaries**: 일부 장식 블록 카테고리 중복

### 제거 시 영향
- **매우 높음**.
  - 11,000개의 커스텀 블록 전부 소실 → 해당 블록으로 건축한 모든 구조물에 대규모 구멍 발생
  - 워크벤치 7종 소실
  - **이미 Chipped 블록으로 건축을 했다면 복구 불가능**
  - 건축 서버에서는 제거 사실상 불가

---

## 11. Biomes O' Plenty / BOP (바이옴스 오 플렌티)

**한줄 요약**: 90개 이상의 신규 바이옴을 오버월드/네더에 추가하는 대표적 바이옴 모드. 커스텀 나무/꽃/블록 포함.

### 추가 콘텐츠 상세
- **블록** (수백 개):
  - 나무 세트 (각 나무별 원목/판자/계단/반블록/울타리/문/다락문/표지판/보트): Fir, Redwood, Cherry (→1.20 바닐라에도 추가됨), Mahogany, Jacaranda, Palm, Willow, Dead, Magic, Umbran, Hellbark, Empyreal
  - 꽃/식물: Lavender, Blue Hydrangea, Rose, Orange Cosmos, Pink Daffodil, Violet, Wildflower, Burning Blossom, Glowflower 등 20종+
  - 기타 블록: Dried Salt, Flesh, Brimstone, Rose Quartz Block, Toadstool, Glowshroom, Spanish Moss, Willow Vine 등

- **아이템/무기/방어구**:
  - Music Disc (커스텀 음악 디스크)
  - 보트/표지판 등 나무 파생 아이템
  - 무기/방어구 없음

- **몹/보스**: 없음
- **구조물**: 없음 (바이옴 전용 지형/수목 생성만)

- **바이옴** (90개+):

  **오버월드 주요 바이옴**:
  Alps, Auroral Garden, Bamboo Grove (→1.20 바닐라), Bayou, Bog, Boreal Forest, Cherry Blossom Grove, Clover Patch, Cold Desert, Coniferous Forest, Crag, Dead Forest, Dryland, Dune Beach, Erupting Inferno, Fir Clearing, Field, Floodplain, Flower Meadow, Forested Field, Fungal Jungle, Glowing Grotto, Grassland, Grove, Highland, Highland Moor, Hot Springs, Jade Cliffs, Jacaranda Glade, Lavender Field, Lush Desert, Lush Savanna, Maple Woods, Marsh, Meadow, Mediterranean Forest, Moor, Muskeg, Mystic Grove, Old Growth Dead Forest, Old Growth Woodland, Ominous Woods, Orchard, Origin Valley, Overgrown Greens, Pasture, Prairie, Pumpkin Patch, Rainforest, Redwood Forest, Rocky Rainforest, Rocky Shrubland, Scrubland, Seasonal Forest, Seasonal Orchard, Shrubland, Snowy Coniferous Forest, Snowy Fir Clearing, Snowy Maple Woods, Spider Nest, Tropics, Tundra, Volcanic Plains, Volcano, Wasteland, Wetland, Wintry Origin Valley, Woodland

  **네더 바이옴**:
  Corrupted Sands, Fungi Forest, Phantasmagoric Inferno, Polar Chasm, Undergarden, Visceral Heap

- **시스템/메카닉**: 없음 (순수 월드젠 모드)

### 성능 영향
- **중간**. 이유:
  - 90개+ 바이옴 추가 → 바이옴 배치 연산 증가로 청크 생성 시간 증가
  - 커스텀 나무 생성(특히 Redwood 거대 나무)이 구조물 생성처럼 비용이 큼
  - 커스텀 블록 텍스처 로딩으로 클라이언트 메모리 증가
  - 네더에도 바이옴 추가 → 네더 청크 생성 부하 증가

### 다른 모드와 중복
- **Terralith**: **직접적 중복!** 양쪽 모두 오버월드 바이옴 대량 추가. 동시 사용 시:
  - 바이옴이 극도로 작아짐 (바이옴 슬롯 경쟁)
  - 서버에서 Terralith 바이옴만 나오는 버그 보고 있음
  - 공식적으로 호환되지만 "하나만 사용 권장"
- **Incendium** (설치 검토 중): 네더 바이옴 중복 (BOP 네더 6개 + Incendium 9개)
- **deeperdarker**: 지하 바이옴 영역에서 간접적 상호작용

### 제거 시 영향
- **매우 높음**.
  - 모든 커스텀 바이옴이 바닐라 바이옴으로 재매핑 → 기존 월드 전역에서 바이옴 색상/날씨/몹 스폰 변경
  - 커스텀 나무 블록(Fir, Redwood, Jacaranda 등)이 전부 소실 → 숲 지역 대규모 구멍
  - 커스텀 꽃/식물 블록 소실
  - 이미 탐험한 영역과 새 영역의 바이옴 불일치로 지형 경계 단절
  - **Terralith과 함께 사용 중이라면 제거 시 Terralith 바이옴만 남아 실질적 영향 감소될 수 있음**

---

## 12. Player Finder vs Better Player Locator Bar (비교)

### Player Finder (플레이어 파인더)

**한줄 요약**: `/findplayer` 명령어로 다른 플레이어의 좌표를 확인하는 서버사이드 유틸리티 모드.

- **타입**: 서버사이드 (클라이언트 설치 불필요, LAN 사용 시에만 클라 필요)
- **기능**:
  - `/findplayer <이름>` 명령어로 대상 플레이어의 XYZ 좌표 표시
  - 플레이어 이름 자동완성 드롭다운
  - 권한 시스템 연동 (LuckPerms 등으로 사용 제한 가능)
- **블록/아이템**: 없음
- **UI**: 없음 (채팅 출력만)
- **설정 옵션**: 최소 (명령어 권한 정도)

### Better Player Locator Bar / BPLB (베터 플레이어 로케이터 바)

**한줄 요약**: 화면 상단 HUD 바에 다른 플레이어의 방향과 거리를 실시간 표시하는 클라이언트 모드.

- **타입**: 클라이언트사이드 (서버 설치 불필요)
- **기능**:
  - XP 바 위에 플레이어 위치 표시 바 렌더링
  - 플레이어 스킨 아이콘으로 방향 표시
  - 높이 차이 표시 (위/아래 화살표)
  - 거리 기반 투명도 (100블록에서 페이드 시작, 5000블록에서 거의 투명)
  - 같은 차원에 있는 플레이어만 표시
- **블록/아이템**: 없음
- **UI**: HUD 오버레이 바
- **설정 옵션**: 아이콘 커스터마이즈, 테두리, 페이드 거리, 표시 토글

### 비교표

| 항목 | Player Finder | Better Player Locator Bar |
|------|--------------|--------------------------|
| 사이드 | 서버 | 클라이언트 |
| 위치 확인 방식 | 명령어 (정확한 좌표) | HUD 바 (방향 + 대략적 거리) |
| 실시간 | 아니오 (수동 조회) | 예 (항상 표시) |
| 상세도 | 정확한 XYZ | 방향 + 거리 투명도 |
| PvP 영향 | 높음 (정확한 좌표 노출) | 중간 (대략적 방향만) |
| 권한 제어 | 가능 (LuckPerms 연동) | 불가 (클라 모드) |
| 다른 차원 | 확인 가능 | 같은 차원만 |
| 성능 영향 | 없음 | 미미 (HUD 렌더링) |

### 다른 모드와 중복
- **xaerominimap**: Xaero's Minimap에 이미 다른 플레이어 위치를 미니맵에 표시하는 기능 있음 → BPLB와 기능 중복
- **xaeroworldmap**: 월드맵에서 플레이어 위치 확인 가능 → Player Finder와 유사 역할

### 제거 시 영향
- 양쪽 모두 **영향 없음**. 순수 유틸리티 모드로 월드 데이터 변경 없음.

### 추천
- **소규모 친목 서버**: Better Player Locator Bar (항상 표시, 직관적)
- **PvP/대규모 서버**: Player Finder + LuckPerms (권한 제어 가능)
- **이미 Xaero's Minimap/Worldmap 사용 중**: 둘 다 불필요할 수 있음 (기존 모드로 충분)

---

## 종합 요약표

| 모드 | 콘텐츠 규모 | 성능 영향 | 기존 모드 중복 | 제거 위험도 |
|------|-----------|----------|--------------|-----------|
| LuckPerms | 없음 (유틸) | 최소 | 없음 | 없음 |
| Spectrum | 매우 큼 | 중~높 | TechReborn, deeperdarker | 심각 |
| AdditionalStructures | 중간 (250 구조물) | 낮~중 | Yungs, Explorify | 낮음 |
| When Dungeons Arise | 큼 (30+ 대형 구조물) | 중간 | Yungs, Explorify | 낮음 |
| IllagerInvasion | 중간 (11몹+아이템) | 중간 | friendsandfoes | 중간 |
| BOMD | 중간 (4보스+아이템) | 낮음 (전투 시 높음) | minecells | 중간 |
| Incendium | 큼 (9바이옴+25아이템) | 낮~중 | 없음 | 중~높 |
| Nullscape | 작음 (3바이옴) | 낮~중 | 없음 | 중간 |
| Many More Ores | 큼 (14광석x10) | 중간 | **TechReborn (심각)** | 높음 |
| Chipped | 매우 큼 (11000블록) | 중~높 | mcw 시리즈 (간접) | 매우 높음 |
| BiomesOPlenty | 매우 큼 (90+바이옴) | 중간 | **Terralith (심각)** | 매우 높음 |
| Player Finder | 없음 (유틸) | 없음 | Xaero's | 없음 |
| BPLB | 없음 (유틸) | 미미 | Xaero's Minimap | 없음 |

---

Sources:
- [LuckPerms 공식](https://luckperms.net/)
- [Spectrum - Modrinth](https://modrinth.com/mod/spectrum)
- [Spectrum Wiki - GitHub](https://github.com/DaFuqs/Spectrum/wiki)
- [AdditionalStructures - CurseForge](https://www.curseforge.com/minecraft/mc-mods/additional-structures-fabric)
- [When Dungeons Arise - CurseForge](https://www.curseforge.com/minecraft/mc-mods/when-dungeons-arise)
- [IllagerInvasion - CurseForge](https://www.curseforge.com/minecraft/mc-mods/illager-invasion)
- [Bosses of Mass Destruction - Modrinth](https://modrinth.com/mod/bosses-of-mass-destruction)
- [Incendium - Stardust Labs Wiki](https://stardustlabs.miraheze.org/wiki/Incendium)
- [Nullscape - Stardust Labs Wiki](https://stardustlabs.miraheze.org/wiki/Nullscape)
- [Many More Ores and Crafts - Modrinth](https://modrinth.com/mod/many-more-ores-and-crafts)
- [Chipped - CurseForge](https://www.curseforge.com/minecraft/mc-mods/chipped)
- [Biomes O' Plenty Wiki](https://biomesoplenty.fandom.com/wiki/Biomes_List)
- [Player Finder - Modrinth](https://modrinth.com/mod/playerfinder)
- [Better Player Locator Bar - CurseForge](https://www.curseforge.com/minecraft/mc-mods/better-player-locator-bar)
