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
| CPU | TBD | TBD |
| RAM | TBD | TBD |
| SSD | TBD | TBD |

Tutorial ini dibuat menggunakan Linux (Ubuntu), untuk sistem operasi lainnya mungkin akan sedikit berbeda.

## 2. Dependencies

### 2.1 Install Curl

```
sudo apt-get install curl
```

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-compose
```

### 2.2 Install Docker

```
sudo apt update
sudo apt install docker.io
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

## 3. Executions

### 3.2 Download Validator

```
curl -O https://raw.githubusercontent.com/shardeum/validator-dashboard/main/installer.sh && chmod +x installer.sh
```

### 3.3 Install Validator

Dengan menjalankan perintah berikut, akan muncul beberapa pengaturan, cukup tekan `enter` pada keyboard untuk mengisi secara default. Step ini akan memakan waktu, tunggu saja sampai proses instalasi selesai.
```
./installer.sh
```

### 3.4 Set up Wallet and Stake SHM

Kunjungi dashboard, ubah `<YOUR_VPS_IP>` sesuai punyamu.
```
https://<YOUR_VPS_IP>:8080/maintenance
```
Hubungkan wallet EVM (rekomendasi: gunakan Rabby), stake SHM minimal 10 ([faucet](https://docs.shardeum.org/docs/faucet/claim)), ubah gwei menjadi custom: 1000.

![image](https://github.com/user-attachments/assets/e45efc4a-29b1-4a74-b1f0-46d30eaa0eae)

### 3.5 Start validator

Tinggal tekan tombol `Stark Node` sampai statusnya hijau, node akan standby sampai terpilih karena validating dipilih secara acak.

![image](https://github.com/user-attachments/assets/8e5bd80f-d7ab-47c5-9d37-ce668f1e7b74)

# Help

## Validator installation stucks (step 3.3)?

`ctrl` + `c` untuk berhenti, ulangi instalnya.

---

Reach us if you have more questions:\
ZuperHunt's [Discord server](https://discord.gg/ZuperHunt) | [X(Twitter)](https://twitter.com/ZuperHunt)

# Acknowledgements

* [Shardeum Documentation](https://docs.shardeum.org/docs/node/run/validator)
