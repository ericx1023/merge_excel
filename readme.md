我要比較兩個不同日期的 CSV 文件，找出 CMAD 日期和計劃數量的變化，
並將這些變化記錄在新文件中

使用 Python、pandas 和 numpy 處理 CSV 文件的腳本。以下是主要功能的概述：

1. 導入必要的庫並定義文件名。

2. 讀取兩個 CSV 文件（前一個和下一個）並從檔名提取日期信息。

3. 處理 "前一個" 文件：
   - 將 'CMAD Date' 轉換為日期類型。
   - 找出最接近但不早於文件日期的 CMAD 日期。
   - 選擇具有該日期的所有行。

4. 對 "下一個" 文件執行相同的操作。


5. 創建一個字典，用於快速查找 "下一個" 文件中的數據。
5.5 複製前一個文件，寫入新的result.csv檔案
6. 在 result.csv 文件中添加新欄位 'Today CMAD Date' 和 'Today Scheduled Quantity'（如果不存在）
7. 遍歷 result.csv 文件的每一行：
   - 如果Sales Document 在 "下一個" 文件中存在：
     - 檢查 CMAD 日期是否有變化，如果有，更新 'Today CMAD Date'。
     - 檢查計劃數量是否有變化，如果有，更新 'Scheduled Quantity'。
   - 將更新後的數據寫回原始的 前一個CSV 文件。

8. 顯示有變化的行數。

