# 虚拟环境配置

## 1. 创建虚拟环境

Python 3 以后版本用自带的命令建立虚拟环境，不用安装另外的如 virtualenv、virtualenvwrapper 等工具。

在 CMD 或 PowerShell 中执行以下命令：

```batch
> cd myApp
myApp> python -m venv venv
```

或者

```batch
> cd myApp
myApp> py -3 -m venv venv
```

创建完成后项目文件夹中会有一个 venv 文件夹。该文件夹包含 'lib'、'include'、'bin'（Windows 系统下是 'scripts'）几个文件夹，共同构成了一个完整的 Python 环境。在 'lib' 中有 pip 等工具用于安装第三方包，它们和系统中已安装的 Python 互不关联。

## 2. 激活虚拟环境

在 CMD 或 PowerShell 中执行以下命令：

```batch
> cd myApp
myApp> venv\scripts\activate
```

激活后，在 CMD 或 PowerShell 中显示：

```batch
(venv) myApp>
```

Windows 系统下，如果要使用 PowerShell 首先要更新一下脚本执行策略。

在管理员 PowerShell 中执行以下命令：

```batch
Set-ExecutionPolicy AllSigned | Set-ExecutionPolicy -ExecutionPolicy UNRESTRICTED
cd myApp
myApp> venv\scripts\activate.ps1
```

## 3. 退出虚拟环境

在 CMD 或 PowerShell 中执行以下命令：

```batch
cd myApp
(venv) myApp> venv\scripts\deactivate
```

退出后，在 CMD 或 PowerShell 中显示：

```batch
myApp>
```

## 4. 导出虚拟环境中的包

- 输出虚拟环境中已安装包的名称及版本号并记录到 requirements.txt 文件中

    在 CMD 或 PowerShell 中执行以下命令：

    ```batch
    (venv) myApp> pip freeze > requirements.txt
    ```

- 将安装的包保存到文件夹(名字任意起，如：packages)里

    在 CMD 或 PowerShell 中执行以下命令：

    ```batch
    (venv) myApp>  pip download -r requirements.txt -d packages
    ```

- 在另一台设备新建虚拟环境

- 将 requirements.txt 和 packages 复制到新建的虚拟环境中，激活虚拟环境后安装包：

    在 CMD 或 PowerShell 中执行以下命令：

    ```
    (venv) myApp> pip install --no-index --find-links=packages -r requirements.txt
    ```

## 5. 删除虚拟环境

直接删除 venv 目录即可


# 依赖模块

## 1. pylint 模块

下载安装

```
在 VSCODE 中安装
python.exe -m pip install -U pylint
pip install -U pylint
```