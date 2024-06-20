---
title: CLI
description: CLI 레퍼런스 문서
tableOfContents:
  maxHeadingLevel: 5
---

Sonamu CLI는 Sonamu 프로젝트를 관리하기 위한 명령어를 제공합니다. 아래의 명령어를 사용하여 프로젝트를 관리할 수 있습니다.

<br/>

---

#### Fixture

##### `fixture init`

`Fixture` 및 테스트를 위한 데이터베이스를 초기화합니다. `SonamuDBConfig` 형식의 DB 연결 설정 중 `development_master`의 설정을 사용하여 `fixture_remote`, `fixture_local`, `test` 데이터베이스를 생성합니다.

##### `fixture import #entityId #recordIds`

`development` 데이터베이스에서 `#entityId`에 해당하는 테이블의 `#recordIds`에 해당하는 레코드를 `fixture_remote` 데이터베이스로 복사하고, `FixtureManager.sync()`를 실행하여 `fixture_local` 데이터베이스로 데이터를 복사합니다.

##### `fixture sync`

`FixtureManager.sync()`를 실행하여 `fixture_remote` 데이터베이스에서 `fixture_local` 데이터베이스로 데이터를 복사합니다.

<br/>

---

#### Migrate

##### `migrate run`

대기 상태의 마이그레이션이 있는 경우 먼저 실행합니다. 그런 다음 Entity 정의와 DB 스키마를 비교하여 마이그레이션 코드를 생성합니다.

##### `migrate check`

현재 Entity 정의와 DB 스키마를 비교하여 적용되지 않은 마이그레이션 코드를 확인합니다.

##### `migrate rollback`

적용된 마이그레이션을 롤백합니다. 롤백은 트랜잭션 단위로 수행됩니다.

##### `migrate reset`

마이그레이션 상태를 초기화합니다. 모든 마이그레이션을 롤백하고 마이그레이션 파일을 삭제합니다.

##### `migrate clear`

적용되지 않은 마이그레이션 파일을 삭제합니다.

<br/>

---

##### `ui`

Sonamu UI를 실행합니다.
