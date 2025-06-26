# [week 5] SQL Injection Attack Walkthrough using DVWA

week 5 - 使用 DVWA 進行 SQL 注入攻擊演練

<h2>Outline 簡介</h2>
In this tutorial-based project from Week 5, I installed and configured Damn Vulnerable Web Application (DVWA) in a local virtual environment to simulate a real-world vulnerable web application. After setting the DVWA security level to low, I practiced fundamental and advanced SQL injection techniques.

在第五週的課程中，我實際安裝並操作了 DVWA（Damn Vulnerable Web Application），於本地虛擬機進行安全測試環境建置，並將安全等級調整為「low」，以便模擬常見的網頁應用程式漏洞: SQL Injection（SQL 注入）攻擊手法。

<h2>Objectives 目的</h2>

By modifying SQL query logic via crafted input values, I successfully (透過逐步實驗練習，學會如何)：
- <b>Bypassed authentication mechanisms (規避基本驗證機制)</b>
- <b>Retrieved database version, user, and structure information (查詢資料庫版本與使用者資訊)</b> 
- <b>Listed all tables and identified user-related data (搜索資料表與欄位名稱)</b> 
- <b>Extracted sensitive fields such as usernames and hashed passwords (讀取帳號與密碼等機敏欄位資訊)</b>


<h2>Materials and Methods 材料與方法</h2>
