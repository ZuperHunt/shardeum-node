Penulis:
[Naufal](https://x.com/0xfal)

> [!NOTE]
> **WHAT IS Shardeum?**\
> .

# Tutorial Shardeum Validator Node

Sebelum ke tutorialnya, kalo kamu belum ngerti gimana cara terhubung ke VPS mu, bisa lihat tutorial yang sudah kami buat [di sini](https://github.com/ZuperHunt/Connect-to-VPS).

## 1. Needs

Kamu bisa gunakan VPS atau PC pribadi dengan kebutuhan:

| ✅ Linux | ✅ macOS | ✅ Windows (WSL) |
| ------------- | ------------- | ------------- |

| Part | Minimum | Recommended |
| ------------- | ------------- | ------------- |
| CPU | 1 Core | 4 Cores |
| RAM | 2 GB | 4 GB |
| SSD | 80 GB | - |

Tutorial ini dibuat menggunakan Linux (Ubuntu), untuk sistem operasi lainnya mungkin akan sedikit berbeda.

## 2. Dependencies

### 2.1 Install Curl

```
sudo apt install curl
```

### 2.2 Install Docker

```
sudo apt update
sudo apt install docker.io
```

## 3. Executions

### 3.1 Create Firewall (for DigitalOcean user)

Buka halaman [Networking](https://cloud.digitalocean.com/networking/firewalls) di dashboard DigitalOcean mu dan buat Firewall dengan nama `shardeum-validator`, selanjutnya ikuti saja seperti SS di bawah:

![image](https://github.com/user-attachments/assets/05e471e3-bc5d-44dd-856e-7d2088892699)

![image](https://github.com/user-attachments/assets/1631d809-3fa3-4cc4-a1ed-c0fcb96ccd82)

### 3.2 Install Validator

```
curl -O https://raw.githubusercontent.com/shardeum/shardeum-validator/refs/heads/itn4/install.sh && chmod +x install.sh && ./install.sh
```

Dengan menjalankan perintah di atas, akan muncul beberapa pertanyaan pengaturan, cukup tekan `enter` pada keyboard untuk mengisi secara default.
Kalian akan ditanya `Do you want to run the web based Dashboard? (Y/n)`, jawab saja `Y`, dan buat password.

Proses instalasi akan memakan waktu, tunggu saja sampai prosesnya selesai.

### 3.3 Set up Wallet and Stake SHM

Buka Shardeum Dashboard di browser dengan mengunjungi link di bawah ini, `<YOUR_VPS_IP>` sesuai punyamu.
```
https://<YOUR_VPS_IP>:8080
```
Hubungkan wallet EVM (rekomendasi: gunakan Rabby / MetaMask), stake minimal 10 SHM (klaim SHM di [faucet](https://docs.shardeum.org/docs/faucet/claim)).

> [!NOTE]
> Saat staking, ubah gas menjadi `Instant` (atau mentok kanan) untuk menghindari macet transaksi.

![{C04ECFAB-BA83-4F7C-AE96-BBAD64CE1349}](https://github.com/user-attachments/assets/304ef408-55ff-4d92-8860-44cafb2c045a)

### 3.4 Start Node

Tinggal tekan tombol `Start Node`, node akan standby sampai terpilih karena validating dipilih secara acak.

![image](https://github.com/user-attachments/assets/308a395e-b482-4180-856d-dbfd888f6292)

> [!WARNING]
> Terkadang, UI-nya akan menampilkan node kalian `Stopped`, coba refresh halaman browser beberapa kali sampai benar-benar yakin kalau node-nya beneran mati.
> Karena traffic yang padat, mengakibatkan hal ini, yang mungkin harusnya berstatus `On Standby` malah `Stopped`.

### 3.5 Verify Validator Quest

[Verify here](https://shardeum.org/incentivized-testnet/validator), node setup is successful only when you enter `On Standby` or `Validating` status.

# Help

## Validator installation stucks (step 3.2)?

`ctrl` + `c` untuk berhenti, ulangi instalnya.

## How to use the CLI commands?

Kamu perlu menjalankan `shell.sh`, lokasinya ada di dalam folder `shardeum`.

```
cd ~/shardeum
./shell.sh
```

**Jika** tidak bisa menggunakan perintah di atas bisa menggunakan perintah ini (di beberapa versi mungkin berbeda cara)

```
cd /home/root/shardeum
./shell.sh
```

## How to clean up my Shardeum old files (uninstall node)?

```
cd ~/
rm -rf shardeum
rm -rf installer.sh
```

**Jika** tidak bisa menggunakan perintah di atas bisa menggunakan perintah ini (di beberapa versi mungkin berbeda cara)

```
cd /home/root
rm -rf shardeum
rm -rf installer.sh
```

## How to update my node?

Read how to use [the CLI commands](#How-to-use-the-CLI-commands) first

```
operator-cli stop
operator-cli version
operator-cli update
operator-cli start
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
