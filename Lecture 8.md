

# **Connection-Oriented Service**

A **connection-oriented service** is a type of communication where a **connection must be established first** before sending data.
Data is then sent in order, and the connection is closed after the communication is finished.

### **Key points:**

* First create a connection.
* Then send data.
* Data arrives **in sequence**.
* Good reliability.

### **Example:**

Telephone call, TCP.

---

# **Connectionless Service**

A **connectionless service** sends data **without creating any connection** beforehand.
Each packet is sent separately and may take different routes to reach the destination.

### **Key points:**

* No connection setup.
* Each packet is independent.
* Packets may arrive **out of order** or get lost.
* Faster and simpler.

### **Example:**

Postal mail, UDP, IP.

---

১. কানেকশনলেস (Connectionless) vs কানেকশন-ওরিয়েন্টেড (Connection-oriented) সার্ভিস

কানেকশন-ওরিয়েন্টেড → টেলিফোনের মতো
প্রথমে ফোন তুলে নাম্বার ডায়াল করতে হয় (কানেকশন তৈরি), কথা বলার পর ফোন রেখে দিতে হয় (কানেকশন ছেড়ে দিতে হয়)।
ডেটা পাঠানোর সময় একটা "পাইপ" তৈরি হয়। যে ক্রমে ডেটা পাঠানো হয়, ঠিক সেই ক্রমেই অন্য পাশে পৌঁছায়।
উদাহরণ: তুমি তোমার বন্ধুকে ফোন করলে → কানেকশন হল → কথা বললে → কথা শেষে লাইন কাটলে।
কানেকশনলেস → ডাকের মতো (চিঠি)
প্রতিটি প্যাকেটের সাথে পুরো ঠিকানা লেখা থাকে। একটা চিঠি পাঠালে আরেকটা চিঠি পাঠানোর জন্য আলাদা কিছু করতে হয় না। প্রতিটি প্যাকেট নিজে নিজে রাস্তা খুঁজে যায়।
উদাহরণ: তুমি ঢাকা থেকে চট্টগ্রামে ৫টা চিঠি পাঠালে → সব চিঠি আলাদা আলাদা পথে যেতে পারে, কোনটা আগে পৌঁছাবে বা হারিয়ে যাবে কিনা তার কোনো গ্যারান্টি নেই।

---

# **What is Datagram Network? (ডেটাগ্রাম নেটওয়ার্ক কী?)**

A **datagram network** sends each packet **independently**.
There is **no connection setup** before sending data.
Each packet can take **different routes** in the network.

### **Key Points (Simple):**

* **No connection** needed.
* Every packet travels **separately**.
* Packets can arrive **out of order**.
* Some packets may get **lost**.
* Very flexible.

### **Example:**

**Internet (IP network)**

---

# **What is Virtual-Circuit Network? (ভার্চুয়াল সার্কিট নেটওয়ার্ক কী?)**

A **virtual-circuit network** creates a **fixed path** before sending data.
After the path (circuit) is created, **all packets follow the same route**.

### **Key Points (Simple):**

* **Connection required first** (path setup).
* All packets follow the **same path**.
* Packets arrive **in order**.
* Faster forwarding (no new routing decision per packet).
* But less flexible.

### **Example:**

**ATM, Frame Relay, X.25**

---

# **Datagram vs Virtual Circuit (Super Simple Table)**

| বিষয়           | Datagram Network                  | Virtual-Circuit Network            |
| -------------- | --------------------------------- | ---------------------------------- |
| কানেকশন লাগে?  | না                                | হ্যাঁ, আগে পথ তৈরি হয়              |
| প্যাকেটের পথ   | প্রতিটি প্যাকেট আলাদা পথে যায়     | সব প্যাকেট একই পথে যায়             |
| ক্রম ঠিক থাকে? | না (out of order)                 | হ্যাঁ (in order)                   |
| সুবিধা         | রুট নষ্ট হলেও অন্য রুটে যেতে পারে | দ্রুত, স্থির রুট, কম decision      |
| অসুবিধা        | প্যাকেট হারাতে পারে               | একটি node নষ্ট হলে পুরো সংযোগ বন্ধ |
| উদাহরণ         | Internet                          | ATM, Frame Relay, X.25             |

---

# **Easy Real-Life Example**

### **Datagram → বাসের রাস্তায় যাওয়া**

* তুমি ঢাকা থেকে সিলেট যাবে।
* জ্যাম পেলে ড্রাইভার রাস্তা পরিবর্তন করতে পারে।
* প্রতিবার ভিন্ন রুট—same as datagram.

### **Virtual Circuit → ট্রেনের রেললাইন**

* ট্রেন **সবসময় একই লাইনে** চলে।
* আগে থেকে রুট সেট করা থাকে।
* same as virtual circuit.

---

### রাউটিং কী? (খুবই সহজ বাংলায়)

তোমার বাড়ি থেকে তোমার বন্ধুর বাড়িতে একটা চিঠি পাঠাতে চাও।  
মাঝে অনেক রাস্তা, মোড়, গলি আছে। চিঠি যেন ঠিকঠাক পৌঁছে যায়, তার জন্য কেউ কেউ সিদ্ধান্ত নেয় – “এই চিঠি এই রাস্তা দিয়ে যাবে”।  
এই সিদ্ধান্ত নেওয়ার পুরো প্রক্রিয়াটাই হলো **রাউটিং**।

নেটওয়ার্কে যখন তুমি কিছু পাঠাও (যেমন WhatsApp মেসেজ, YouTube ভিডিও), সেটা ছোট ছোট প্যাকেটে ভাগ হয়ে যায়। এই প্যাকেটগুলো তোমার ফোন/কম্পিউটার থেকে গন্তব্যে পৌঁছাতে মাঝে ১০-২০টা রাউটার পার হয়।  
প্রতিটি রাউটারের কাজই হলো দেখা – “এই প্যাকেটটা এখন কোন দিকে পাঠাবো যাতে তাড়াতাড়ি আর ঠিকঠাক পৌঁছে যায়?”

#### রাউটিং আর ফরওয়ার্ডিং এর তফাত (খুব সহজে)

- **রাউটিং** → ম্যাপ দেখে সিদ্ধান্ত নেওয়া  
  উদাহরণ: “ঢাকা থেকে সিলেট যাওয়ার সবচেয়ে ভালো রাস্তা কোনটা?” – এটা ঠিক করা।

- **ফরওয়ার্ডিং** → চিঠি হাতে হাতে দেওয়া  
  উদাহরণ: প্যাকেট এসেছে → রাউটার টেবিল চেক করে বলল, “এটা পরের রাউটারে পাঠাও” – এটা শুধু পাঠানো।

#### দুই রকমের নেটওয়ার্কে রাউটিং হয় ভিন্নভাবে

1. **ডেটাগ্রাম নেটওয়ার্ক** (যেমন: ইন্টারনেট)  
   → প্রতিটি প্যাকেট নিজে নিজে আসে।  
   → প্রতিবার রাউটার নতুন করে সিদ্ধান্ত নেয় কোন পথে পাঠাবে।  
   → রাস্তায় জ্যাম বা রাউটার নষ্ট হলে অন্য পথ বেছে নিতে পারে।

2. **ভার্চুয়াল সার্কিট নেটওয়ার্ক** (পুরনো টেলিফোনের মতো)  
   → শুরুতে একবার পুরো পথ ঠিক করে দেওয়া হয়।  
   → তারপর সব প্যাকেট সেই একই পথে চলে।  
   → মাঝে আর সিদ্ধান্ত নিতে হয় না।

#### রাউটিং এর লক্ষ্যগুলো কী? (সহজ ভাষায়)

1. **ঠিক পৌঁছাক** → প্যাকেট যেন হারিয়ে না যায় বা ভুল জায়গায় না যায়।
2. **সহজ হোক** → খুব জটিল হলে রাউটার ধীর হয়ে যায়।
3. **মজবুত হোক** → কোনো রাউটার নষ্ট হলেও পুরো ইন্টারনেট বন্ধ হয়ে যাবে না।
4. **স্থিতিশীল হোক** → হঠাৎ হঠাৎ পথ বদলাতে থাকলে সমস্যা হয়।
5. **সবাইকে সমান সুযোগ** → কেউ বেশি, কেউ কম পাবে না।
6. **দ্রুত ও ভালো হোক** → কম সময়ে বেশি প্যাকেট পৌঁছে যাক।

সার কথা:  
**রাউটিং মানে ইন্টারনেটের ট্রাফিক পুলিশ** – যে সিদ্ধান্ত নেয় তোমার মেসেজ, ভিডিও, ফাইল কোন রাস্তা দিয়ে সবচেয়ে ভালো যাবে। এই কাজটা না থাকলে ইন্টারনেট একদম চলবে না! 😊

---

# **What is Routing?**

Routing is the main function of the **Network Layer**.
It means **deciding the best path** for packets to travel from the **source machine** to the **destination machine**.

Since most networks are large, packets usually need to cross **many routers** (multiple hops) to reach their final destination.

### **Simple Definition:**

**Routing = Choosing the best path for a packet in a network.**

---

# **How Routing Works**

A **routing algorithm** decides:
➡️ *Which output line or which next router a packet should go to.*

### **If the network uses Datagrams:**

* Every packet is treated separately.
* A **new routing decision** is made for **each packet**.
* Because the best route may change over time.

### **If the network uses Virtual Circuits:**

* Routing decision is made **only once when the VC is created**.
* All packets follow the **same pre-planned route**.
* This is also called **Session Routing**.

---

# **Routing vs Forwarding (Simple Difference)**

Routing and forwarding are not the same.

### **Routing**

* **Making decisions** about which routes are best.
* **Updates the routing table**.
* Slow, done by the routing algorithm.

### **Forwarding**

* What the router does **when a packet arrives**.
* It **uses the routing table** to send the packet to the correct output line.
* Fast, done for each packet.

### **Think of it like:**

* **Routing = Planning the road map**
* **Forwarding = Using that map to send each car forward**

---

# **Goals of Routing**

### **1. Correctness**

Routing must be accurate.
Packets should reach the correct destination.

### **2. Simplicity**

Routing should be simple.
More complexity = more overhead and slower performance.

### **3. Robustness**

The network should work for years, even if:

* some routers fail
* traffic changes
* topology changes
  Routing algorithms must handle failures without shutting down the whole network.

### **4. Stability**

Routing must not oscillate or become unpredictable.
It should behave correctly under all conditions.

### **5. Fairness**

Every node should get a fair chance to send its packets.
Common rule: **First Come, First Serve (FCFS)**.

### **6. Optimality**

Routing should be:

* **Fast**
* **Produce high throughput**
* **Minimize delay**

There is a trade-off:
You cannot always get lowest delay and highest throughput at the same time.

---

### ইন্টার-ডোমেইন ও ইন্ট্রা-ডোমেইন রাউটিং – খুব সহজ বাংলায়

আজকাল ইন্টারনেটটা এতো বড় যে একটা মাত্র রাউটিং সিস্টেম দিয়ে পুরো পৃথিবীর সব রাউটারের টেবিল আপডেট করা সম্ভব না।  
তাই পুরো ইন্টারনেটকে ছোট ছোট “রাজ্য” বা “দেশ”-এ ভাগ করে দেওয়া হয়েছে। এই রাজ্যের নাম হলো **Autonomous System (AS)**।

#### Autonomous System (AS) কী?
- একটা AS মানে একটা বড় গ্রুপের নেটওয়ার্ক + রাউটার  
- যেগুলো একই কোম্পানি বা একই প্রশাসনের (administration) নিয়ন্ত্রণে থাকে।

উদাহরণ:
- বাংলালিংকের পুরো নেটওয়ার্ক = ১টা AS
- গ্রামীণফোনের পুরো নেটওয়ার্ক = আরেকটা AS
- BTCL-এর নেটওয়ার্ক = আরেকটা AS
- Google-এর নেটওয়ার্ক = আরেকটা AS
- Facebook-এর নেটওয়ার্ক = আরেকটা AS

#### দুই রকমের রাউটিং হয়

1. **ইন্ট্রা-ডোমেইন রাউটিং (Intra-Domain Routing)**  
   → একই AS-এর ভিতরে রাউটিং  
   → মানে একই কোম্পানির ভিতরে প্যাকেট কোন রাউটার দিয়ে যাবে  
   উদাহরণ: গ্রামীণফোনের ঢাকার একটা টাওয়ার থেকে চট্টগ্রামের একটা টাওয়ারে ডেটা পাঠানো।  
   এটা খুব দ্রুত আর স্মার্টভাবে হয় (প্রোটোকল: OSPF, IS-IS, RIP ইত্যাদি)

2. **ইন্টার-ডোমেইন রাউটিং (Inter-Domain Routing)**  
   → বিভিন্ন AS-এর মাঝে রাউটিং  
   → মানে এক কোম্পানির নেটওয়ার্ক থেকে আরেক কোম্পানির নেটওয়ার্কে প্যাকেট পাঠানো  
   উদাহরণ: তুমি গ্রামীণফোন দিয়ে Facebook খুললে → গ্রামীণফোনের AS থেকে Facebook-এর AS-এ যেতে হবে।  
   এটার জন্য ব্যবহার হয় **BGP** (Border Gateway Protocol) – এটাই পুরো ইন্টারনেটকে একসাথে জুড়ে রেখেছে।

সহজ উদাহরণ:  
ধরো তুমি ঢাকায় আছো, তোমার বন্ধু লন্ডনে।  
- ঢাকা শহরের ভিতরে যাওয়া = Intra-Domain  
- ঢাকা থেকে লন্ডন যাওয়া = Inter-Domain (দেশ থেকে দেশান্তর)

#### নন-অ্যাডাপটিভ ও অ্যাডাপটিভ রাউটিং (খুব সহজে)

1. **নন-অ্যাডাপটিভ (Static Routing)**  
   → আগে থেকে পথ ঠিক করে লিখে রাখা হয়  
   → রাউটার চালু করার সময় এই টেবিল লোড হয়  
   → রাস্তা খারাপ হয়ে গেলেও নিজে নিজে বদলাতে পারে না  
   উদাহরণ: ছোট অফিসে ২-৩টা রাউটার থাকলে ম্যানুয়ালি লিখে দেওয়া হয়।  
   সুবিধা: সহজ। অসুবিধা: রাউটার নষ্ট হলে পুরোপুরি বন্ধ!

2. **অ্যাডাপটিভ (Dynamic Routing)**  
   → রাউটার নিজে নিজে শিখে, বোঝে, পথ বদলায়  
   → কোন রাস্তায় জ্যাম বা রাউটার নষ্ট হলে অন্য পথ বেছে নেয়  
   → ইন্টারনেটে যেটা হয় এটাই  
   উদাহরণ: Google Maps-এ জ্যাম দেখে নতুন রাস্তা দেখায় – ঠিক সেই রকম!

সার কথা:  
- **Intra-Domain** = এক কোম্পানির ভিতরের GPS  
- **Inter-Domain** = দেশ থেকে দেশান্তরে যাওয়ার আন্তর্জাতিক GPS (BGP)  
- **Static** = আগে থেকে লেখা কাগজের ম্যাপ  
- **Dynamic** = Google Maps-এর মতো লাইভ আপডেট হওয়া ম্যাপ

Here is the **simplest and clearest English explanation** of **Inter-domain vs Intra-domain Routing** and **Adaptive vs Nonadaptive Routing**.

---

# **What is Intra-Domain and Inter-Domain Routing?**

Today’s internet is extremely large.
A **single routing protocol cannot manage the whole Internet**, so it is divided into smaller groups called **Autonomous Systems (AS).**

---

## **Autonomous System (AS)**

An AS is:

* A group of networks and routers
* Controlled by a **single organization** (ISP, university, company)

Examples:

* Grameenphone network = one AS
* Google network = one AS

---

# **Intra-Domain Routing**

**Routing inside an Autonomous System (AS).**

### **Simplified Meaning:**

Routing **within one organization** or one administrative domain.

### **Examples of Intra-domain protocols:**

* RIP
* OSPF
* EIGRP

---

# **Inter-Domain Routing**

**Routing between different Autonomous Systems (AS).**

### **Simplified Meaning:**

Routing **from one organization’s network to another organization’s network**.

### **Example of Inter-domain protocol:**

* BGP (Border Gateway Protocol)

---

# **Simple Table**

| Topic      | Intra-Domain Routing | Inter-Domain Routing    |
| ---------- | -------------------- | ----------------------- |
| Scope      | Inside one AS        | Between different ASes  |
| Control    | One administrator    | Multiple administrators |
| Examples   | RIP, OSPF            | BGP                     |
| Complexity | Lower                | Higher                  |

---

# **Nonadaptive vs Adaptive Routing Algorithms**

## **Nonadaptive Routing (Static Routing)**

* Routing decisions are **precomputed**.
* Routes do **not change**, even if the network fails or traffic changes.
* Routing tables are loaded **when the network starts**.
* Does **not respond** to congestion or link failure.

### **Key Idea:**

**Fixed routes. No reaction to real-time changes.**

### **Example:**

Static routing configured by a network admin.

---

## **Adaptive Routing (Dynamic Routing)**

* Routing decisions **change automatically** based on:

  * Network topology changes
  * Traffic load
  * Link failures
* Routers exchange information to update routes.

### **Key Idea:**

**Routes change according to network conditions.**

### **Examples:**

* OSPF
* RIP
* BGP
* EIGRP

---

# **Summary Table**

| Topic                       | Nonadaptive Routing | Adaptive Routing |
| --------------------------- | ------------------- | ---------------- |
| Other name                  | Static routing      | Dynamic routing  |
| Route changes?              | No                  | Yes              |
| Respond to failures?        | No                  | Yes              |
| Based on real-time traffic? | No                  | Yes              |
| Use in modern networks      | Rare                | Common           |

---

### শর্টেস্ট পাথ রাউটিং কী? (খুবই সহজ বাংলায় + উদাহরণ)

এটা হলো ইন্টারনেটের সবচেয়ে জনপ্রিয় রাউটিং পদ্ধতি।  
এর মূল আইডিয়া:  
**“যে পথে যেতে সবচেয়ে কম খরচ বা কম সময় লাগবে, সেই পথই বেছে নাও”**

#### নেটওয়ার্ককে কীভাবে ভাবা হয়?
নেটওয়ার্ককে একটা ম্যাপ বা গ্রাফ হিসেবে দেখা হয়:

- প্রতিটি রাউটার = একটা শহর (নোড)
- দুই রাউটারের মাঝের লাইন = রাস্তা (লিঙ্ক)
- প্রতিটি রাস্তার পাশে একটা সংখ্যা থাকে = খরচ (cost)  
  এই খরচ হতে পারে:
  - হপ সংখ্যা (কয়টা রাউটার পার হতে হবে)
  - দূরত্ব (কিলোমিটার)
  - ব্যান্ডউইথ
  - ডিলে (কত সেকেন্ড লাগে)

#### উদাহরণ দিয়ে বোঝা যাক (Dijkstra’s Algorithm)

ধরো এই নেটওয়ার্ক ম্যাপটা:

```
    A
   /  \  
  4    2
 /      \
B-------C
  1     5
   \   /
    3
     D
```

এখানে সংখ্যাগুলো হলো খরচ।  
প্রশ্ন: **A থেকে D যাওয়ার সবচেয়ে কম খরচের পথ কোনটা?**

Dijkstra’s অ্যালগরিদম ধাপে ধাপে এটা বের করে। দেখি কীভাবে:

| ধাপ | বর্তমান নোড | কী করি?                              | এখন পর্যন্ত দূরত্ব |
|-----|-------------|--------------------------------------|-------------------|
| ১   | A           | A কে ০ দূরত্ব দিলাম (নিজের থেকে নিজে) | A=0               |
| ২   | A           | A এর পাশের নোড দেখি: B=4, C=2         | A=0, C=2, B=4     |
| ৩   | C           | C সবচেয়ে কম → C কে চূড়ান্ত করলাম      | A=0, C=2 (চূড়ান্ত), B=4 |
| ৪   | C           | C এর পাশের নোড: D=2+5=7, B=2+?         | B এর পথ: A→B=4 বা A→C→B=? → ৪ই কম |
| ৫   | B           | B সবচেয়ে কম → B চূড়ান্ত               | A=0, C=2, B=4 (চূড়ান্ত) |
| ৬   | B           | B থেকে D = 4+3 = 7                     | D=7               |
| ৭   | D           | D চূড়ান্ত                              | সব শেষ             |

**ফলাফল: A → C → B → D (মোট খরচ = ২ + ? না, আসলে A→B→D = ৪+৩ = ৭)**  
আরেকটা পথ: A→C→D = ২+৫ = ৭ → দুটোই সমান।  
কিন্তু সবচেয়ে কম হলো ৭।

#### আরেকটা সহজ উদাহরণ (যেটা বইয়ে থাকে)

```
A ─1─ B ─1─ C
     ╱      ╲
    10       1
   ╱          ╲
F ──────────── E ─1─ D
```

প্রশ্ন: A থেকে D যাওয়ার সবচেয়ে কম পথ?

Dijkstra বলবে:  
A → B → C → E → D (খরচ = ১+১+১+১ = ৪)  
অন্য পথ A → F → E → D = অনেক বেশি  
তাই সবচেয়ে কম পথ: **A-B-C-E-D** (মোট ৪)

#### সার কথা (খুব সহজে)

শর্টেস্ট পাথ রাউটিং মানে:
“গুগল ম্যাপসের মতো – যে রাস্তায় সবচেয়ে কম সময় বা কম জ্যাম, সেই পথই দেখাবে”

ইন্টারনেটের বেশিরভাগ রাউটার (OSPF, IS-IS) এই Dijkstra’s অ্যালগরিদমই ব্যবহার করে।  
এজন্যই তুমি যখন YouTube খোলো, ডেটা সবচেয়ে ভালো আর দ্রুত পথ দিয়ে তোমার কাছে আসে।

আশা করি এখন পুরোপুরি ক্লিয়ার! 😊  
আরও উদাহরণ বা ছবি চাইলে বলো।

---

### ফ্লাডিং (Flooding) কী? – খুব সহজ বাংলায়

ফ্লাডিং হলো সবচেয়ে সোজা আর বোকা-বোকা রাউটিং পদ্ধতি।  
এর নিয়ম একটাই:

**যে প্যাকেটটা এসেছে, সেটা যেখান থেকে এসেছে শুধু সেই দিক ছাড়া – বাকি সব দিকে পাঠিয়ে দাও!**

উদাহরণ:  
ধরো তুমি একটা গ্রুপে WhatsApp-এ মেসেজ পাঠালে।  
ফ্লাডিং মানে – গ্রুপের প্রত্যেকটা মেম্বার নিজে থেকে সেই মেসেজ আরেকজনকে ফরওয়ার্ড করে দিচ্ছে (যাকে পেয়েছে তাকে ছাড়া)।  
ফলাফল? ১ মিনিটের মধ্যে সবাই একই মেসেজ ১০ বার পেয়ে গেল! 😂

#### ফ্লাডিং এর ভালো-মন্দ

| ভালো দিক                              | খারাপ দিক                                      |
|---------------------------------------|-----------------------------------------------|
| প্যাকেট ১০০% সব জায়গায় পৌঁছে যায়     | একই প্যাকেট বার বার আসে → নেটওয়ার্ক জ্যাম হয়ে যায় |
| কোনো রাউটার নষ্ট হলেও কাজ করে        | অনেক ব্যান্ডউইথ নষ্ট হয়                        |
| কোনো সেটআপ লাগে না                    | সাধারণ কাজে (YouTube, WhatsApp) ব্যবহার করা যায় না |
| সবচেয়ে দ্রুত পথ বের করে (সব পথ একসাথে চেক করে) |                                                |

#### কখন ফ্লাডিং কাজে লাগে? (বাস্তব উদাহরণ)

1. **সামরিক নেটওয়ার্ক বা যুদ্ধের মাঠে**  
   বোমা পড়ে অনেক রাউটার নষ্ট হয়ে গেলেও – যদি কোনো পথ থাকে, ফ্লাডিং দিয়ে মেসেজ পৌঁছে যাবে।

2. **ওয়্যারলেস নেটওয়ার্ক (Wi-Fi)**  
   তুমি Wi-Fi রাউটার থেকে একটা মেসেজ পাঠালে – তোমার ফোন, ল্যাপটপ, টিভি সবাই একসাথে পায়। এটাই আসলে ফ্লাডিং!

3. **গুরুত্বপূর্ণ ব্রডকাস্ট মেসেজ**  
   যেমন: “নেটওয়ার্কে নতুন রাউটার যোগ হয়েছে” – এই খবর সবাইকে জানাতে ফ্লাডিং ব্যবহার করা হয়।

4. **অন্যান্য রাউটিং অ্যালগরিদমের শিক্ষক**  
   ফ্লাডিং সবসময় সবচেয়ে কম সময়ে পৌঁছে দেয় (কারণ সব পথ একসাথে চেক করে)।  
   তাই অন্য অ্যালগরিদমগুলোকে ফ্লাডিং এর সাথে তুলনা করে দেখা হয় – “এটা কতটা ভালো?”

#### ফ্লাডিং কমানোর উপায় (যাতে পাগল না হয়ে যায়)

- প্রতিটি প্যাকেটে একটা **সিরিয়াল নাম্বার** দেওয়া হয়  
- রাউটার মনে রাখে – “এই নাম্বারের প্যাকেট আমি আগেও দেখেছি”  
- যদি আবার আসে → আর ফরওয়ার্ড করে না

এভাবে নেটওয়ার্ক “বন্যা” থেকে বাঁচে!

#### সার কথা (এক লাইনে)

ফ্লাডিং মানে – “যাকে পেয়েছি তাকে দিয়ে দাও” পদ্ধতি।  
খুব বোকা, খুব নোংরা, কিন্তু কিছু বিশেষ কাজে এর চেয়ে ভালো কিছু নেই!

যদি আরও মজার উদাহরণ বা ছবি চাও, বলো! 😄
