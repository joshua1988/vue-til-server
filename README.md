# Vue TIL 애플리케이션 Node.js 서버 코드


[인프런 Vue.js 끝장내기 강좌](https://www.inflearn.com/course/vue-js-%EB%81%9D%EB%82%B4%EA%B8%B0-%EC%BA%A1%ED%8B%B4%ED%8C%90%EA%B5%90) TIL 애플리케이션의 백엔드 API를 제공하는 Node.js 코드 리포지토리입니다.

## 개발 환경

- [Node.js 10.16](https://nodejs.org/en/download/releases/)

## NVM 설치 및 버전 변경 방법

이 리포지토리의 Node.js 소스는 버전 10.16과 호환됩니다.
로컬에 Node.js가 설치되어 있지 않은 분들은 위에서 안내한 링크로 다운로드 받습니다.

만약 이미 다른 버전의 Node.js를 사용하는 분들은 [NVM(Node Version Manager)](https://github.com/nvm-sh/nvm)을 이용하여 Node.js 버전을 맞춰주시면 됩니다.

### 설치 절차

1. VSCode의 내장 터미널을 `bash`로 실행하고 아래 명령어를 입력합니다.

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.2/install.sh | bash
```

2. 설치가 완료되면 터미널에서 아래 명령어로 `nvm` 명령어를 시스템 레벨에 추가합니다.

```bash
vi ~/.bashrc
```

```bash
# vi로 연 .bashrc 파일에 "i" 키를 입력하여 쓰기 모드로 진입합니다.
# 그리고 나서 아래 내용을 추가하고 ":"를 입력한 다음 "wq"를 입력하여 저장 후 종료합니다.
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

3. 이제 터미널에 `nvm` 명령어를 입력하면 인식이 되는지 확인합니다.
4. 인식되면 아래의 명령어로 Node.js를 설치합니다.

```bash
nvm install 10.16
```

5. 설치가 끝나면 아래의 명령어로 Node.js 버전을 변경합니다.

```bash
nvm use 10.16
```

6. 설치한 이후 아래 명령어로 Node.js 버전이 잘 설정되었는지 확인합니다.

```bash
node -v
```

## 서버 실행 절차

1. 로컬에 Node.js를 설치합니다.
2. 리포지토리를 클론한 다음 아래 명령어를 실행합니다.

```bash
# Node.js를 실행하기 위해 필요한 라이브러리를 설치하는 명령어
npm i
```

3. `package.json`에 정의되어 있는 실행 명령어를 입력합니다.

```bash
npm run start
```

4. 명령어 실행 창에서 아래와 같은 메시지가 떴는지 확인합니다.

![success-log](./images/success-log.png)

## API 문서 확인 절차

TIL 애플리케이션의 백엔드 API는 아래 주소에서 확인할 수 있습니다.

[http://localhost:3000/api/docs](http://localhost:3000/api/docs)

## Mongo Cloud 가입 절차

애플리케이션의 데이터는 몽고 DB에 저장합니다. 
실습 환경을 빠르게 구성하기 위해서 로컬에 몽고 DB를 설치하지 않고 몽고 DB 클라우드 서비스를 사용할게요.

[몽고 DB 클라우드 서비스 사이트](https://cloud.mongodb.com/)

1. 다음 링크로 몽고 DB 클라우드 서비스에 가입합니다. [가입 페이지](https://cloud.mongodb.com/user#/atlas/register/accountProfile)
2. 가입한 계정으로 로그인
3. 무료 인스턴스 생성. **꼭 Free Tier**를 선택하세요!
4. Database Access - 데이터베이스 접속을 위한 계정 생성. 예시) test/1234
5. Network Access - `ADD IP ADDRESS` 버튼 클릭 후 `ALLOW ACCESS FROM ANYWHERE` 버튼 클릭 또는 현재 IP만 화이트리스트로 등록
6. Clusters
   1. 메인 페이지의 `CONNECT` 버튼 클릭
   2. Connect Your Application 클릭
   3. `DRIVER`에 `Node.js` 선택
   4. `VERSION`에 `3.0 or later` 선택
   5. Connection String 복사 후 `app.js` 파일의 아래 부분에 붙여넣기

  ```js
  mongoose.connect('여기다가 붙여넣으세요.', {
    useNewUrlParser: true,
  });
  ```

7. Node.js 서버 재 실행 후 API 동작 여부 확인

## License

MIT - CaptainPangyo