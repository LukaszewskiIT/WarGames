# Level 0  
 
**Host:**  
`century0@century.underthewire.tech`

### Description&Objective:
The goal of this level is to log into the game.

### Solution  
Log into the SSH session using the password provided in the **UnderTheWire Slack channel**.

##### Password:
`century1`

---

# Level 1

**Host:**  
`century1@century.underthewire.tech`

### Description & Objective:
> The password for **Century2** is the build version of the instance of **PowerShell** installed on this system.  

### Solution
> I searched in the browser how to check the PowerShell version using a command.

### Commands & Output:

```powershell  
$PSVersionTable  
```

![Level1](UnderTheWire/Century/Screenshots/century1.png)

---

## Level 2

**Host:**  
`century2@century.underthewire.tech`

### Description & Objective:
> The password for Century3 is the name of the built-in cmdlet that performs the wget like function within PowerShell PLUS the name of the file on the desktop.

### Solution
> I searched the web on how to list files in the current directory using a PowerShell command.
  
### Commands & Output:
  
```powershell  
Get-ChildItem  
```
![[Pasted image 20260308230812.png]]

```powershell
Invoke-WebRequest
```

---

## Level 3

**Host:**  
`century3@century.underthewire.tech`

### Description & Objective:
> The password for Century4 is the number of files on the desktop.

### Solution
> 

### Commands & Output:
```powershell
Get-ChildItem -File | Measure-Object | Select-Object -ExpandProperty Count
```

Short, console style version:
```powershell
(ls).Count
```

![[Pasted image 20260308232243.png]]

## Level 4

**Host:**  
`century4@century.underthewire.tech`

### Description  
The password for Century5 is the name of the file within a directory on the desktop that has spaces in its name.

### Solution
> 

### Commands & Output:

```powershell
Get-ChildItem -Path "C:\users\century4\desktop\Can You Open Me"
```

![[Pasted image 20260311032430.png]]

---

## Level 5

**Host:**  
`century5@century.underthewire.tech`

### Description & Objective:
> 

### Solution
> 

### Commands & Output:

```powershell
ls
```

```powershell
Get-ADDomain
```

## outputs:

#### 1:
![[Pasted image 20260311033717.png]]
#### 2:
![[Pasted image 20260311033513.png]]

---

# Personal Thoughts:


#### Sources:

