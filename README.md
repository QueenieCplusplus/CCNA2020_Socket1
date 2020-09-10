# CCNA2020_Socket1
不同主機在同一網路間的通訊

# MAC Frame Format

目的地位址與來源位址皆為網卡硬體位址即網卡卡號 NIC ID（獨一無二），一台電腦通常有二片內建網卡。

硬體位址： 00:00:00:00:00:00 到 FF:FF:FF:FF:FF:FF 六對二個16進制位元所組成。

同網路間，來源與目的地的網卡硬體位址不會被改變，然而如果是不同網路間，則會造成機器與機器間要透過其他網路設備的 NIC 硬體位址之間串連，那麼這封包的硬體位址會作相應的改變。

傳遞的資料大小為 46 ~ 1500 bytes（MTU）。


# Communication in Practice

實際的傳輸方式，解析如下：


PC A 擁有兩片 NIC, 假設為 NIC-a1 與 NIC-a0

PC B 擁有兩片 NIC, 假設為 NIC-b3 與 NIC-b2

PC C 擁有兩片 NIC, 假設為 NIC-c4 與 NIC-c5


實際線路串連方式，如下：


         PC-A  NIC-a1 -----(hub)-------  NIC-b2  PC-B  NIC-b3   ------(sw)------  NIC-c4   PC-C
         
傳輸路徑解析：

PC-A 與 PC-C 之間通訊，要通過 PC-B，基於實體線路與實體 Hub 和 Swithcer 阜(網孔)的關係。
而 PC-A 與 PC-B 之間的 frame 來源為 NIC-a1, 目的地為 NIC-b2。
而 PC-B 與 PC-C 之間的 frame 來源為 NIC-b3, 目的地為 NIC-c4。
         
         
         
         


