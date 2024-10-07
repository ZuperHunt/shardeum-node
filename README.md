Penulis: [Naufal](https://x.com/0xfal)

> [!NOTE]
> **WHAT IS Shardeum?**\
> .

# Tutorial Shardeum Atomium Node

## 1. Needs

### 1.1 Computer

Kamu bisa gunakan VPS atau PC pribadi dengan kebutuhan:

| ✅ Linux | ✅ macOS | ✅ Windows (WSL) |
| ------------- | ------------- | ------------- |

| Part | Minimum | Recommended |
| ------------- | ------------- | ------------- |
| CPU | 2 Cores | 4 Cores |
| RAM | 8 GB | 16 GB |
| SSD | 250 GB | - |

Tutorial ini dibuat menggunakan Linux (Ubuntu), untuk sistem operasi lainnya mungkin akan sedikit berbeda.

## 2. Dependencies

### 2.1 Install Curl

```
sudo apt-get install curl
```

### 2.2 Install Docker

```
sudo apt update
sudo apt install docker.io
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

## 3. Executions

### 3.1 Download Validator

```
curl -O https://raw.githubusercontent.com/shardeum/validator-dashboard/main/installer.sh && chmod +x installer.sh
```

### 3.2 Install Validator

```
./installer.sh
```
Dengan menjalankan perintah di atas, akan muncul beberapa pertanyaan pengaturan, cukup tekan `enter` pada keyboard untuk mengisi secara default.
Kalian akan ditanya `Do you want to run the web based Dashboard? (Y/n)`, jawab saja `Y`, dan buat password.

Proses instalasi akan memakan waktu, tunggu saja sampai prosesnya selesai.

### 3.3 Set up Wallet and Stake SHM

Buka Shardeum Dashboard di browser dengan mengunjungi link di bawah ini, `<YOUR_VPS_IP>` sesuai punyamu.
```
https://<YOUR_VPS_IP>:8080/maintenance
```
Hubungkan wallet EVM (rekomendasi: gunakan Rabby / MetaMask), stake minimal 10 SHM (klaim SHM di [faucet](https://docs.shardeum.org/docs/faucet/claim)).

> [!NOTE]
> Saat staking, ubah gas menjadi `Instant` untuk menghindari macet transaksi.

![{C04ECFAB-BA83-4F7C-AE96-BBAD64CE1349}](https://github.com/user-attachments/assets/304ef408-55ff-4d92-8860-44cafb2c045a)

### 3.4 Start Validator

Tinggal tekan tombol `Stark Node` sampai statusnya hijau, node akan standby sampai terpilih karena validating dipilih secara acak.

### 3.5 Verify Validator Quest

[Verify here](https://shardeum.org/incentivized-testnet/validator), node setup is successful only when you enter `On Standby` or `Validating` status.

> [!WARNING]
> Terkadang, UI-nya akan menampilkan node kalian `Stopped`, coba refresh halaman browser beberapa kali sampai benar-benar yakin kalau node-nya beneran mati.
> Karena traffic yang padat, mengakibatkan hal ini, yang mungkin harusnya berstatus `On Standby` malah `Stopped`.

![image](https://github.com/user-attachments/assets/308a395e-b482-4180-856d-dbfd888f6292)

# Help

## Validator installation stucks (step 3.2)?

`ctrl` + `c` untuk berhenti, ulangi instalnya.

## How to clean up my Shardeum old files?

```
cd ~/.shardeum
./cleanup.sh
cd ~/
rm -rf .shardeum
rm installer.sh
```

## How to fix Docker container issue?

```
docker system prune
```

---

Reach us if you have more question:\
ZuperHunt's [Discord server](https://discord.gg/ZuperHunt) | [X(Twitter)](https://twitter.com/ZuperHunt)

# Acknowledgements

* [Shardeum Documentation](https://docs.shardeum.org/docs/node/run/validator)
