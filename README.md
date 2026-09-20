# AICC
여성 의류 쇼핑몰 AI상담 어시스턴트
# AICC — 서버 상태 확인 API

Spring Boot로 만든 간단한 서버 상태 확인 API입니다. 서버 실행 후 `/health`에 접속하면 JSON 응답을 반환합니다.

## 실행 준비

* 프로젝트의 `pom.xml`에 지정된 Java 버전과 호환되는 JDK
* Eclipse 또는 Spring Tool Suite(STS)
* Git 또는 GitHub에서 다운로드한 프로젝트 소스

## 프로젝트 다운로드

```bash
git clone https://github.com/"깃허브이름"/AICC.git
cd AICC
```

Git이 없다면 GitHub의 **Code → Download ZIP**을 눌러 다운로드하고 압축을 해제합니다.

## 실행 방법

1. Eclipse 또는 STS를 실행합니다.
2. **File → Import → Maven → Existing Maven Projects**를 선택합니다.
3. `pom.xml`이 있는 폴더를 선택하고 **Finish**를 누릅니다.
4. 필요한 라이브러리가 다운로드될 때까지 기다립니다.
5. `src/main/java`에서 `@SpringBootApplication`과 `main()` 메서드가 있는 클래스를 찾습니다.
6. 해당 클래스를 우클릭하여 **Run As → Java Application**으로 실행합니다.

## 동작 확인

기본 포트가 8080인 경우, 서버 실행 후 브라우저에서 아래 주소로 접속합니다.

```text
http://localhost:8080/health
```

정상 응답:

```json
{"status":"ok"}
```

`localhost`는 실행한 사람 자신의 컴퓨터를 뜻합니다. 각자 프로젝트를 실행한 상태에서 접속해야 합니다.

## 오류 해결

* **Spring 관련 코드에 빨간 줄이 표시되는 경우:** 프로젝트 우클릭 → **Maven → Update Project**를 실행합니다. Spring Web 의존성이 포함되어 있는지도 확인합니다.
* **8080 포트가 이미 사용 중인 경우:** 해당 포트를 사용하는 서버를 종료하거나 `application.properties`에 `server.port=8081`을 설정하고 `http://localhost:8081/health`로 접속합니다.
* **접속이 안 되는 경우:** 서버가 정상적으로 실행 중인지 콘솔을 확인합니다.

> GitHub에 코드를 올리는 것만으로 서버가 실행되지는 않습니다. 공용 주소로 접속하려면 별도의 서버 배포가 필요합니다.
