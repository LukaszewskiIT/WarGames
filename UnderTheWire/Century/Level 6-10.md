# Level 6  

#### Host:
`ssh century6@century.underthewire.tech`

### Description & Objective:
>The password for Century7 is the number of folders on the desktop.
### Solution:
> I used my knowledge of `Get-ChildItem` and the `.Count` property gained in previous levels, specifying that only directories should be counted by using the `-Directory` parameter.

### Commands&Outpust:

```powershell
(Get-ChildItem -Directory).Count
```


![[Pasted image 20260315145753.png]]

---

# Level 7 

#### Host:
`ssh century7@century.underthewire.tech`

### Description&Objective:
> The password for Century8 is in a readme file somewhere within the contacts, desktop, documents, downloads, favorites, music, or videos folder in the user’s profile.
### Solution

To solve this section, I needed to run a recursive search across the user folders to find the specified readme file. I assumed it would be a `.txt` file, so I ran a command filtering the results by that extension. Then, I used `Get-Content` with the specified path to view the file's contents.

### Commands&Outpust:

```powershell
Set-Location C:\users\century7
```

```powershell
Get-ChildItem -Recurse -Filter "*.txt"
```

```powershell
Get-Content -Path C:\users\century7\Downloads\Readme.txt
```

![[Pasted image 20260315154015.png]]

---


# Level 8  

#### Host:
`Lorem  ipsum Lorem  ipsum Lorem  ipsum `

### Description&Objective:
> Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum 
### Solution:
  
Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum 

### Commands&Outpust:



---


# Level 9 

#### Host:
`Lorem  ipsum Lorem  ipsum Lorem  ipsum `

### Description&Objective:
> Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum 
### Solution:
  
Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum 

### Commands&Outpust:



---


# Level 10  

#### Host:
`Lorem  ipsum Lorem  ipsum Lorem  ipsum `

### Description&Objective:
> Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum 
### Solution:
  
Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum 

### Commands&Outpust:



---



# Level 11  

#### Host:
`Lorem  ipsum Lorem  ipsum Lorem  ipsum `

### Description&Objective:
> Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum 
### Solution:
  
Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum Lorem  ipsum 

### Commands&Outpust:



---






#### References:
- [Microsoft Docs](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-7.5) & [PowerShellFAQs](https://powershellfaqs.com/find-file-by-name-in-powershell/) – knowledge about the `Get-ChildItem` cmdlet. 
- [Microsoft Docs](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-content?view=powershell-7.5) – knowledge about the `Get-Content` cmdlet.
- [PowerShellFAQs](https://powershellfaqs.com/change-directory-in-powershell/) – guidance on moving between directories in PowerShell.
- [Microsoft Docs](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-unique?view=powershell-7.5) - knowledge about the `Get-Unique` cmdlet.
