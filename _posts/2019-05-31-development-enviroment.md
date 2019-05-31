---
title: Mac 개발환경
date: 2019-05-31 18:02:22 +900
category: Other
tag: development enviroment
---


# Homebrew 

Homebrew는 자유 오픈 소스 소프트웨어 패키지 관리 시스템으로 리눅스의 apt or yum과 비슷한 mac용 패키지 매니저로 소프트웨어 설치를 단순하게 만들어준다. 다양한 프로그램을 복잡한 빌드 과정 없이 설치하거나 삭제할 수 있고 업데이트나 관리도 간편하다.

### 설치
터미널에 다음을 입력한다.
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
  
[Homebrew](https://brew.sh/index_ko){: target="_blank"} / [brew 명령어](https://docs.brew.sh/Manpage.html){: target="_blank"}

# git

버전 관리 도구로 유명하다. macOS에는 기본적으로 설치되어 있으나 최신버전이 아니므로 업데이트 한다.
```
brew install git
```

## Git Large File Storage

용량이 큰 바이러니 파일을 git으로 관리하기 용이하다.
```
brew install git-lfs
```

### 설정
macOS에서 한글 파일명을 정상적으로 처리하기 위해 다음과 같이 설정해주어야 한다.

```
git config --global user.name "Your Name"
git config --global user.email "you@your-domain.com"
git config --global core.precomposeunicode true
git config --global core.quotepath false
```

# 터미널 설정

## iterm2

다양한 기능과 손쉽게 테마를 설정할 수 있어서 terminal보다 널리 사용된다.

### 설치 
```
brew cask install iterm2
```

### 테마 설정
[Snazzy.itermcolors](https://raw.githubusercontent.com/sindresorhus/iterm2-snazzy/master/Snazzy.itermcolors) 마우스 오른쪽 클릭으로 저장 후 더블클릭 하면 자동으로 추가된다.
  
설치 후 iterm2를 실행 후 설정 창(command+,)에서 profiles를 선택하고 colors 탭을 선택 한 후 오른쪽 하단에 있는 color presets 선택박스를 클릭하여 snazzy를 선택한다.

### 추가 설정
테마 어둡게  
    - Appearance > Theme: Dark  
스크롤바 감춤  
    - Appearance > Hide scrollbars 체크  
타이틀 바 밑에 1px 라인 제거  
    -Appearance > Show line under title bar when the tab bar is not visible 체크 안함  
마진 수정  
- Advanced > Height of top and bottom margins in terminal panes: 10  
- Advanced > Width of left and right margins in terminal panes: 12  

## zsh & oh-my-zsh
macOS는 기본으로 Bash(Bourne-again) shell을 사용한다. shell은 bash외에 csh, ksh, sh, tcsh, zsh등을 내장하고 있는데 대새는 zsh다.  
zsh에 설정 관리 프레임워크인 oh-my-zsh을 사용하여 예쁜 테마를 적용하고 다양한 플러그인을 설치할 수 있다.

### 설치
zsh를 최신으로 업데이트 하고 zsh-completions를 설치한다.
```
brew install zsh 
brew install zsh-completions
```
oh-my-zsh 설치
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
### 플러그인
명령어 하이라이팅 플러그인 zsh-syntax-highlighting  
자동완성 플러그인 zsh-autosuggestions
```
# zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# zsh-autosuggestions
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```
  
플러그인을 설치하면 반드시 ~/.zshrc 파일을 설정해 주어야 한다.  
파일을 열고 plugins 항목에 다음을 추가해준다.
```
plugins=(
  git
  zsh-syntax-highlighting   <<
  zsh-autosuggestions       <<
)
```

설정 후 터미널을 재시작 하거나 source ~/.zshrc 명령어를 실행해 설정을 다시 불러온다.

## 테마
다양한 테마가 존재하는데 테마를 바꾸는 방법은 ~/.zshrc파일의 ZSH_THEME="robbyrussell" 부분을 원하는 테마로 수정하면 된다.
  
여기서는 이쁘고 단순하고 빠른 pure prompt를 사용한다.

```
brew install nodejs # nodejs가 설치되어 있다면 skip
npm install --global pure-prompt
```
  
설치 후 ~/.zshrc에 다음 항목을 추가한다.(맨 밑에 추가)
```
autoload -U promptinit; promptinit
prompt pure
```

# vim


# Reference

[본격 macOS에 개발환경 구축하기](https://subicura.com/2017/11/22/mac-os-development-environment-setup.html){: target="_blank"}