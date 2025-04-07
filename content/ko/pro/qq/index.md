---
title: 팩맨 AI(진행중)
date: 2025-04-02
---
### https://github.com/bong-coding/pacman

# 팩맨 AI 에이전트를 구현하여 팩맨을 조종
**AI개념을 실제로 구현해보는데 중점을 둔 프로젝트**
---



## 💡 주요 학습 주제

### ✔️ Search (탐색 알고리즘)
- DFS / BFS / UCS / A*  
- 게임 트리 탐색 (Minimax, Alpha-Beta Pruning)

### ✔️ Markov Decision Processes (MDP)
- 가치 반복 (Value Iteration), 정책 반복 (Policy Iteration)

### ⏳ 확률 및 추론
- Bayes Rule, Hidden Markov Model (HMM), Particle Filtering

### ⏳ 강화학습 (Reinforcement Learning)
- Q-learning, Exploration vs Exploitation

### ⏳ 머신러닝 기초
- Naive Bayes, Perceptron, 간단한 Neural Network 소개

---

### 수행내용
| 프로젝트명 | 설명 |
|------------|------|
| **Project 1: Search** | 팩맨이 미로를 탐색하도록 DFS, BFS, UCS, A* 구현 |
| **Project 2: Multi-Agent** | Minimax, Expectimax, Alpha-Beta 등 전략 기반 에이전트 구현 |
| **Project 3: MDPs** | GridWorld 환경에서 가치 반복 및 정책 반복 구현 |
| **Project 4: Reinforcement Learning** | Q-learning 기반 학습형 에이전트 개발 |
| **Project 5: Classification** | Naive Bayes 및 Perceptron을 이용한 손글씨 분류기 |
| **Project 6 (Optional): Neural Nets** | 간단한 DNN을 통한 이미지 분류기 구현 (비공식 프로젝트) |

---
### 프로젝트 구조
```bash
.
├── pacman.py               # 메인 게임 실행 엔진
├── search.py               # DFS, BFS, UCS, A* 등의 알고리즘 구현
├── searchAgents.py         # 다양한 Search 기반 Agent 구현
├── game.py                 # 게임 로직 (에이전트, 환경 등)
├── ghostAgents.py          # 고스트 AI 로직
├── pacmanAgents.py         # 기본 Pacman 에이전트들 (GreedyAgent 등)
├── eightpuzzle.py          # 8 퍼즐 문제 구현 (검색 문제 예시)
├── layout.py               # 게임 맵 레이아웃 처리
├── graphicsDisplay.py      # 게임 GUI 렌더링
├── textDisplay.py          # CLI 텍스트 기반 렌더링
├── graphicsUtils.py        # 그래픽 유틸 함수 모음
├── util.py                 # 공통적으로 사용하는 유틸 자료구조들
├── projectParams.py        # 프로젝트 파라미터 설정
├── grading.py              # 자동 채점 로직
├── autograder.py           # 전체 자동 채점 스크립트
├── testClasses.py          # 테스트 케이스용 클래스
├── testParser.py           # 테스트 파일 파싱
└── searchTestClasses.py    # 검색 문제용 테스트 클래스
```
---

## 🛠️ 환경 및 요구사항

- Python 3.x
- Numpy
- 터미널/CLI 사용 경험
- (선택) VS Code 또는 PyCharm 등 Python IDE

---

### 실행방법

기본 게임 실행
```bash
python pacman.py
```
특정 레이아웃에서 실행
```bash
python pacman.py -l mediumClassic
```
특정 알고리즘 사용하는 에이전트 실행(EX: DFS)
```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=depthFirstSearch
```
A* 알고리즘 + 휴리스틱 사용
```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=aStarSearch,heuristic=manhattanHeuristic
```