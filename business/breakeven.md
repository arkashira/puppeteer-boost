# Breakeven Analysis – puppeteer‑boost  
*Prepared for: Axentx – Product Strategy & DevSecOps*  

---

## 1. Cost per Active User (USD / month)

| Component | Assumptions | Cost per user |
|-----------|-------------|---------------|
| **Compute** | 0.5 h of GPU‑enabled VM (t3.medium) per user, 720 h/month | **$0.50** |
| **Storage** | 1 GB of S3‑class storage per user | **$0.02** |
| **Bandwidth** | 5 GB egress per user | **$0.50** |
| **Total** | | **$1.02** |

> *All costs are based on AWS pricing (2026) and include 10 % margin for operational overhead.*

---

## 2. Pricing Tiers

| Tier | Price / mo | Core Features | Target Users |
|------|------------|---------------|--------------|
| **Basic** | **$10** | • 1 GB storage<br>• 20 GB bandwidth<br>• 2 concurrent scripts<br>• Community support | Developers, hobbyists |
| **Pro** | **$30** | • 10 GB storage<br>• 200 GB bandwidth<br>• 10 concurrent scripts<br>• Priority email support<br>• API access | Small teams, CI/CD |
| **Enterprise** | **$100** | • 1 TB storage<br>• 1 TB bandwidth<br>• Unlimited concurrency<br>• Dedicated account manager<br>• 99.9 % SLA | Large orgs, regulated environments |

*All tiers include 30 days of free trial.*

---

## 3. Customer Acquisition Cost (CAC)

| Channel | Avg. CAC |
|---------|----------|
| Paid Search + Social | **$250** |
| Partner Referrals | **$150** |
| Content Marketing | **$100** |

**Estimated CAC Range:** **$100 – $250** per new user (average $175).  
*Assumes 30‑day conversion cycle and 20 % churn in the first month.*

---

## 4. Lifetime Value (LTV)

| Tier | Avg. Monthly Revenue | Gross Margin | Avg. Tenure (mo) | LTV |
|------|----------------------|--------------|------------------|-----|
| Basic | $10 | 70 % | 12 | **$84** |
| Pro | $30 | 70 % | 12 | **$252** |
| Enterprise | $100 | 70 % | 12 | **$840** |

> *LTV = (Monthly Revenue × Gross Margin) × Avg. Tenure.*

---

## 5. Break‑Even User Count

### 5.1. Profit per User (after variable costs)

| Tier | Net Revenue / mo | Variable Cost / mo | Profit / mo |
|------|------------------|--------------------|-------------|
| Basic | $10 | $1.02 | **$8.98** |
| Pro | $30 | $1.02 | **$28.98** |
| Enterprise | $100 | $1.02 | **$98.98** |

### 5.2. Weighted Average (market mix)

Assuming 60 % Basic, 30 % Pro, 10 % Enterprise:

| Metric | Value |
|--------|-------|
| Avg. Price | $25 |
| Avg. Gross Margin | 70 % → $17.50 |
| Avg. Variable Cost | $1.02 |
| Avg. Profit | $16.48 |

### 5.3. Users Needed to Cover CAC

```
CAC_avg = $175
Profit_per_user = $16.48
Users_to_cover_CAC = 175 / 16.48 ≈ 10.6 → 11 users
```

### 5.4. Users Needed to Cover Fixed Overhead

Assuming fixed monthly overhead (dev ops, support, marketing) = **$5,000**:

```
Users_for_fixed = 5,000 / 16.48 ≈ 303 users
```

### 5.5. Total Break‑Even Users

```
Total = 303 (fixed) + 11 (CAC) ≈ 314 users
```

> *Thus, acquiring ~315 users (across tiers) will bring the business to break‑even.*

---

## 6. Path to $10 K MRR

| Tier | Users Needed | MRR Contribution |
|------|--------------|------------------|
| Basic | 10 000 / 10 = **1,000** | $10 000 |
| Pro | 10 000 / 30 = **334** | $10 020 |
| Enterprise | 10 000 / 100 = **100** | $10 000 |

**Recommended Mix (balanced risk):**

| Tier | Users | MRR |
|------|-------|-----|
| Basic | 400 | $4 000 |
| Pro | 300 | $9 000 |
| Enterprise | 100 | $10 000 |
| **Total** | **800** | **$23 000** |

*This mix delivers $10 K MRR with a diversified customer base, keeping churn risk low.*

---

## 7. Quick Takeaways

| Item | Value |
|------|-------|
| Variable cost per user | **$1.02** |
| Avg. profit per user | **$16.48** |
| Break‑even users | **≈ 315** |
| CAC range | **$100 – $250** |
| LTV (Basic) | **$84** |
| LTV (Pro) | **$252** |
| LTV (Enterprise) | **$840** |
| Path to $10 K MRR | **100 Enterprise** or **334 Pro** or **400 Basic** |

*These figures provide a clear roadmap for pricing, sales targets, and funding requirements.*