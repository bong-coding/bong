---
# Leave the homepage title empty to use the site title
title:
date: 2024-10-05
type: landing

sections:
  - block: slider
    content:
      slides:
        - title: Thank you for visiting.
          content: I'm Bongmin Lee, an undergraduate student preparing to become a backend developer.
          align: center
          background:
            image:
              filename: backend.jpg
              filters:
                brightness: 1
            position: right
            color: '#000'
        - title: Hopefully project focus, not algorithm focus 💻
          content: I'm looking forward to creating many projects that utilize open source.
          align: left
          background:
            image:
              filename: na.jpg
              filters:
                brightness: 0.7
            position: center
            color: '#555'
        - title: If anyone else has the same idea, I'd love to hear from you.
          content: Press the button below and you'll be with me for life...
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
            text: Get in touch
            url: contact
    design:
      is_fullscreen: true
      slide_height: '400px'
      loop: true
      interval: 3000

  # - block: markdown
  #   id: section-1
  #   content:
  #     title: Greetings
  #     subtitle: Greetings
  #     text: |
  #       Hello, I'm Bongmin Lee, a student at Chonbuk National University. I am currently studying Spring Boot and networking, and my favorite language is C++. I apologize for not being able to upload the project code due to USB issue. I will upload them as soon as possible.
        

  # - block: hero
  #   content:
  #     title: |
  #       SpingBoot 
  #     image:
  #       filename: spring.png
  #     text: |
  #       Spring Boot is easy to set up with its auto-configuration features, easy to deploy with its built-in web server, and is well-suited for developing microservice architectures and supported by a large community.

  # - block: hero
  #   content:
  #     title: |
  #       C++ 
  #     image:
  #       filename: cpp.png
  #       align: left
  #     text: |
  #       C++ is a great language to write optimized programs because of its high performance and memory control.
          

  # - block: hero
  #   content:
  #     title: |
  #       SQL Developer
  #     image:
  #       filename: sql.png
  #     text: |
  #       SQL Developer is a database development tool provided by Oracle that makes it easy to work with SQL, PL/SQL. It provides the ability to run SQL queries, manage database objects, debugging features, and more, making it useful for database developers and administrators.

  # - block: collection
  #   content:
  #     title: blog
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
  #     page_type: blog
  #   design:
  #     view: card
  #     columns: '1' 
          

  # - block: collection
  #   content:
  #     title: Project
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
  #     page_type: pro
  #   design:
  #     view: community/custom_card
  #     columns: '1'
        
---
