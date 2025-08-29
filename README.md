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
<br />
Task 2: Manipulated Input for Multiple Records<br/>(輸入操控取得多筆紀錄) <br/>
<img src="https://i.imgur.com/mEu8Dnf.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Task 3: Extract Database Version<br/>(讀取資料庫版本) <br/>
<img src="https://i.imgur.com/DlyOOx7.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Task 4: Extract Database User<br/>(讀取資料庫使用者) <br/>
<img src="https://i.imgur.com/q5iRFJz.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Task 5: Identify Active Database<br/>(確認當前資料庫) <br/>
<img src="https://i.imgur.com/dZJcibk.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
  
<br />
Task 6: Enumerate Table Names<br/>(枚舉表格名稱) <br/>
<img src="https://i.imgur.com/vlCWr5J.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Task 7: Filter User-Related Tables<br/>(過濾使用者相關表格) <br/>
<img src="https://i.imgur.com/KwvK4HX.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Task 8: Enumerate Columns<br/>(枚舉欄位) <br/>
<img src="https://i.imgur.com/rTwtHs4.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Task 9: Data Exposure Demonstration<br/>(資料洩漏示範) <br/>
<img src="https://i.imgur.com/XdTuhdB.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
