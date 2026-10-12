# India-Stocks-601-630-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 601 to 630)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-601-630-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (601 to 630)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 601 | `ALLDIGI` | Alldigi Tech Limited | `ALLDIGI.NS` |
| 602 | `ALLTIME` | All Time Plastics Limited | `ALLTIME.NS` |
| 603 | `ALMONDZ` | Almondz Global Securities Limited | `ALMONDZ.NS` |
| 604 | `ALOKINDS` | Alok Industries Limited | `ALOKINDS.NS` |
| 605 | `ALPA` | Alpa Laboratories Limited | `ALPA.NS` |
| 606 | `ALPHAGEO` | Alphageo (India) Limited | `ALPHAGEO.NS` |
| 607 | `ALPINETEX` | Alpine Texworld Limited | `ALPINETEX.NS` |
| 608 | `ALUFLUOR` | Alufluoride Limited | `ALUFLUOR.NS` |
| 609 | `AMAGI` | Amagi Media Labs Limited | `AMAGI.NS` |
| 610 | `AMAL` | Amal Limited | `AMAL.NS` |
| 611 | `AMANTA` | Amanta Healthcare Limited | `AMANTA.NS` |
| 612 | `AMARJOTHI` | Amarjothi Spinning Mills Limited | `AMARJOTHI.NS` |
| 613 | `AMBALALSA` | Ambalal Sarabhai Enterprises Limited | `AMBALALSA.NS` |
| 614 | `AMBICAAGAR` | Ambica Agarbathies & Aroma industries Limited | `AMBICAAGAR.NS` |
| 615 | `AMBIKCO` | Ambika Cotton Mills Limited | `AMBIKCO.NS` |
| 616 | `AMDIND` | AMD Industries Limited | `AMDIND.NS` |
| 617 | `AMJLAND` | Amj Land Holdings Limited | `AMJLAND.NS` |
| 618 | `AMNPLST` | Amines & Plasticizers Limited | `AMNPLST.NS` |
| 619 | `AMRUTANJAN` | Amrutanjan Health Care Limited | `AMRUTANJAN.NS` |
| 620 | `ANDHRAPAP` | ANDHRA PAPER LIMITED | `ANDHRAPAP.NS` |
| 621 | `ANDHRSUGAR` | The Andhra Sugars Limited | `ANDHRSUGAR.NS` |
| 622 | `ANDREWYU` | Andrew Yule & Company Limited | `ANDREWYU.NS` |
| 623 | `ANIKINDS` | Anik Industries Limited | `ANIKINDS.NS` |
| 624 | `ANKITMETAL` | Ankit Metal & Power Limited | `ANKITMETAL.NS` |
| 625 | `ANMOL` | Anmol India Limited | `ANMOL.NS` |
| 626 | `ANNAPURNA` | Annapurna Swadisht Limited | `ANNAPURNA.NS` |
| 627 | `ANNU` | Annu Projects Limited | `ANNU.NS` |
| 628 | `ANSALAPI` | Ansal Properties & Infrastructure Limited | `ANSALAPI.NS` |
| 629 | `ANSALBU` | Ansal Buildwell Limited | `ANSALBU.NS` |
| 630 | `ANTELOPUS` | Antelopus Selan Energy Limited | `ANTELOPUS.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream ALLDIGI 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-601-630-Historical-Data/main/ALLDIGI/1m/2026/10/ALLDIGI_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
