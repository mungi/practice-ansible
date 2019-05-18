Ansible 실습 환경설정
=====================

### 1. VirtualBox 다운로드 및 설치

[Windows](https://download.virtualbox.org/virtualbox/6.0.4/VirtualBox-6.0.4-128413-Win.exe)  

[macOS](https://download.virtualbox.org/virtualbox/6.0.4/VirtualBox-6.0.4-128413-OSX.dmg)  
또는
> brew cask install virtualbox virtualbox-extension-pack  

[VirtualBox Extendtion Pack](https://download.virtualbox.org/virtualbox/6.0.4/Oracle_VM_VirtualBox_Extension_Pack-6.0.4.vbox-extpack)  

### 2. Vagrant 다운로드 및 설치

[Windows](https://releases.hashicorp.com/vagrant/2.2.4/vagrant_2.2.4_x86_64.msi)  
[Mac OSX](https://releases.hashicorp.com/vagrant/2.2.4/vagrant_2.2.4_x86_64.dmg)
[Red Hat](https://releases.hashicorp.com/vagrant/2.2.4/vagrant_2.2.4_i686.rpm)
[Ubuntu](https://releases.hashicorp.com/vagrant/2.2.4/vagrant_2.2.4_i686.deb)

### 3. Vagrant

#### 플러그인 설치  
> vagrant plugin install vagrant-hostmanager

#### Box 이미지 다운로드
> vagrant box add centos/7

#### Vagrant 파일
> cd  
> mkdir ansible  
[Vagrantfile](https://raw.githubusercontent.com/c1t1d0s7/cccr/master/Ansible-Vagrantfile)  
> 파일 받아서 Vagrantfile로 저장  

### 4. Vagrant 사용법

상태확인  
> vagrant status [VM]    

시작  
> vagrant up [VM]  

일시중지  
> vagrant suspend [VM]  

재개  
> vagrant resume [VM]  

중지  
> vagrant halt [VM]  

삭제  
> vagrant destroy [VM]  

SSH 연결
> vagrant ssh [VM]  

스냅샷 확인  
> vagrant snapshot list [VM]  

스냅샷 생성
> vagrant snapshot save [VM]  <SNAP-NAME>  

스냅샷 복구
> vagrant snapshot restore [VM]  <SNAP-NAME>  

공유폴더 동기화
- 공유폴더 동기화는 Vagrantfile이 있는 현재 디렉토리와 VM의 /vagrant 파일이 기본 동기화 됨
- 공유폴더 동기화가 되는 시점은 vagrant up 명령을 실행할 때만 동기화 됨
> vagrant rsync [VM]  

### 5. Playbook 작성을 위한 에디터 도구 팁

#### 1) vi/vim
vim-enhanced 패키지 필요  
.vimrc
> autocmd FileType yaml setlocal ts=2 sts=2 sw=2 expandtab

#### 2) Visual Studio Code
[VSCODE](https://code.visualstudio.com)  
또는
> brew cask install visual-studio-code
