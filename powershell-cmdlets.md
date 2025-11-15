## PowerShell命令

### 1.get-help,首先需要以管理员身份端口powershell然后链接网络更新get-help

```postgresql
get-help get-eventlog
```

![image-20251114193851277](assets/image-20251114193851277.png)

### 2.get-eventlog

```powershell
get-eventlog -list
```

效果:

![image-20251114194042888](assets/image-20251114194042888.png)

```powershell
get-eventlog -logname system -newest 5
```

效果:

![image-20251114194341190](assets/image-20251114194341190.png)

```powershell
$event = get-eventlog system -newest 50
$event | group-object -property source -noelement | sort-object -property count -descending
```

效果:

![image-20251114194828113](assets/image-20251114194828113.png)

```powershell
get-eventlog -logname system -entrytype error -newest 10
```

效果:

![image-20251114195130274](assets/image-20251114195130274.png)

```powershell
 get-eventlog -logname system -instanceid 10016 -source DCOM -newest 10
```

效果:

![image-20251114195645132](assets/image-20251114195645132.png)

```powershell
 get-eventlog -logname system -computername KENNYCAI -newest 10
```

效果:

![image-20251114200201425](assets/image-20251114200201425.png)

```powershell
get-eventlog -logname system -newest 1 | select-object -property *
```

效果:

![image-20251114200615196](assets/image-20251114200615196.png)

```powershell
Get-EventLog -LogName System -UserName NT* -newest 10
```

效果:

![image-20251114201948424](assets/image-20251114201948424.png)