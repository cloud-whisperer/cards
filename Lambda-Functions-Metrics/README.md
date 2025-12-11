# ⚡ AWS Lambda Summary  
### *Metrics • Duration • Memory • Cost Optimisation*  

---

## 🧩 **1. Key Lambda Metrics**
- ⏱️ **Duration** — Total time your function spends running.  
- 💾 **Memory Usage** — How much of the allocated memory your function actually uses.  
- 🔁 **Invocations** — How often the function is called.  
- ❌ **Errors** — Failures during execution.  
- 📉 **Throttles** — Concurrency limit reached; Lambda rejects additional requests.  
- 🧊 **Cold Starts** — Extra time required when Lambda initializes a new execution environment.  

---

## ⏱️ **2. Duration: What It Tells You**
- 🐢 Long durations = slower code, heavy dependencies, network delays.  
- 🔄 Spiky durations = cold-starts, retries, or external system problems.  
- 🎯 Duration drives cost — faster execution often means cheaper workloads.  
- 🔍 Duration anomalies reveal hidden loops, recursion, or inefficient libraries.  

---

## 💾 **3. Memory: How to Think About It**
- 🚀 More memory = more CPU → faster execution.  
- ✂️ Too little memory → slow performance, timeouts, higher cost.  
- 🧮 Optimal memory is *not* the smallest memory — it’s the tier where speed becomes efficient.  
- 📊 Watching “Max Memory Used” helps determine proper sizing.  

---

## 💰 **4. Cost Optimisation Essentials**
- ⚖️ **Balance memory and speed**:  
  Increase memory → reduce duration → lower total cost.  
- 🧹 Reduce dependencies to shrink cold-start time.  
- 🕸️ Cache libraries inside global scope.  
- 🌐 Minimise network calls (API, DB).  
- 🔁 Avoid self-invocation loops or infinite retries.  
- 🎯 Use *Provisioned Concurrency* only for predictable workloads.  
- 💤 Use *Reserved Concurrency* to prevent runaway costs.  

---

## 🧠 **5. Little-Known Expert Tips**
- 📐 **Memory–Duration Mapping** finds your exact sweet spot for cost & speed.  
- 🔎 **Look for duration sawtooth patterns** → GC pressure or inefficient buffers.  
- 🧊 **Avoid cold-start clusters** by warming functions or reducing package size.  
- 📉 **Use asynchronous invocations** for heavy workloads to reduce user-facing latency.  
- 🛰️ **Tune architecture** (SQS → Lambda, EventBridge → Lambda) to smooth concurrency spikes.  

---

## 🛠️ **6. Useful Tools**
- 📊 **CloudWatch Metrics** — durations, memory, concurrency.  
- 🕵️ **X-Ray** — traces, bottlenecks, external call delays.  
- 🔬 **Lambda Power Tuning** — memory-performance optimisation.  
- 🧮 **Cost Explorer** — cost visibility and per-function breakdown.  

---

## 🧾 **7. Quick Reference (Cheat Sheet)**
- ⏱️ **Fastest performance** = higher memory tier.  
- 💵 **Lowest cost** = point where duration drops but memory increase stabilises.  
- 🧊 **Cold-start sensitive apps** → keep package small + warm concurrently.  
- 🔁 **High-invocation apps** → ensure proper concurrency settings.  

---

