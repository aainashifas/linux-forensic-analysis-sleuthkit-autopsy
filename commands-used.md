# Commands Used

## Partition Layout

```bash
mmls Linux_Financial_Case.001
```

<img width="888" height="243" alt="mmls partition layout output" src="https://github.com/user-attachments/assets/b636c61a-7cae-42f5-b439-f52ef5b10c61" />

## File System Information

```bash
fsstat -o 2048 Linux_Financial_Case.001
```

<img width="881" height="523" alt="fsstat file system information output" src="https://github.com/user-attachments/assets/1332a9e8-bedd-4519-a2af-828d349337a5" />

## Read-Only Mount

```bash
sudo mount -o ro,loop,offset=$((2048*512)) Linux_Financial_Case.001 /mnt/finance
```

<img width="883" height="178" alt="read only forensic mount command output" src="https://github.com/user-attachments/assets/13815cbe-0076-42e6-b20c-bb1454b4d472" />

## List Deleted Files and Directories

```bash
fls -o 2048 -rdm / Linux_Financial_Case.001 > flsBody
```

<img width="781" height="52" alt="fls deleted files body file command" src="https://github.com/user-attachments/assets/47e27404-09ae-44fa-a1d7-ef55612318c0" />

## Create Timeline from fls Output

```bash
mactime -b flsBody > flsMactime
```

<img width="796" height="55" alt="mactime timeline from fls body command" src="https://github.com/user-attachments/assets/541334ff-4626-4f48-8f40-57ec9fb64dc3" />

## List Deleted Inodes

```bash
ils -o 2048 -m Linux_Financial_Case.001 > ilsBody
```

<img width="809" height="59" alt="ils deleted inode body file command" src="https://github.com/user-attachments/assets/0bddb19d-5519-4a34-8af1-85459c0ee700" />

## Create Timeline from ils Output

```bash
mactime -b ilsBody > ilsMactime
```

<img width="870" height="402" alt="mactime timeline from ils body output" src="https://github.com/user-attachments/assets/5a35157d-7f8d-411b-b0ab-f70813375910" />

## View Inode Metadata

```bash
istat -o 2048 Linux_Financial_Case.001 46082
```

<img width="863" height="399" alt="istat inode metadata output" src="https://github.com/user-attachments/assets/5dcefb9c-fc5a-4410-986d-564291a70554" />

## Extract File Content from Inode

```bash
icat -o 2048 Linux_Financial_Case.001 46082 > inode46082dump.bin
```

<img width="858" height="45" alt="icat inode content extraction command" src="https://github.com/user-attachments/assets/b966d1df-06b7-4e26-9e72-37897b4fea76" />

## Find Filename from Inode

```bash
ffind -o 2048 Linux_Financial_Case.001 46082
```

<img width="812" height="83" alt="ffind filename from inode output" src="https://github.com/user-attachments/assets/7e7908c2-cecc-4384-a706-439f6c91f3b1" />

## Dump Data Block Content

```bash
blkcat -o 2048 Linux_Financial_Case.001 197122 > block197122dump.bin
```

<img width="873" height="54" alt="blkcat data block dump command" src="https://github.com/user-attachments/assets/330a2315-ff2b-4fa6-8a7f-c46d6e2c7b81" />

## Find Inode Referencing a Data Block

```bash
ifind -o 2048 -d 197122 Linux_Financial_Case.001
```

<img width="791" height="85" alt="ifind inode referencing data block output" src="https://github.com/user-attachments/assets/8d10a9a7-6879-43f2-a318-582233c09242" />
