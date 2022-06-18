> git에 push한 commit message 내용을 변경해야하는 문제 발생

## commit message 수정을 위한 'Rebase'

- 해당 commit으로 이동하고 commit메세지를 수정한 다음 해당 branch에 다시 merge하는 방식
- 새로운 branch 생성하는 것과 다른 점은 merge commit이 생성되는 것을 막고 깔끔하게 commit 메시지 자체만 남기는 것 가능
- git rebase -i HEAD~최근 commit log 중 불러올 커밋 갯수
  - git rebase -i HEAD~3
  - rebase 명령어와 -i를 함께 사용하면 rebase를 **대화형으로 수행하여** 여러 commit들의 순서를 바꾸거나 commit history 를 변경 또는 삭제 가능
- 출력된 commit 중 수정하고 싶은 commit의 pick을 'i'로 INSERT모드로 전환하여 reword로 수정하고
- COMMEAND 모드로 전환할 때는 ESC 키를 눌러 전환하고 :wq 작성하여 저장/종료함
- 수정할 commit message가 출력되고  수정후 :wq로 저장/종료 함
- 이미 원격에 올라간 commit message 수정을 위해 강제 푸쉬함
- git push --force 브랜치 이름
- 이 방법은 협업 시 다른 팀원의 local 저장소에  해당 commit log의 내용과 달라지므로 주의하여 사용해야 함