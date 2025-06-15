# Git版本控制

練習設置:使用vscode先建立一個project檔案裡面裝有vr眼鏡的price、specs和systems的.md檔案。

- **git —version:**
    
    可以看到git的版本，表示成功安裝git。
    
    ![image](https://github.com/user-attachments/assets/42617296-c4b2-4556-ba33-6e8065cc48d0)
    
- **git config —global [user.name](http://user.name)(user.email) “zxc910529”(”zxc910529@gmail.com”)**
    
    記錄作者資訊，在””中。
    
- **git init**
    
    要把一個資料夾轉成具有git版本管理的儲存庫，會在當前目錄建立一個.git資料夾，儲存檔案變更的歷史，刪除掉的話備份紀錄會消失。
    
  ![image 1](https://github.com/user-attachments/assets/b91e4e86-2b46-4fbb-bf9c-541d523ad2d8)

- **clear**
    
    清除終端的內容，使乾淨一點。
    
- **git status**
    
    檢查當前目錄中的每個檔案狀態。
    
    未追蹤(Untracked):git不會去紀錄內容變更和編輯歷史。
    
    以追蹤:(Tracked):git可以去紀錄內容變更和編輯歷史。
    
    暫存(Staged)
    
    提交(Commited)
    
    ![image 2](https://github.com/user-attachments/assets/99eb91f9-59bd-4eca-8abf-295399c08a8b)
    
- **git add [price.md](http://price.md)     or git add .  →全部資料夾的檔案都追蹤放到暫存區裡**
    
    把price.md檔案加入追蹤，此時用git status可看到變成綠色表示已追蹤，準備提交。
    
    ![image 3](https://github.com/user-attachments/assets/395c8aea-668c-4320-82f3-a64e2bdf151c)
    
- **git commit -m “建立還原點”   (m為message縮寫)**
    
    每個commit(提交)都要附帶簡短的訊息
    
    ![image 4](https://github.com/user-attachments/assets/c9ce5b38-e113-49f3-bf88-731c132274aa)

**有修改被git追蹤的檔案的話，檔案右邊會顯示M表示有被修改，此時還是要經過git add和git commit -m "”提交**

- **git log  or  git log —oneline**
    
    列出提交(commit)的歷史，按q可取消。
    
    Head,Master:最新的存檔點和目前主要的任務。
    
    ![image 5](https://github.com/user-attachments/assets/e2f4a901-f097-4203-b05a-5085c2d5df94)
    
- **git diff a7c5cc0 (commit的編號) — [price.md](http://price.md) (也可打.看全部檔案)**
    
    比較新、舊版本的內容差異。
    
   ![image 6](https://github.com/user-attachments/assets/6b573023-5b4f-43e2-b59f-5a2ab7b1e1f1)

- **git checkout a7c5cc0 (commit的編號) price.md**
    
    此變動也需進行commit
    
  ![image 7](https://github.com/user-attachments/assets/12a4df53-89f7-4d24-b386-32e489fcdd08)
  
  ![image 8](https://github.com/user-attachments/assets/47ca70ea-1ec7-402e-a467-413621f6f2e7)

  ![image 9](https://github.com/user-attachments/assets/fc850eae-6910-4af9-8f83-30410566a79e)

- **git reset —hard a7c5cc0 (commit的編號)**
    
    將檔案還原到某個時間點並捨棄之後的儲存檔紀錄，此操作不可逆，有需要可做備份。
    
    ![image 10](https://github.com/user-attachments/assets/d0a5b478-06ea-4edc-8789-8a38c309d814)
    
- **刪除文件ex:刪除market.md**
    
    先加入market.md
    
    ![image 11](https://github.com/user-attachments/assets/bac3d916-0bcb-4b9f-ba2d-0273f52192e9)

    刪除後看status會發現此檔案是未暫存的變更。
    
    ![image 12](https://github.com/user-attachments/assets/99404d2d-d23a-495d-8d4e-e7dc0fe19d88)
    
    需使用git add再加入到暫存區，因為git是追蹤檔案的變化而不是檔案本身，因此刪除檔案的動作也要追蹤
    
    ![image 13](https://github.com/user-attachments/assets/49b836cf-3a1f-4ae1-857e-049c01da5575)
    
- **建立.gitignore檔案，把要忽略、不追蹤、不建立版本紀錄的檔名、副檔名寫在裡面**
    
    在commit時可以忽略這些檔案維持專案的整潔
    
    ![image 14](https://github.com/user-attachments/assets/c36efdc7-8495-49d7-a95b-2735e682fc07)

    ![image 15](https://github.com/user-attachments/assets/bc731472-6c23-4170-8e01-4407df4c7ed9)
    
- **把Git中的資料夾備份到Github**
    
    建立新的repository(儲存庫)
    
    ![image 16](https://github.com/user-attachments/assets/5c7ba62c-5773-4cf5-9605-2f66408874be)
    
    把本地檔案推到Github(要先確定在本地中有ssh金鑰以及在Github中有正確設定ssh公鑰)
    
    cat ….:把公鑰內容複製到github設定
    
    ![image 17](https://github.com/user-attachments/assets/c56a1c51-54d7-465b-8290-4f14d65355d3)

    確定ssh能連上github
    
    ![image 18](https://github.com/user-attachments/assets/2f50b1a8-50c0-4ac0-b9c6-d756abaec9fb)

    1.git remote add origin [git@github.com](mailto:git@github.com):zxc910529/PractiseGit_Project.git   (連結本地和雲端除儲存庫)
    
    2.git branch -M main   (把原來的主線分支的master改成main)
    
    3.git push -u origin main  (把main推送到雲端)
    
    ![image 19](https://github.com/user-attachments/assets/f78ce251-0f58-49f1-a742-1c5f83499334)

    ![image 20](https://github.com/user-attachments/assets/1db13480-2f1d-4eae-bbd7-b04074ade2b2)

    可看到以上傳完成!
    
- **git clone [git@github.com](mailto:git@github.com):zxc910529/PractiseGit_Project.git**
    
    把儲存庫的檔案複製到目前的資料夾
    
    git checkout -b  branch2
    
    共同編輯要要編輯儲存庫的檔案時，可建立分支並切換過去
    
    之後可以在github中用pull request請求合併到主線分支。
    
    之後可在本地中打git pull下載最新的變更維持本地和儲存庫同步。
