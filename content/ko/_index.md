---
# Leave the homepage title empty to use the site title
title:
date: 2022-10-24
type: landing

# sections:
#   - block: hero
#     content:
#       title: |
#         Wowchemy
#         Research Group
#       image:
#         filename: welcome.jpg
#       text: |
#         <br>
        
#         The **Wowchemy Research Group** has been a center of excellence for Artificial Intelligence research, teaching, and practice since its founding in 2016.
sections:
  - block: slider
    content:
      slides:
      - title: 봉의 개발일기
        content: 백엔드  개발자를 준비하는 학부생 이봉민입니다.
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
          url: ../contact/
    design:
      is_fullscreen: true
      slide_height: '400px'
      loop: true
      interval: 3000

  # - block: collection
  #   content:
  #     title: Latest News
  #     subtitle:
  #     text:
  #     count: 5
  #     filters:
  #       author: ''
  #       category: ''
  #       exclude_featured: false
  #       publication_type: ''
  #       tag: ''
  #     offset: 0
  #     order: desc
  #     page_type: post
  #   design:
  #     view: card
  #     columns: '1'
  
  # - block: markdown
  #   content:
  #     title:
  #     subtitle: ''
  #     text:
  #   design:
  #     columns: '1'
  #     background:
  #       image: 
  #         filename: coders.jpg
  #         filters:
  #           brightness: 1
  #         parallax: false
  #         position: center
  #         size: cover
  #         text_color_light: true
  #     spacing:
  #       padding: ['20px', '0', '20px', '0']
  #     css_class: fullscreen

  # - block: collection
  #   content:
  #     title: Latest Preprints
  #     text: ""
  #     count: 5
  #     filters:
  #       folders:
  #         - publication
  #       publication_type: 'article'
  #   design:
  #     view: citation
  #     columns: '1'

  # - block: markdown
  #   content:
  #     title:
  #     subtitle:
  #     text: |
  #       {{% cta cta_link="./people/" cta_text="Meet the team →" %}}
  #   design:
  #     columns: '1'
---
