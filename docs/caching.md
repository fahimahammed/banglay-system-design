# 🗃️ Caching (ক্যাশিং)

সিস্টেম ডিজাইনে **Caching** হলো দ্রুত ডেটা অ্যাক্সেস করার একটি পদ্ধতি, যেখানে আগের থেকে পাওয়া ডেটা একটি মাঝারি (Intermediate) জায়গায় সংরক্ষণ করা হয়, যাতে বারবার ডাটাবেজ বা সার্ভারকে হিট না করতে হয়।

---

## 🎯 কেন ক্যাশিং দরকার?

- ডেটাবেজ বা API এর ওপর লোড কমাতে
- দ্রুত রেসপন্স টাইম নিশ্চিত করতে
- ব্যান্ডউইথ সাশ্রয় করতে
- ইউজারের অভিজ্ঞতা উন্নত করতে

---

## 🧱 ক্যাশিংয়ের ধরন

### ১. Browser Cache

- ইউজারের ব্রাউজারে সংরক্ষিত ডেটা (images, CSS, JS)
- Static ফাইলের জন্য বেশি ব্যবহার হয়

### ২. CDN Cache

- Content Delivery Network (CDN) সার্ভারগুলো বিশ্বব্যাপী স্ট্যাটিক ফাইল ক্যাশ করে রাখে
- ইউজারের কাছাকাছি সার্ভার থেকে ডেটা দেয়

### ৩. Application Cache (In-Memory Cache)

- সার্ভারের মেমোরিতে ক্যাশ রাখা হয় (যেমন: Redis, Memcached)
- ডেটাবেজে লোড কমায়

### ৪. Database Cache

- DB এর frequently used query results ক্যাশ করা হয়
- Query performance বাড়ায়

---

## 🔄 Cache Invalidation (ক্যাশ রিফ্রেশ করা)

ক্যাশিংয়ের সবচেয়ে বড় চ্যালেঞ্জ হলো **ক্যাশ পুরনো হয়ে গেলে কিভাবে সেটি আপডেট করবেন?**

- Time-based expiration (TTL)
- Write-through cache (লেখার সময় ক্যাশ আপডেট)
- Cache-aside pattern (ডেটা রিকোয়েস্টে ক্যাশ চেক করা)

---

## 🛠️ জনপ্রিয় ক্যাশিং টুলস ও সার্ভিস

| টুল/সার্ভিস | বর্ণনা |
|-------------|---------|
| Redis       | In-memory ডেটাবেস, অনেক দ্রুত |
| Memcached   | Distributed memory caching system |
| Varnish     | HTTP accelerator, ওয়েব পেজ ক্যাশিংয়ের জন্য |
| Cloudflare CDN | গ্লোবাল CDN এবং ক্যাশিং সার্ভিস |

---

## 🖼️ ক্যাশিং এর কার্যপ্রণালী (সাধারণ উদাহরণ)

```
[Client Request] → [Cache] → [Data found?]
↓ Yes            ↓ No
\[Return Data] → \[Database] → \[Cache Update] → \[Return Data]

```

---

## 📌 কবে ক্যাশ করবেন?

- Frequently requested ডেটা
- Computationally expensive calculation
- Slow external API response

---

## 📎 পরবর্তী অধ্যায়:

👉 [Load Balancing (লোড ব্যালেন্সিং)](load-balancing.md)

---

## ✅ সারাংশ

- ক্যাশিং পারফরম্যান্স বাড়ায়, লেটেন্সি কমায়
- ক্যাশ মিস হলে ডেটাবেজ হিট হয়, তাই ক্যাশিং স্ট্রাটেজি গুরুত্বপূর্ণ
- ক্যাশ ইনভ্যালিডেশন একটা বড় চ্যালেঞ্জ

---

আপনি ক্যাশিং ভালোভাবে বুঝলে আপনার সিস্টেম অনেক দ্রুত ও স্কেলেবল হবে।

