# 登入：

登入有效期為180天，全加密傳輸，允許5裝置同時登入

## 傳入：

POST \("account","password","googlerecaptcha"\)

### 格式：

帳號：小於128字元之英文、數字；採UTF-8編碼  
密碼：編碼後小於256字元之Base64編碼  
驗證碼：自Google取得之驗證碼

## 回傳：

### 狀態碼：

#### 200 OK：回傳json格式的文件

* UserName：UTF-8之學生姓名
* StudentID：8位之正整數
* room：5位之整數；-1為不住校、-2為未知
* email：Base64編碼之電子郵件
* cookie：64字元之ASCII亂數
* ID：系統發給的使用者ID
* time：ISO 8601

#### 403 Forbidden：通常是登入失敗，回傳json格式的文件

##### error：

* user not fount
* recaptcha error
* account was banned
* bad enter

##### time：

* 正整數；自1970/1/1開始計算之秒數









