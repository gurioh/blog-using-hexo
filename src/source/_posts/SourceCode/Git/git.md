---
title: Git 유용한 명령어
date: 2019-12-05 21:55:49
tags: git
categories:
 - [git]
---

#  Git ignore 리모트 적용방법
 > git rm -r --cached .
 git add .
 git commit -m "Apply .gitignore"



# Git Log

> git log --pretty=format:"%h - %an, %ar : %s" --since=1.weeks --committer Henry

Git 커밋 히스토리를 보는 방법이다.

> --pretty 옵션은 기본형식 외에 다양한 형식으로 화면에 출력해 준다.
> format  옵션을 pretty 옵션에 적용하면 커스텀하여 화면에 출력하는 것이 가능하다.

기타 옵션 사항은 
아래 링크에서 확인
https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%BB%A4%EB%B0%8B-%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%A1%B0%ED%9A%8C%ED%95%98%EA%B8%B0