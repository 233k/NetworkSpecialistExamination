# RAM (Random Access Memory)
## RAM とは

コンピュータシステムにおけるメモリの一種

- DRAM
- SRAM

が存在する.

||Volatile|R/W IO|Power|Cost|
|-|-|-|-|-|
|DRAM|Volatile|Slow|Large|High|
|SRAM|Nonvolatile|Fast|Small|Low|
 
※ volatile：揮発性

### DRAM (Dynamic RAM)
DRAMに限らず、メモリが "0", "1"の情報を蓄える部分を「メモリセル」という.

DRAMは複数のDRAMメモリセルで構成される.また,DRAMメモリセルは1個のトランジスタと1個のコンデンサから構成される.

時間経過に伴いコンデンサから電荷がリークするため再書き込みする. この再書き込みをリフレッシュといい,1秒間に数十回の頻度で行われる.

#### 主な用途
- パソコンや周辺機器などのメインメモリ
- グラフィックスカードのビデオメモリ
- ハードディスクドライブのバッファメモリ

### SRAM (Static RAM)
SRAMのメモリセルは4~6個のトランジスタからなるフリップフロップ回路メモリセルがで構成される.

記憶素子として磁性体を用いる MRAM も SRAM の一種.

#### 用途
- CPUとDRAMの間のキャッシュメモリ

## RAM の計算
### アドレス線が10本の場合のDRAM 
DRAMメモリセルは格子状に並んでおり、この位置はROWアドレスとColumnアドレスで表される.

一般に10本のアドレス線と書かれた場合には、どちらも10本を意味し、その容量は

2^10 * 2^10 = 2^20

で、1M word

# 参考
- http://mh.rgr.jp/memo/mp0024.htm
- http://ifdl.jp/akita/class_old/old/04/lsi/11.html