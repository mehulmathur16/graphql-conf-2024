class: center middle

.font-size-5[.tc-highlight[Scaling] GraphQL for 500,000,000 req/min]

GraphQL Conf 2024

---

# Who am I?

--

1. Founder of Tailcall

--

2. VP of Engineering at Dream11

--

3. Open Source Author and Maintainer

 <!-- TODO: add social icons -->

---

# Agenda

1. GraphQL Journey

2. Challenges & Workarounds

3. Learnings of the last 8 years

4. Applying learnings today

5. Key Takeaway

---

# .font-size-5.tc-highlight[\#TailcallHack]

Fastest Server Wins!

- TODO: Add QR Code

---

class: middle

# GraphQL Journey

## .font-grey[Section 1]

---

# .tc-highlight[2016] Dream11

.stat[

.stat-item[10 .title[Full Stack Engineers]]

.stat-item[100,000 .title[Concurrency]]

.stat-item[1,000,000 .title[Users]]

]

--
.block.center[ .font-size-5[💰 .weight-700.custom-underline[Series B]]st
--

- Android

- iOS

- PWA

- Microservices

- ## .block.center[ .font-size-5[🧐 .weight-700.custom-underline[GraphQL?]]st

# .tc-highlight[2024] Dream11

.stat[

.stat-item[500 .title[Engineers]]

.stat-item[10,000,000 .title[Concurrency]]

.stat-item[200,000,000 .title[Users]]

]

---

![Architecture](./img/architecture.svg)

- ## .block.center[ .font-size-5[🙌 .weight-700.custom-underline[GraphQL]]st

class: middle

# Challenges & Workarounds

## .font-grey[Section 2]

---

.font-size-3[
👉 .weight-700.custom-underline[Speculative Performance]
]

--

.font-size-3[🛠️] .font-grey[ Benchmarking Infrastructure]

---

.font-size-3[
👉 .weight-700.custom-underline[Highly Specialized]st
]

--

.font-size-3[🛠️] .font-grey[ Declarative Design]

---

.font-size-3[👉 .weight-700.custom-underline[Fragile]]

--

.font-size-3[🛠️] .font-grey[Processes & Testing Infrastructure]

---

.font-size-3[👉 .weight-700.custom-underline[Caching]]

--

.font-size-3[🛠️] .font-grey[On Services]

---

.font-size-3[👉 .weight-700.custom-underline[Resiliency]]

--

.font-size-3[🛠️] .font-grey[ Follow Traditions]

---

.font-size-3[👉 .weight-700.custom-underline[Maintenance]]

--

.block[.center[.font-size-6[🤷]]]

---

class: middle

# Learnings of 8 Years

## .font-grey[Section 3]

---

class:middle center

.font-size-3.weight-700[🕊️ Liberties Constraint and Constraints Liberate🕊️]

---

class:middle custom-background-image
background-image: url(./img/rush-hour.png)

--

.font-size-3.weight-500[🚦 Traffic Signal]

.font-size-3.weight-500[👮 Fine]

.font-size-3.weight-500[🛣 Marking]

---

class: middle
.block.half[![GraphQL Logo](img/graphql-logo-white.png)]
.two-columns[
.column[
.font-size-3[
.custom-underline[
🚧 .weight-500[Constraint]
]
]

- Schema

- Query

- Single Endpoint

- DSL
  ]
  .column[
  .font-size-3[
  .custom-underline[
  🕊️ .weight-500[Liberties]
  ]
  ]

- Type System

- Efficiency

- Unification

- Specialization
  ]
  ]

---

class: two-columns

.column[
.font-size-3[
.custom-underline[
🕊️ .weight-500[Liberties]
]
]

- Type System

- Efficiency

- Unification

- Specialization

]

.column[
.font-size-3[
.custom-underline[
🚧 .weight-500[Constraint]
]
]

- Learning Curve

- Complexity

- Reliability 🙅

- Interoperability 🙅

]

---

class: middle

.font-size-3[
📌 .weight-700.custom-underline[Two Pass Executor]st
]

---

class: middle

.font-size-3[
🙅‍♂️ .weight-700.custom-underline[Handwritten GraphQL]st
]

---

class: middle

.font-size-3[
🤔 .weight-700.custom-underline[Learn from SQL]st
]

---

class: middle

.font-size-3[
✋ .weight-700.custom-underline[Avoid Business Logic]st
]

---

class:middle

# Applying Learnings

## .font-grey[Section 4]

---

# 2020 .tc-highlight[Rewrite] GraphQL

1. High performance & reliability

2. Declarative, extendable & modular Design

3. Connect to any data-source

---

# 2021 .tc-highlight[Launch]

--

- Before `40,000` cores

--

- After `6,400` cores

--

.stat[

.stat-item[🚀 7x .title[Performance]]

.stat-item[💵 85% .title[Cost]]

.stat-item[💪 3 .title[Team]]

]

---

# 2022 .tc-highlight[Open Source]

Before open sourcing:

--

- ~~JS~~ to Rust

--

- ~~Declarative~~ to Configuration

---

class: flex-col flex-top

.logo[![Tailcall Logo](./img/taicall.svg)]

## 🚀 High Performance

## 🌍 General Purpose

## 👐 Apache 2.0

---

<!-- TODO: add a more Dream11 Example -->

### Your Schema

```graphql
schema {
  query: Query
}

type Query {
  posts: [Post]
}

type Post {
  id: ID
  title: String
  body: String
}
```

---

### Describe your .tc-highlight[resolvers]

```graphql
schema @upstream(baseURL: "https://api.d11.local") {
  query: Query
}

type Query {
  posts: [Post] @http(path: "/posts")
}

type Post {
  id: ID
  title: String
  body: String
}
```

--

### Start the server

```bash
tailcall start ./config.graphql
```

---

# Javascript

- TODO
- TODO

.js-code-screenshot[![JS Version](./img/js-graphql-server.png)]

---

class: middle

# How does it works?

---

# Initialization

<!-- TODO: add an excalidraw visual  -->

- Read the configuration

- Attach Resolvers

- Initialize HTTP Server

---

# Query Execution

![Query Engine](./img/query-engine.svg)

---

# Project

<!-- Github Repo -->
<!-- Contributors + Releases + Commits -->
<!-- Looking for Contributors and Feedback! -->

---

class: middle

# Summary

## .font-grey[Section 5]

---

## Summary

1. Innovation on GraphQL performance is necessary

2. A 2 pass executor is a key for performance and reliability

3. Handwritten GraphQL is difficult to maintain

4. Library authors should take inspiration from SQL engines

---

class: center flex-col

# Thank You!

.font-size-5[❤️]

<!-- Links to Runar's Talk  -->
<!-- Links to SQL Engine  -->
