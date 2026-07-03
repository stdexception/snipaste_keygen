# Snipaste 公钥替换

## 密钥信息

| 项目 | 值 |
| --- | --- |
| 原始公钥 | `86a6313855512c692b7f44a7041a86d02890544923714acaeeb29e52883c9060` |
| 替换公钥 | `1ebf8f1197d33a99aee6c625e306739eb9bf1c2806324eb7b83a09933062aa04` |
| 对应私钥 | `951743f1381818ec1af9a32a2eafce42c6261f5089468ef863e7b903c183b3f6` |

## 替换方法

在原始二进制文件中搜索原始字节序列,然后替换为对应的值。总共有四个位置需要处理。

## P1 公钥替换

### 原始值

```cpp
appendLittleEndian32(encoded, 0x0605D602);
appendLittleEndian32(encoded, 0x6D9AA9AC);
appendLittleEndian32(encoded, 0xA6582F90);
appendLittleEndian32(encoded, 0x4D0A0CBF);
appendLittleEndian32(encoded, 0x7760E0AC);
appendLittleEndian32(encoded, 0xCEFC89DA);
appendLittleEndian32(encoded, 0x5382E255);
appendLittleEndian32(encoded, 0xFD1C2A33);
appendLittleEndian32(encoded, 0xEBB401BB); // unchanged
appendLittleEndian32(encoded, 0x2E8AF932);
appendLittleEndian32(encoded, 0xC32EAC2B);
appendLittleEndian32(encoded, 0x3D010B7A);
appendLittleEndian32(encoded, 0x75D375D6);
appendLittleEndian32(encoded, 0x2AB21F07);
appendLittleEndian16(encoded, 0xF605);
```

### 替换值

```cpp
appendLittleEndian32(encoded, 0x2FBBCF9A);
appendLittleEndian32(encoded, 0x9D8C2B6E);
appendLittleEndian32(encoded, 0x24DAB615);
appendLittleEndian32(encoded, 0x03FF1058);
appendLittleEndian32(encoded, 0x1628CF3D);
appendLittleEndian32(encoded, 0xB3F8CAFF);
appendLittleEndian32(encoded, 0x92156A03);
appendLittleEndian32(encoded, 0x9926748B);
appendLittleEndian32(encoded, 0xEBB401BB); // unchanged
appendLittleEndian32(encoded, 0x2E8AF932);
appendLittleEndian32(encoded, 0xC32EAC2B);
appendLittleEndian32(encoded, 0x3D010B7A);
appendLittleEndian32(encoded, 0x75D375D6);
appendLittleEndian32(encoded, 0x2AB21F07);
appendLittleEndian16(encoded, 0xF605);
```

## P2 Alternate Public Key

### 原始值

```text
AB CE 56 14 98 79 05 D9 F5 31 87 D2 83 9C AB 77
C5 76 88 59 75 F9 E7 5F 31 FE 2C 7D CB 24 4C B5
```

### 替换值

```text
24 32 3B 78 BC 83 E6 9A 2D CF AF C8 81 4C 7A AE
DE 32 04 D4 A3 FC 27 12 CE 1C D3 82 46 BD ED 44
```

## P3 Base64 Public Key Text

### 原始值

```text
86 17 95 87 F4 64 65 25 C4 74 B6 27 66 03 35 E6
24 24 17 74 03 34 96 15 65 54 B6 A6 36 55 27 B4
73 27 B4 56 55 F6 76 83 B6 74 14 D3 00
```

### 替换值

```text
84 27 B2 05 54 A5 66 45 F4 07 D6 57 53 37 95 C6
43 77 A5 A7 E6 27 D6 F2 84 34 76 74 D4 B6 63 33
57 44 F6 A4 B6 A7 24 96 17 76 15 D3 00
```

## P4 AES Base64 Crypto Material

### 原始值

```cpp
appendLittleEndian32(encoded, 0x45FD0238);
appendLittleEndian32(encoded, 0x7EEF67D7);
appendLittleEndian32(encoded, 0xCFC76404);
appendLittleEndian32(encoded, 0x8CBC9227);
appendLittleEndian32(encoded, 0x7AD53112);
appendLittleEndian32(encoded, 0x7DD062A8);
appendLittleEndian32(encoded, 0xD7C7661E);
appendLittleEndian32(encoded, 0xA99DF722);
appendLittleEndian32(encoded, 0xB4590DF9);
appendLittleEndian32(encoded, 0xB7629496);
appendLittleEndian32(encoded, 0x484E64E3);
appendLittleEndian32(encoded, 0xE1F6014D); // unchanged
appendLittleEndian32(encoded, 0x6BAC9F42);
appendLittleEndian32(encoded, 0x281980F0);
appendLittleEndian32(encoded, 0x05AC0293);
appendLittleEndian32(encoded, 0xEA4382A3);
appendLittleEndian32(encoded, 0xF5B0992B);
appendLittleEndian16(encoded, 0x66FC);
```

### 替换值

```cpp
appendLittleEndian32(encoded, 0x6D8F0118);
appendLittleEndian32(encoded, 0x78DF7BDD);
appendLittleEndian32(encoded, 0xC8C15307);
appendLittleEndian32(encoded, 0x8EB6D174);
appendLittleEndian32(encoded, 0x47FE0464);
appendLittleEndian32(encoded, 0x03D453F6);
appendLittleEndian32(encoded, 0xFACB6000);
appendLittleEndian32(encoded, 0xD1D9C90C);
appendLittleEndian32(encoded, 0x9B7D3BBB);
appendLittleEndian32(encoded, 0xE64781A8);
appendLittleEndian32(encoded, 0x485E44F9);
appendLittleEndian32(encoded, 0xE1F6014D); // unchanged
appendLittleEndian32(encoded, 0x6BAC9F42);
appendLittleEndian32(encoded, 0x281980F0);
appendLittleEndian32(encoded, 0x05AC0293);
appendLittleEndian32(encoded, 0xEA4382A3);
appendLittleEndian32(encoded, 0xF5B0992B);
appendLittleEndian16(encoded, 0x66FC);
```


## 结果

使用已知的私钥生成自己的离线授权码了，对应文件 **Snipaste_pubkey.exe**

# 参考

- [
Snipaste v2.11.3 离线授权分析](https://www.52pojie.cn/forum.php?mod=viewthread&tid=2114393)

- [Snipaste-2.10.8-x64 离线激活记录](https://www.cnblogs.com/DirWang/p/19258416)