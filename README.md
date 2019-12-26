# Vue TIL 애플리케이션 Node.js 서버 코드

TIL 애플리케이션의 백엔드 API를 제공하는 Node.js 코드 리포지토리입니다.

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
# vi로 연 .bashrc 파일에 아래 내용을 추가하고 ":"를 입력한 다음 "wq"를 입력하여 저장 후 종료합니다.
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

추가 작성 필요

## License

MIT - CaptainPangyo