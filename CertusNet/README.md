# OAM ISLA项目V1
该GitBook是2024年7月1日新创建，汇总的OAM全部设计文档，很多内容进行了重新编写。使用GitBook（Markdown）的形式主要是为了方便大家随时查阅以及良好的历史版本追踪能力。
**ISLA** 的全称是 Integration System for Logistics Administration (用于组织管理自动化的集成系统)

- 如果你是第一次看到此篇文档，首先欢迎你加入OAM团队，也欢迎你阅读我们的文档。请从[新员工工作指引](./Commonwork/new_employee.md)开始阅读。
- 所有文档内容均尽量标注代码出处以便今后开发人员在优化对应功能的时候，能够依托此文档快速索引到代码位置，方便开发。

## 目录
* [NR-OAM总体设计说明](A1-C0-oam_overview.md)
    * [守护进程](A1-C1-daemon.md)
    * [启动流程](A1-C2-startup.md)
    * [设备与配置](A1-C3-config.md)
    * [EU,RU管理](A1-C4-eru_mgmt.md)
    * [告警](A1-C5-alarm.md)
    * [性能](A1-C6-pm.md)
    * [日志](A1-C7-log.md)
    * [软件升级](A1-C8-swm.md)
    * [南向接口](A1-C9-sourceinterface.md)
    * [自动开站](A1-C10-startup-automation.md)
    * [License软件许可](A1-C11-license.md)
    * [基站直连接口](A1-C12-restful_interface.md)
* [加速卡总体设计说明](A2-C0-fh_overview.md)
* [ERU总体设计说明](A3-C0-eru_overview.md)
    * [NETCONF Server](A3-C1-eru_netconf_server.md)
* [直放站（永鼎）开发维护方法](A4-C0-signalbooster_overview.md)
* [LTE（海能达）开发维护说明](A5-C0-hyt_lte_overview.md)
    * [LBP板卡升级流程汇总](A5-C1-lbp_upgrade.md)
    * [海能达LTE-Sector管理（ERU）和组网时延配置](A5-C2-sector_cell_config.md)
* [特性设计报告汇总](./SpecificFunction/specific_overview.md)
    * [基站升级优化方案](./SpecificFunction/UpgradeRefineFunction/upgrade_refine_function.md)
    * [动态AGC](./SpecificFunction/cell/dynamic_agc.md)
    * [基站节能流程](./SpecificFunction/cell/save_energy_flow.md)
* [基站缺陷与GAP汇总](./TrapAndGap/trap_gap_overview.md)
    * [海能达LTE多小区](./TrapAndGap/hyt_muticell.md)
    * [灵活小区删建与激活去激活](./TrapAndGap/flex_cell.md)
    * [前传卡同步升级功能](./TrapAndGap/fh_sync_upgrade.md)
* [资源工作汇总](./Commonwork/overview.md)
    * [各类权限,常用软件汇总](./Commonwork/authority_software.md)
    * [新员工工作指引](./Commonwork/new_employee.md)
    * [开发虚拟机列表与管理办法](./Commonwork/vm_manager.md)
    * [Bugzilla问题处理流程](./Commonwork/bugzilla_process.md)
    * [版本编译发布流程](./Commonwork/compile_publish_process.md)




## 文档分类与使用规范说明

### 内部文档(即本GitBook)
2024年7月1日起，所有OAM的设计和对内说明文档均使用GitBook（Markdown）形式，方便大家随时查阅
- **设计文档**：包含NR-OAM，LTE-OAM总体设计、加速卡总体设计、ERU总体设计、直放站（永鼎）维护方法等。
- **资源文档**：包含新员工工作指引、各类权限,常用软件等。
- **内部梳理总结文档**：包含特性设计报告汇总、基站缺陷与GAP等

### 对外说明文档（在Confluence上发布）
- **版本发布说明**：OAM的版本发布周期按照项目节奏调整，如周或月为粒度发布或紧急BugFix版本。均需要在[Confluence](http://192.168.10.67:8090/pages/viewpage.action?pageId=16515518)上列出本次发布的组件和对应的版本号，以及发布说明（主要是列出Bugzilla系统中的BugID和描述）
- **特性自测报告**：在[Confluence](http://192.168.10.67:8090/pages/viewpage.action?pageId=52166683)上进行编写和发布，该服务托管在项目管理，自测报告主要阅读对象为测试、交付，故在此发布

### 外部文档（从项目SVN中取用）
- **运营商规范**：请直接取用项目管理SVN中的文件，该文档由产品经理负责更新，地址：http://172.16.33.5/svn/5G/Documents/common
- **项目需求**：请直接取用项目管理SVN中的文件，该文档由产品经理负责更新，地址：http://172.16.33.5/svn/5G/Documents/common



## GitBook 使用说明

### 本地安装和预览

1. 确保你已经安装了 Node.js 和 npm。
2. 全局安装 GitBook CLI：
    ```sh
    npm install -g gitbook-cli
    ```
3. 克隆本项目到本地：
    ```sh
    git clone http://172.21.6.179:8099/certusnetoam/oam_gitbook.git
    ```
4. 进入项目目录并安装依赖：
    ```sh
    gitbook install
    ```
5. 运行 GitBook 以在本地预览：
    ```sh
    gitbook serve
    ```
    预览地址通常为 `http://localhost:4000`。

### 部署到服务器

目前OAM组内部 GitBook 托管在服务器 `172.21.6.174` 上。若想要更新此文档，以下是部署步骤：

1. 将本地修改推送到远程仓库：
    ```sh
    git add .
    git commit -m "Update documentation"
    git push origin master
    ```
2. SSH 登录到服务器：
    ```sh
    ssh root@172.21.6.174
    # 密码: CertusNet.123
    ```
3. 进入项目目录并拉取最新的更改：
    ```sh
    cd /home/oamGitBook/
    git pull
    ```
4. 构建静态文件：
    ```sh
    gitbook build
    ```
5. 访问： http://172.21.6.174:4000/


### 自启动指南
在 Ubuntu 下设置 GitBook Server 自启动，你可以使用 systemd 服务管理器来创建自启动服务。以下是具体步骤：

#### 步骤 1：创建 GitBook 服务文件

1. 创建一个新的 systemd 服务文件，例如 `gitbook.service`。

   ```sh
   sudo vim /etc/systemd/system/gitbook.service
   ```

2. 在服务器中添加以下内容：
   ```ini
   [Unit]
    Description=GitBook Service
    After=network.target

    [Service]
    ExecStart=/usr/local/bin/gitbook serve /home/oamGitBook
    WorkingDirectory=/home/oamGitBook
    Restart=always
    User=root
    Environment=PATH=/usr/bin:/usr/local/bin
    Environment=NODE_ENV=production

    [Install]
    WantedBy=multi-user.target
   ```

3. 在服务文件中添加以下内容，假设你有两个 GitBook 项目，并且需要在启动时指定不同的端口：

   ```ini
   [Unit]
   Description=GitBook Server for Project1 and Project2
   After=network.target

   [Service]
   ExecStart=/bin/bash -c 'cd /home/user/gitbooks/project1 && gitbook serve --port 4000 & cd /home/user/gitbooks/project2 && gitbook serve --port 4001'
   Restart=always
   User=user
   Environment=PATH=/usr/bin:/usr/local/bin
   Environment=NODE_ENV=production
   WorkingDirectory=/home/user

   [Install]
   WantedBy=multi-user.target
   ```

   请将 `/home/user/gitbooks/project1` 和 `/home/user/gitbooks/project2` 替换为你的实际项目路径。将 `user` 替换为运行 GitBook Server 的实际用户。

#### 步骤 2：设置服务文件权限

1. 设置服务文件的正确权限：

   ```sh
   sudo chmod 644 /etc/systemd/system/gitbook.service
   ```

#### 步骤 3：刷新 systemd 并启用服务

1. 重新加载 systemd 配置：

   ```sh
   sudo systemctl daemon-reload
   ```

2. 启用 GitBook 服务，使其在启动时自动运行：

   ```sh
   sudo systemctl enable gitbook.service
   ```

3. 立即启动 GitBook 服务：

   ```sh
   sudo systemctl start gitbook.service
   ```

#### 步骤 4：检查服务状态

1. 检查 GitBook 服务是否成功启动：

   ```sh
   sudo systemctl status gitbook.service
   ```

#### 示例服务文件解释

- `[Unit]` 部分定义了服务的描述和依赖关系。
- `[Service]` 部分定义了服务的执行命令、重启策略、运行用户和环境变量。
  - `ExecStart` 使用 `/bin/bash -c` 来运行两个 `gitbook serve` 命令，将它们放在后台运行（通过 `&` 符号）。
  - `Restart` 设置为 `always`，以确保服务在失败时自动重启。
  - `User` 指定运行服务的用户。
  - `Environment` 设置了环境变量，包括 `PATH` 和 `NODE_ENV`。
  - `WorkingDirectory` 设置了工作目录。
- `[Install]` 部分定义了服务安装的目标。



### 贡献指南

如果你想为本项目做出贡献，请遵循以下步骤：

1. 克隆此仓库
2. 创建你的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交你的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开一个 Pull Request


### 附录

Theme: [gitbook-plugin-theme](https://www.npmjs.com/search?q=gitbook-plugin-theme)
- 当前应用主题：[skdoc](https://www.npmjs.com/package/gitbook-plugin-theme-skdoc)


# Change Log
| Date (YYYY-MM-DD) | Version | Changed By | Change Description       |
| ----------------- | ------- | ---------- | ------------------------ |
| 2024-07-09        | 1.0     | Guoliang   | 创建文档，并完成大纲设计 |