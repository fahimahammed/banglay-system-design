# 🧠 সিস্টেম ডিজাইনের মূল নীতিমালা (System Design Principles)

সিস্টেম ডিজাইন শেখার প্রথম ধাপ হলো কিছু মৌলিক ধারণা ও নীতিমালা বোঝা — যেগুলোর ওপর ভিত্তি করে বড় এবং জটিল সফটওয়্যার আর্কিটেকচার গঠন করা হয়।

এই ডকুমেন্টে আমরা আলোচনা করবো এমন কিছু গুরুত্বপূর্ণ প্রিন্সিপল যা যেকোনো সফল সিস্টেম ডিজাইনের ভিত্তি।

---

## ⚙️ ১. Scalability (স্কেলেবিলিটি)

**স্কেলেবিলিটি** মানে হলো একটি সিস্টেমের ক্ষমতা বাড়ানো — যাতে সে বেশি ইউজার, বেশি রিকোয়েস্ট বা বেশি ডেটা হ্যান্ডেল করতে পারে।

### ✳️ দুই ধরনের স্কেলিং:
- **Vertical Scaling** – একটি সার্ভারের ক্যাপাসিটি বাড়ানো (CPU, RAM বাড়ানো)
- **Horizontal Scaling** – একাধিক সার্ভার যোগ করে লোড ভাগ করা (Load Balancer দিয়ে)

---

## 🏃‍♂️ ২. Performance (পারফরম্যান্স)

পারফরম্যান্স ভালো মানে:
- দ্রুত রেসপন্স টাইম
- কম Latency
- Efficient Resource Usage

**কীভাবে বাড়ানো যায়?**
- Caching ব্যবহার করে
- Database Indexing
- Efficient Algorithms & Queuing

---

## 🔁 ৩. Reliability (রিলায়েবিলিটি)

একটি সিস্টেম সবসময় কাজ করবে — এমন নিশ্চয়তা থাকলে সেটি রিলায়েবল।

### 🧰 টুলস ও কৌশল:
- Replication
- Failover Systems
- Retry Mechanism
- Monitoring & Alerting

---

## 🧷 ৪. Availability (এভেইলেবিলিটি)

**Availability** মানে হলো, ইউজার যখনই চায়, তখনই সিস্টেম অ্যাক্সেসযোগ্য।

### ➕ High Availability অর্জনের উপায়:
- Redundant Systems
- Load Balancing
- Distributed Servers (Multiple Data Centers)

---

## 🛡️ ৫. Fault Tolerance (ফল্ট টলারেন্স)

সিস্টেমের কিছু অংশ ব্যর্থ হলেও বাকি অংশ যেন ঠিকঠাক কাজ করে — এই সক্ষমতাকে বলে Fault Tolerance।

🛠️ উদাহরণ:
- Circuit Breaker Pattern
- Graceful Degradation

---

## ⚖️ ৬. Consistency vs Availability (CAP Theorem)

> **CAP Theorem** বলে — একটি Distributed System একসাথে তিনটি বিষয় রাখতে পারে না: **Consistency**, **Availability**, এবং **Partition Tolerance**।

আপনাকে বেছে নিতে হয় দুটি:

| বেছে নিলে | মানে |
|-----------|------|
| CP | ডেটা সব জায়গায় এক থাকে, কিন্তু কিছু সময় সিস্টেম অ্যাক্সেস করা যায় না |
| AP | সিস্টেম সবসময় চলবে, কিন্তু ডেটা একটু দেরিতে সিঙ্ক হতে পারে |

---

## 🔐 ৭. Security (নিরাপত্তা)

একটি প্রোডাকশন সিস্টেমের জন্য সিকিউরিটি অত্যন্ত গুরুত্বপূর্ণ।

- Authentication & Authorization
- Data Encryption (in transit & at rest)
- Rate Limiting & Firewalls
- Input Validation (XSS, SQL Injection Prevention)

---

## 🧲 ৮. Maintainability & Modularity

সিস্টেম যেন ভবিষ্যতে সহজে পরিবর্তন, আপডেট বা debug করা যায় — সেজন্য ভালো design দরকার।

- Code should be modular
- Layered architecture
- Clear separation of concerns

---

## 📝 সংক্ষেপে মনে রাখার নিয়ম (S.P.R.A.F.C.S.M):

| অক্ষর | বিষয় |
|-------|------|
| S | Scalability |
| P | Performance |
| R | Reliability |
| A | Availability |
| F | Fault Tolerance |
| C | Consistency |
| S | Security |
| M | Maintainability |

---

## 🔗 পরবর্তী অধ্যায়:

👉 [Scalability কী এবং কেন গুরুত্বপূর্ণ?](scalability.md)

---

**নোট:** সব প্রিন্সিপল সব সিস্টেমে একসাথে প্রয়োগ করা যায় না। বাস্তব প্রজেক্টে ট্রেড-অফ করতে হয় — কোনটা বেশি জরুরি, সেটা বুঝে সিদ্ধান্ত নিতে হয়।

