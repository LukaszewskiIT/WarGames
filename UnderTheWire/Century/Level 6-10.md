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

### Description & Objective:
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
`ssh century8@century.underthewire.tech`

### Description & Objective:
> The password for Century9 is the number of unique entries within the file on the desktop.
### Solution:
  
The solution is to locate the `.txt` file on the desktop that contains the entries and parse its contents using `Get-Content`. The output is then processed through `Sort-Object` and `Get-Unique` to identify unique entries, and finally counted using `Measure-Object`.

### Commands & Outpust:

```powershell
ls
```

```powershell
Get-Content unique.txt | Sort-Object | Get-Unique | Measure-Object
```

![[Pasted image 20260315165050.png]]

---


# Level 9 

#### Host:
`ssh century9@century.underthewire.tech`

### Description & Objective:
> The password for Century10 is the 161st word within the file on the desktop.
### Solution:
  
Here I needed to think a bit. The file on the desktop contains a large number of unsorted words, and the goal is to find the 161st one. Counting them manually was not practical, so I decided to store the words in a structure that would allow easy indexing.

The first solution that came to mind was creating an array. I created an array named `$strings` and populated it using `Get-Content`, splitting the words with the `.Split()` method. After creating the array, the only step left was to retrieve the 161st word. Since array indexing starts at 0, the correct index is `160`.

### Commands & Outpust:

```powershell
$strings = (Get-Content .\Word_File.txt).Split()
```

```powershell
$strings[160]
```
-
![[Pasted image 20260315173056.png]]

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
