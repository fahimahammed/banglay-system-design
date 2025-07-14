# 📈 Scalability (স্কেলেবিলিটি)

**Scalability** হলো একটি সিস্টেমের এমন ক্ষমতা, যা বাড়তে থাকা লোড (users, requests, data) মোকাবেলা করতে পারে — পারফরম্যান্স কম না দিয়ে।

> সহজভাবে: আপনি যদি ১০০ জন ইউজারের জন্য একটি অ্যাপ বানান, পরে সেটা ১০ লাখ ইউজার ব্যবহার করে — এবং অ্যাপটি ঠিকঠাক চলে — তাহলে সেটা স্কেলেবল।

---

## 🎯 Scalability কেন দরকার?

- ইউজার বাড়লে পারফরম্যান্স যেন ঠিক থাকে
- ব্যবসা বাড়ার সাথে সাথে সার্ভিসেও উন্নয়ন আসে
- লোড পিক টাইমে (e.g. sale, launch) সিস্টেম যেন ক্র্যাশ না করে
- ইন্টারভিউতে একটিই প্রশ্ন বারবার আসে: **“How would you scale this system?”**

---

## 🧱 Scalability এর ধরন

### 🔼 ১. Vertical Scaling (Scale Up)

একটি সার্ভারের হেডওয়ার শক্তি বাড়ানো (CPU, RAM, Disk)

**উদাহরণ:** ছোট VPS থেকে বড় Dedicated Server এ মুভ করা

✅ সুবিধা:
- ইমপ্লিমেন্ট করা সহজ
- একটিই সার্ভার মেইনটেইন করতে হয়

❌ সমস্যা:
- একটা সময়ের পরে সীমা আসে
- একটিই failure point থাকে

---

### ➕ ২. Horizontal Scaling (Scale Out)

অনেকগুলো সার্ভার একসাথে কাজ করায়। Load Balancer দিয়ে রিকোয়েস্ট ভাগ করা হয়।

**উদাহরণ:** Web Server A, B, C একসাথে চলছে behind a Load Balancer

✅ সুবিধা:
- Infinity scalability (in theory)
- Fault Tolerance বাড়ে

❌ সমস্যা:
- Design জটিল
- ডেটা সিঙ্ক করা বা কনসিসটেন্সি বজায় রাখা কঠিন

---

## 🧮 কী কী স্কেল করা যায়?

| বিষয় | স্কেলিং উপায় |
|------|--------------|
| Web Server | Horizontal via Load Balancer |
| Database | Read Replica, Sharding |
| Cache | Redis Cluster |
| File Storage | Object Storage (e.g., S3, GCS) |
| Background Jobs | Distributed Workers |

---

## 🖼️ স্কেলেবিলিটির উদাহরণ (দৃশ্যত)

```
             [Client]
                ↓
         [Load Balancer]
     ↓          ↓         ↓
[Server A] [Server B] [Server C] 
```

---

## 🔧 Scalability ডিজাইন করার সময় যা ভাবতে হয়

- কত ধরনের লোড আসবে (Traffic, Data Size, Concurrency)?
- কোন অংশগুলো Bottleneck হতে পারে?
- Latency কিভাবে কমানো যাবে?
- Stateless design করা যাবে কিনা?
- Scale করার সময় Security ও Cost কীভাবে handle হবে?

---

## 📌 কিছু ভালো Practice

- Stateless Server Design
- Async Processing (e.g., Queues)
- Use CDN for static content
- Database Read/Write Separation
- Auto-scaling infrastructure (Cloud)

---

## 📎 শিখুন আরও:

- [Load Balancing](load-balancing.md)
- [Database Design](database-design.md)
- [Caching](caching.md)

---

## ✅ সারাংশ:

| বিষয় | Scalability Tips |
|------|------------------|
| Web Layer | Horizontal Scaling + Load Balancer |
| App Logic | Stateless + Distributed |
| DB Layer | Sharding + Replication |
| Cache Layer | Redis/Memcached Cluster |
| File Storage | Cloud Object Storage |

---

আপনি যদি একটি scalable system ডিজাইন করতে পারেন, তাহলে আপনি একজন সত্যিকারের software architect হতে পারেন।
