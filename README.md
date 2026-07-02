# RunTime-SCA
Runtime SCA 是一個只觀測、只讀取的 Runtime SBOM 探針。它會在一段觀測時間內捕捉主機上「實際被執行的 ELF 執行檔」與「實際被映射成可執行的共享函式庫」，再把這些檔案解析成作業系統套件或 standalone ELF，最後輸出 CycloneDX 1.7 JSON。  簡單說，它不是看「系統安裝了什麼」，而是看「程式執行時真的用到了什麼」。  Linux 版使用 eBPF，FreeBSD 版使用 DTrace。兩個版本的輸出格式一致，後續都可以交給 Grype、Trivy、Dependency-Track 或其他支援 CycloneDX 的工具處理。
