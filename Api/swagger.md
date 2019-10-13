# Swaggerの書き方

## リクエストの書き方
### フォームからのリクエストの書き方
#### 画像 + 他のデータを一緒にリクエストしたい場合
下記のように書く.

```
parameters: 
 - in: formData
   name: upfile
   type: file
   required: true
 - in: formData
   name: note
   type: string
   required: false
   description: sample text
```


#### 参考URL 
- [File Upload](https://swagger.io/docs/specification/2-0/file-upload/)
- [Describing Parameters](https://swagger.io/docs/specification/2-0/describing-parameters/)
