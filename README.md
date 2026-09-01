# Shared-photo-wall
A simple image sharing website that supports uploading, viewing, downloading, and deleting (your own) images!

✨ 功能 
 
 • 📤 上传图片（支持拖拽） 
 • 👀 查看大图 
 • 📥 下载图片 
 • 🗑️ 删除自己的图片 
 • 💾 记住用户名 
 • 🎨 漂亮的渐变界面 
 • 📱 响应式设计


# 📸 部落图片墙

一个简单的图片分享网站，支持上传、查看、下载、删除（自己的）图片！

## 🚀 快速开始

### 1. 创建 Supabase 项目
1. 访问 https://supabase.com 注册
2. 创建新项目
3. 在项目设置 → API 里获取你的 URL 和 Anon Key

### 2. 配置数据库和存储桶

#### 存储桶设置
- Storage → New bucket → 命名为 `photos`
- 设为 Public bucket
- Policies → Disable RLS（最简单）或创建Buckets3个： NAME                                   COMMAND       APPLIED TO
-                                                 Allow Public Delete                     DELETE       anon, authenticated
-                                                 Allow Public Upload                     INSERT       anon, authenticated
-                                                 Allow Public Read                       SELECT       anon, authenticated


#### 数据库表
- Table Editor → New table → 命名为 `photos`
- 添加这些列：
  - `id` (int8, Primary Key, Is Identity)
  - `url` (text)
  - `name` (text)
  - `uploader` (text)
  - `user_id` (text)
  - `file_path` (text)
  - `created_at` (timestamptz, Default: now())

### 3. 修改配置
编辑 `photo-wall.html`，填入你的配置：

```javascript
const SUPABASE_URL = 'YOUR_SUPABASE_URL';
const SUPABASE_ANON_KEY = 'YOUR_SUPABASE_ANON_KEY';
