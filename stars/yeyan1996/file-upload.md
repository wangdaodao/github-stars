---
project: file-upload
stars: 698
description: A guide about how to upload and process large files (using Vue.js for frontend and Node.js for backend)
url: https://github.com/yeyan1996/file-upload
---

Implement Large File Upload and Resume Feature
==============================================

English | 中文

Blog

> Node14 is recommended

To retry the upload, you need to delete the file in `/target` directory, otherwise the upload will succeed directly because the server cache the file

download demo file: https://v0c98mphqw.feishu.cn/file/boxcnZ34jCyQziXxsS9NaV0zfre

Frontend

-   Vue@2
-   Element-ui
-   Blob#slice: file slice
-   FileReader + WebWorker + spark-md5: create file hash
-   xhr: send formData

Backend

-   Nodejs@14
-   multiparty: resolve formData

start
=====

```
npm install
```

```
npm run start
```
