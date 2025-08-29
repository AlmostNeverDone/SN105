# SQL Injection Attack Walkthrough using DVWA

使用 DVWA 進行 SQL 注入攻擊演練

<h2>Outline 簡介</h2>

Hands-on exploration of SQL Injection using the Damn Vulnerable Web Application (DVWA) to understand input validation gaps, Boolean logic abuse, and UNION-based data enumeration—performed strictly in an isolated lab VM.

在受控的 DVWA 環境中動手實作 SQL 注入，理解輸入驗證缺口、布林邏輯繞過與以 UNION 進行資料枚舉；所有操作僅於隔離實驗用 VM 內完成。

<h2>Objectives 目的</h2>

By modifying SQL query logic via crafted input values, I successfully (透過逐步實驗練習，學會如何)：
* Bypassed authentication mechanisms (規避基本驗證機制)</b>
* Retrieved database version, user, and structure information (查詢資料庫版本與使用者資訊)</b> 
* Listed all tables and identified user-related data (搜索資料表與欄位名稱)</b> 
* Extracted sensitive fields such as usernames and hashed passwords (讀取帳號與密碼等機敏欄位資訊)</b>


<h2>Materials and Methods 材料與方法</h2>

[Environment]
* Linux Debian 12 VM with VirtualBox nested VMs (帶有 VirtualBox 嵌套虛擬機的 Linux Debian 12 虛擬機)</b> 
* UniSQ Student VM Portal (UniSQ 學生用 VM)</b>
* Damn Vulnerable Web Application [易受攻擊的 Web 應用程式 (DVWA)]</b>

*Safety note: DVWA is intentionally vulnerable; do not deploy on internet-facing hosts.
<br/>*安全提醒：DVWA 為刻意脆弱之系統，請勿對外公開部署。

[Tasks]
* Baseline Test(基線測試)</b>
* Manipulated Input for Multiple Records(輸入操控取得多筆紀錄)</b>
* Extract Database Version(讀取資料庫版本)</b>
* Extract Database User(讀取資料庫使用者)</b>
* Identify Active Database(確認當前資料庫)</b>
* Enumerate Table Names(枚舉表格名稱)</b>
* Filter User-Related Tables(過濾使用者相關表格)</b>
* Enumerate Columns(枚舉欄位)</b>
* Data Exposure Demonstration(資料洩漏示範)</b>


<h2>Practice 實踐</h2>

<p align="center">
Task 1: Baseline Test<br/>(基線測試) <br/>
<img src="https://i.imgur.com/InVX6Db.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Confirms that input directly affects the backend query.(確認輸入內容會直接參與後端查詢)</b>
<br/>
<br />
Task 2: Manipulated Input for Multiple Records<br/>(輸入操控取得多筆紀錄) <br/>
<img src="https://i.imgur.com/mEu8Dnf.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Indicates lack of input validation. (顯示後端查詢缺乏輸入驗證)</b>
<br/>
<br />
Task 3: Extract Database Version<br/>(讀取資料庫版本) <br/>
<img src="https://i.imgur.com/DlyOOx7.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Proves that system-level information can be exposed. (證實能以 UNION 技術讀取系統層級資訊)</b>
<br/>
<br />
Task 4: Extract Database User<br/>(讀取資料庫使用者) <br/>
<img src="https://i.imgur.com/q5iRFJz.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Reveals which account the application uses for DB access. (揭露應用程式連線所使用的 DB 帳號)</b>
<br/>
<br />
Task 5: Identify Active Database<br/>(確認當前資料庫) <br/>
<img src="https://i.imgur.com/dZJcibk.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Helps in structuring further enumeration. (協助後續資料庫結構探索)</b>
<br/> 
<br />
Task 6: Enumerate Table Names<br/>(枚舉表格名稱) <br/>
<img src="https://i.imgur.com/vlCWr5J.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Confirms metadata exposure. (證實中繼資料可被揭露)</b>
<br/>
<br />
Task 7: Filter User-Related Tables<br/>(過濾使用者相關表格) <br/>
<img src="https://i.imgur.com/KwvK4HX.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Pattern search identifies sensitive structures. (透過模式比對鎖定敏感表格)</b>
<br/>
<br />
Task 8: Enumerate Columns<br/>(枚舉欄位) <br/>
<img src="https://i.imgur.com/rTwtHs4.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Reveals schema design of target table. (揭露目標表格的欄位設計)</b>
<br/>
<br />
Task 9: Data Exposure Demonstration<br/>(資料洩漏示範) <br/>
<img src="https://i.imgur.com/XdTuhdB.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Confirms real-world risk of SQL Injection. (證實 SQLi 對敏感資料的實際危害)</b>
<br/>


<h2>Results 成果展示</h2>

Successfully demonstrated how SQL Injection can escalate from retrieving a single record to exposing complete database structures and sensitive user information in DVWA under Low Security settings. The project highlights both the technical risks of insecure coding practices and the importance of systematic defense measures such as input validation and parameterized queries.

本專題成功展示了 SQL 注入在 DVWA 低安全等級下，如何從單筆查詢逐步升級到完整資料庫結構與敏感使用者資料的洩漏。此實作凸顯了不安全編碼的技術風險，以及輸入驗證與參數化查詢等系統性防禦措施的重要性。


<h2>Reference 參考</h2>

[UniSQ] [CSC8520 - Securing Networks](https://handbook-guide.unisq.edu.au/course/2025/CSC8520)
