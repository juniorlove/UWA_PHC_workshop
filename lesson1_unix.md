# lesson1 of HPC: Unix Shell

11 Jul 2022, Sen

## 1. [`man`*](<https://www.linuxcool.com/man#:~:text=man%E5%91%BD%E4%BB%A4%E6%98%AFLinux%E4%B8%8B%E6%9C%80%E6%A0%B8%E5%BF%83%E7%9A%84%E5%91%BD%E4%BB%A4%E4%B9%8B%E4%B8%80%E3%80%82.%20%E8%80%8Cman%E5%91%BD%E4%BB%A4%E4%B9%9F%E5%B9%B6%E4%B8%8D%E6%98%AF%E8%8B%B1%E6%96%87%E5%8D%95%E8%AF%8D%E2%80%9Cman%E2%80%9D%E7%9A%84%E6%84%8F%E6%80%9D%EF%BC%8C%E5%AE%83%E6%98%AF%E5%8D%95%E8%AF%8Dmanual%E7%9A%84%E7%BC%A9%E5%86%99%EF%BC%8C%E5%8D%B3%E4%BD%BF%E7%94%A8%E6%89%8B%E5%86%8C%E7%9A%84%E6%84%8F%E6%80%9D%E3%80%82.%20man%E5%91%BD%E4%BB%A4%E4%BC%9A%E5%88%97%E5%87%BA%E4%B8%80%E4%BB%BD%E5%AE%8C%E6%95%B4%E7%9A%84%E8%AF%B4%E6%98%8E%E3%80%82.%20%E5%85%B6%E5%86%85%E5%AE%B9%E5%8C%85%E6%8B%AC%E5%91%BD%E4%BB%A4%E8%AF%AD%E6%B3%95%E3%80%81%E5%90%84%E9%80%89%E9%A1%B9%E7%9A%84%E6%84%8F%E4%B9%89%E5%8F%8A%E7%9B%B8%E5%85%B3%E5%91%BD%E4%BB%A4%20%E3%80%82.,%E6%9B%B4%E4%B8%BA%E5%BC%BA%E5%A4%A7%E7%9A%84%E6%98%AF%EF%BC%8C%E4%B8%8D%E4%BB%85%E5%8F%AF%E4%BB%A5%E6%9F%A5%E7%9C%8BLinux%E4%B8%AD%E5%91%BD%E4%BB%A4%E7%9A%84%E4%BD%BF%E7%94%A8%E5%B8%AE%E5%8A%A9%EF%BC%8C%E8%BF%98%E5%8F%AF%E4%BB%A5%E6%9F%A5%E7%9C%8B%E8%BD%AF%E4%BB%B6%E6%9C%8D%E5%8A%A1%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6%E3%80%81%E7%B3%BB%E7%BB%9F%E8%B0%83%E7%94%A8%E3%80%81%E5%BA%93%E5%87%BD%E6%95%B0%E7%AD%89%E5%B8%AE%E5%8A%A9%E4%BF%A1%E6%81%AF%E3%80%82.%20man%E6%89%8B%E5%86%8C%E9%A1%B5%E6%96%87%E4%BB%B6%E5%AD%98%E6%94%BE%E5%9C%A8%2Fusr%2Fshare%2Fman%E7%9B%AE%E5%BD%95%E4%B8%8B%E3%80%82.%20%E8%AF%AD%E6%B3%95%E6%A0%BC%E5%BC%8F%EF%BC%9A%20man%20%5B%E5%91%BD%E4%BB%A4%5D>)

**Usages:** Abbreviation of '**manual**', which is to view help informations of commands, configuration files, and services.

```bash
>>> man ls
```

**Parameter:**

- `-a`: search in all `man` manual
- `-d`: check whether the new file is correct
- `-f`: display the short discription
- `-p`: use pager
- `-M`: specify the path
- `-w`: display the file location

**Hot-keys of `man` menu:**

- `q`: quit
- `Enter`: filp down by line
- `Space`, `PgDn`: page down
- `b`, `PgUp`: page up
- `home`: to homepage
- `end`: to final page
- `/$string`: find keyword `$string` (in ascent order)
- `?$string`: find keyword `$string` (in descent order)
- `n`: navigate to the next keyword
- `N`: navigate to the last keyword

## 2. [`cd`](<https://swcarpentry.github.io/shell-novice/02-filedir/index.html>)

```bash
# Open `usr/bin`:
>>> cd usr/bin/
# Open $home:
>>> cd ~
>>> cd
# Back to the former directory:
>>> cd -
# Back to the parent directory:
>>> cd ..
# Present the local address:
>>> pwd
usr/bin
```

## 3. [`ls`](<https://www.runoob.com/linux/linux-comm-ls.html>)

[**Parameter:** (partial)](<https://www.yiibai.com/linux/ls.html>)

- `-r`, `-reverse`: listed in reverse order
- `-R`, `-recursive`: list all sub-directory as well
- `-f`: list without counting
- `-F`: Add a signal behind (`*` for files and `/` for directories)
- `-t`: list files of sub-directories in order if possible

**Cases:**

```bash
>>> pwd
/mnt/c/Users/Hsueh/Desktop/NoteGem2016

>>> ls
NoteGem2016-67.0.0.333.exe  'Password=1.txt'
>>> ls -r -F
'Password=1.txt'*   NoteGem2016-67.0.0.333.exe*
```

## 4. [`wc`*](<https://www.runoob.com/linux/linux-comm-wc.html>)

**Usage:** count words.

**Parameter:**

- `-c`, `--bytes`, `--chars`: present the number of <u>**bytes**</u> only;
- `-l`, `--lines`: present the number of <u>**lines**</u> only;
- `-w`, `--words`: present the number of <u>**words**</u> only

```bash
>>> pwd
/mnt/c/Users/Hsueh/Desktop/元素统计

>>> wc demo.m
28  81 716 demo.m
>>> wc -c demo.m
716 demo.m
>>> wc -l demo.m
28 demo.m
>>> wc -w demo.m
81 demo.m
```

**Cases:**

```bash
>>> pwd
/mnt/c/Users/Hsueh/Desktop/元素统计

>>> wc -w *.m > len.txt # Which means the result of `wc -w` are saved as 'lengths.text'
>>> cat len.txt # Browse the data
  81 demo.m
  58 statable.m
 139 total
>>> sort -n len.txt
  58 statable.m
  81 demo.m
 139 total
```

## 5. [`less`*](<https://www.runoob.com/linux/linux-comm-less.html>)

**Usage:** similar to `more`, which is to browse the file

```bash
>>> less len1.txt # browse a single file
```

**Parameter:**

*(Click the linkage of `less*`)*

**Cases:**

```bash
>>> less len1.txt len2.txt # browse multiple files
```

where `n` switch to `len2.txt` and `p` to `len1.txt`

## 6. [`sort`](<https://www.runoob.com/linux/linux-comm-sort.html>)

**Parameter:**

- `-k $field1 [, field2]`: sort with the specified column(s)

```bash
>>> sort -k 2,2 len.txt
# where `2,2` means the matrix is sorted only by 2nd column
```

**Q: How about `sort -k 2,1 len.txt`?**
**A:** According to the result shown as follows, it may concluded that Command `sort -k f1,f2 $file` equals that of `sort $file` when `f1` > `f2`.

```bash
>>> cat a
1 2 1 4 5
2 2 2 2 2
2 3 7 5 1
2 0 8 3 9

>>> sort a
1 2 1 4 5
2 0 8 3 9
2 2 2 2 2
2 3 7 5 1
>>> sort -k 5 a
2 3 7 5 1
2 2 2 2 2
1 2 1 4 5
2 0 8 3 9
>>> sort -k 5,4 a
1 2 1 4 5
2 0 8 3 9
2 2 2 2 2
2 3 7 2 1
## Results of `sort -k 5,3 a`, `sort -k 5,2 a`, and `sort -k 5,1 a` are same with `sort -k 5,4 a`
# and so is `sort -k 4,3 a`, `sort -k 4,2 a` and `sort -k 4,1 a`
```

## 7. [`cut`](<https://www.runoob.com/linux/linux-comm-cut.html>)

**Usage:** present the words from `num1` to `num2` each line

```bash
>>> cut -b $N a
```

**Parameter:**

- `-b`: select these <u>**bytes**</u> only
- `-c`: select these <u>**character**</u> only
- `-d`, `--delimiter=DELIM`: specify `DELIM` as delimiter (default: `Tab`)
  - `-df`: used with `-d`, pointing the region displayed
- `$N`:
  - `$N`: `$N`'th byte, character or field, counted from 1
  - `$N-`: from `$N`'th byte, character or field, to `end` of line
  - `$N-$M`: from `$N`'th to `$M`'th (included) byte, character or field
  - `-$M`: from `start` to `$M`'th (included) byte, character or field

[To exlain, for example,](<https://www.programming-books.io/essential/bash/the-cut-command-35e5e54a9c0b4f6b90147f6cecd723d3>)

```text
# In an encoding where each character in the input string is three bytes wide
# Selecting bytes 1-6 yields the first two characters (correct)

$LC_ALL = ja_JP.UTF-8 cut -b1-6 kanji.utf-8.txt
...first two characters of each line...

# Selecting all three characters with the -c switch doesn’t work
# It behaves like -b, contrary to documentation

$LC_ALL = ja_JP.UTF-8 cut -c1-3 kanji.utf-8.txt
...first character of each line...

# In this case, an illegal UTF-8 string is produced
# The -n switch would prevent this, if implemented

$LC_ALL = ja_JP.UTF-8 cut -n -c2 kanji.utf-8.txt
...second byte, which is an illegal UTF-8 sequence...

```

## 8. [`uniq`](<https://www.runoob.com/linux/linux-comm-uniq.html>)

**Usage:** Check and delete repeated rows, generally used with `sort` together.

**Parameter:**

- `-c`, `--count`: show the occurred times
- `-d`, `--repeated`: show **repeated rows** only
- `-u`, `--unique`: show rows **oncedisplayed once** only

## 9. [`touch`](<https://www.runoob.com/linux/linux-comm-touch.html>)

**Usage:** modify the time properties of files/directories

```bash
>> pwd
/mnt/c/Users/Hsueh/Desktop/元素统计
>> ll len.txt
-rwxrwxrwx 1 khan khan 39 Jul 11 13:18 len.txt*

>>> touch testfile
>>> ll len.txt
-rwxrwxrwx 1 khan khan 39 Jul 11 15:12 len.txt*
```

## 10. `rm`

**Parameter:**

- `-i`: do a confirmation one by one before deletion

---

## Today in History

[![China National Maritime Day](https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/%E9%84%AD%E5%92%8C%E4%B8%8B%E8%A5%BF%E6%B4%8B%E4%B8%96%E7%95%8C%E5%9C%96.png/1920px-%E9%84%AD%E5%92%8C%E4%B8%8B%E8%A5%BF%E6%B4%8B%E4%B8%96%E7%95%8C%E5%9C%96.png)](<https://en.wikipedia.org/wiki/Ming_treasure_voyages>)
<center>

Zheng He Xia Xiyang (Ming treasure voyages, 11 Jul 1405)
</center>
