---
# Leave the homepage title empty to use the site title
title:
date: 2024-10-05
type: landing

sections:
  - block: slider
    content:
      slides:
        - title: 찾아주셔서 감사합니다.
          content: 백엔드 개발자를 준비하는 학부생 이봉민입니다.
          align: center
          background:
            image:
              filename: backend.jpg
              filters:
                brightness: 1
            position: right
            color: '#000'
        - title: 알고리즘이 중점이 아닌 프로젝트 중점을 희망 💻
          content: 오픈소스를 잘 활용하여 많은 프로젝트들을 만들어 보고 싶습니다.
          align: left
          background:
            image:
              filename: na.jpg
              filters:
                brightness: 0.7
            position: center
            color: '#555'
        - title: 같은 생각을 갖고 계신분이 있다면 연락바랍니다.
          content: 아래 버튼을 누르면 평생 저와함께...
          align: right
          background:
            image:
              filename: call.jpg
              filters:
                brightness: 0.5
            position: center
            color: '#333'
          link:
            icon: phone
            icon_pack: fas
            text: 연락주세요
            url: contact
    design:
      is_fullscreen: true
      slide_height: '400px'
      loop: true
      interval: 3000

  - block: markdown
    id: section-1
    content:
      title: 인사말
      subtitle: 인사말
      text: |
        안녕하세요, 저는 전북대학교에 재학중인 이봉민입니다. 저는 현재 스프링부트와 네트워크에 대해서 공부를 하고 있는 중이며, 가장 자신있는 언어는 C++입니다. 현재 USB 이슈로 프로젝트 코드들을 업로드를 하지 못하여 사죄의 말씀을 드립니다. 최대한 빠른 시일 내에 업로드하겠습니다.

  - block: hero
    content:
      title: |
        SpingBoot 
      image:
        filename: spring.png
      text: |
        스프링부트는 자동 설정 기능으로 설정이 간편하고, 내장 웹 서버를 제공해 배포가 쉽습니다. 또한, 마이크로서비스 아키텍처 개발에 적합하며 대규모 커뮤니티의 지원을 받을 수 있습니다.

  - block: hero
    content:
      title: |
        C++ 
      image:
        filename: cpp.png
      text: |
        C++은 성능이 뛰어나며 메모리 제어가 가능해 최적화된 프로그램을 작성하기 좋은 언어입니다.  

  - block: hero
    content:
      title: |
        SQL Developer
      image:
        filename: sql.png
      text: |
        SQL Developer는 Oracle에서 제공하는 데이터베이스 개발 도구로, SQL, PL/SQL 작업을 쉽게 수행할 수 있도록 도와줍니다. SQL 쿼리 실행, 데이터베이스 객체 관리, 디버깅 기능 등을 제공하여 데이터베이스 개발자 및 관리자에게 유용한 기능을 제공합니다.

  - block: collection
    content:
      title: blog
      subtitle:
      text:
      count: 5
      filters:
        author: ''
        category: ''
        exclude_featured: false
        publication_type: ''
        tag: ''
      offset: 0
      order: desc
      page_type: blog
    design:
      view: card
      columns: '1'   
      
  - block: collection
    content:
      title: Project
      subtitle:
      text:
      count: 5
      filters:
        author: ''
        category: ''
        exclude_featured: false
        publication_type: ''
        tag: ''
      offset: 0
      order: desc
      page_type: pro
    design:
      view: community/custom_card
      columns: '1'    
      
       
---
