# 关于 GIT 撤销修改的操作详解

## 4个区

```flow
st=>start: 工作区
e1=>start: 暂存区
e2=>start: 本地仓库
e=>end: 远程仓库
st->e1->e2->e
```

## 5种状态

- 未修改（Origin）
- 已修改（Modified）
- 已暂存（Staged）
- 已提交（Committed）
- 已推送（Pushed）

## 检查修改

1. 已修改，未暂存

   ```shell
   git diff
   ```

   ​

2. 已暂存，未提交

   ```shell
   git diff --cached
   ```

   ​

3. 已提交，未推送

   ```shell
   git diff master origin/master
   ```

## 撤销修改

1. 已修改，未暂存

   ```shell
   git checkout
   或
   git reset --hard
   ```

   ​

2. 已暂存，未提交

   ```shell
   git reset
   git checkout
   或
   git reset --hard
   ```

   ​

3. 已提交，未推送

   ```shell
   git reset --hard origin/master
   ```

4. 已推送

   ```shell
   git reset --hard HEAD^
   git push -f
   ```

   ​
