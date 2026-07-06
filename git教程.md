你们实训文档里第 1 天就要求做 **Git 与版本控制实战**，包括在 GitHub/GitLab 上创建团队项目仓库、完成第一次协作提交。
下面我按 **GitHub 公共仓库** 教你，最简单。

## 一、先在 GitHub 上新建公共仓库

打开 GitHub，登录账号。

右上角点 **+** → **New repository**。

填写：

```text
Repository name: student-course-system
Description: 学生选课及学籍管理系统
Visibility: Public
```

然后建议勾选：

```text
Add a README file
```

最后点：

```text
Create repository
```

这样公共仓库就建好了。

---

## 二、把仓库下载到电脑

在仓库页面点绿色按钮 **Code**，复制仓库地址。

建议复制 **HTTPS** 地址，类似：

```bash
https://github.com/你的用户名/student-course-system.git
```

然后在电脑终端执行：

```bash
cd Desktop
git clone https://github.com/你的用户名/student-course-system.git
cd student-course-system
```

这样你的桌面上就会多一个项目文件夹。

---

## 三、第一次提交代码

比如你们先创建一个 `main.c`：

```c
#include <stdio.h>

int main() {
    printf("学生选课及学籍管理系统\n");
    return 0;
}
```

然后在项目文件夹里执行：

```bash
git status
git add .
git commit -m "初始化项目结构"
git push
```

如果推送成功，刷新 GitHub 页面，就能看到你上传的代码。

---

## 四、邀请组员一起协作

进入 GitHub 仓库页面：

```text
Settings → Collaborators → Add people
```

输入组员的 GitHub 用户名或邮箱，邀请他们。

组员接受邀请后，就可以一起提交代码。

---

## 五、推荐你们的项目目录结构

你们可以这样建文件：

```text
student-course-system/
├── README.md
├── main.c
├── common.h
├── student.c
├── student.h
├── course.c
├── course.h
├── select.c
├── select.h
├── file.c
├── file.h
├── login.c
├── login.h
├── data/
│   ├── students.txt
│   ├── courses.txt
│   └── selections.txt
└── docs/
    ├── 需求分析报告.docx
    ├── 总体设计文档.docx
    └── 测试报告.docx
```

这个结构也符合你们实训要求里的“多文件方式、每个模块作为单独 C 文件、头文件放宏和数据结构”的要求。

---

## 六、组员每天常用命令

每次开始写代码前，先拉取最新版本：

```bash
git pull
```

写完代码后提交：

```bash
git add .
git commit -m "完成学生信息添加功能"
git push
```

查看当前状态：

```bash
git status
```

查看提交记录：

```bash
git log --oneline
```

---

## 七、最简单的协作规则

你们可以先不用复杂分支，直接这样：

```text
组长：负责 main.c、总体结构、文档整合
成员1：负责 student.c / student.h
成员2：负责 course.c / course.h
成员3：负责 select.c、file.c、测试文档
```

每个人尽量不要同时改同一个文件，这样最不容易冲突。

如果你们只想交实训作业，用这个流程就够了：

```bash
git clone 仓库地址
git pull
修改代码
git add .
git commit -m "说明这次改了什么"
git push
```

记住这四个核心命令就行：

```bash
git pull
git add .
git commit -m "提交说明"
git push
```
