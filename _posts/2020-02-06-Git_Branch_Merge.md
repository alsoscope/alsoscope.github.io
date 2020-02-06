---
title: "MySQL Dump"
date: 2020-02-06 00:00:00 -0400
categories: jekyll update
---

### GitHub에서 Branch & Merge

브랜치 생성

    git branch portfolio

브랜치 이동하기

    git checkout portfolio

master 를 HEAD 로 가져온다. 실행은 master 노드에서.

    git checkout master

portfolio branch와 merge 한다

    git merge portfolio

오류

    `$ git push -u origin master
    To https://github.com/alsoscope/spring_web.git
     ! [rejected]        master -> master (fetch first)
    error: failed to push some refs to 'https://github.com/alsoscope/spring_web.git'
    hint: Updates were rejected because the remote contains work that you do
    hint: not have locally. This is usually caused by another repository pushing
    hint: to the same ref. You may want to first integrate the remote changes
    hint: (e.g., 'git pull ...') before pushing again.
    hint: See the 'Note about fast-forwards' in 'git push --help' for details.`

Fetch 가 아닌 Pull을 한다.<br>
pull은 내부적으로 fetch+merge 이다.

    git pull

    git add

    git commit -m ""

    git push -u origin master
