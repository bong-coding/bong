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
          content: 백엔드를 준비하고 있는 이봉민입니다.
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

  # - block: markdown
  #   id: section-1
  #   content:
  #     title: 인사말
  #     subtitle: 인사말
  #     text: |
  #       찾아주셔서 감사합니다. 백엔드를 희망하는 취준생 겸 학부생 이봉민입니다. 뭐 들어오신 이유는 저한테 관심이 있기에 사이트 방문을 한거라 생각이 드는데 천천히 둘러보십쇼
  
---
