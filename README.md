# Arcium Node Auto Installer

<div align="center">

![Arcium](https://img.shields.io/badge/Arcium-Node-blue)
![Version](https://img.shields.io/badge/version-1.0.0-green)
![License](https://img.shields.io/badge/license-MIT-orange)

**Automation script untuk setup Arcium Node dengan mudah dan cepat!**

[Telegram Channel](https://t.me/dasarpemulung) • [Telegram Group](https://t.me/parapemulung)

</div>

---

## 📋 Daftar Isi

- [Fitur](#-fitur)
- [Requirements](#-requirements)
- [Instalasi](#-instalasi)
- [Cara Menggunakan](#-cara-menggunakan)
- [Menu](#-menu)
- [Troubleshooting](#-troubleshooting)
- [Kontak](#-kontak)

---

## ✨ Fitur

Script ini mengotomasi seluruh proses setup Arcium Node dengan fitur:

### 🚀 Setup Otomatis
- ✅ Auto-install semua dependencies (Rust, Solana CLI, Docker, Node.js, Yarn, Arcium CLI)
- ✅ Auto-detect public IP address
- ✅ Auto-generate keypairs (node, callback, identity)
- ✅ Import existing keypairs (opsional)
- ✅ Auto-funding dengan devnet SOL
- ✅ Auto-initialize node accounts on-chain
- ✅ Auto-generate config file
- ✅ One-command Docker deployment

### 📊 Monitoring & Maintenance
- ✅ Background monitoring service
- ✅ Auto-refill SOL ketika balance rendah
- ✅ Auto-restart Docker container jika crash
- ✅ Health check setiap 5 menit
- ✅ Real-time logs monitoring

### 🔧 Cluster Management
- ✅ Create cluster baru
- ✅ Join existing cluster
- ✅ Auto-accept cluster invitations

### 📈 Status & Logs
- ✅ Check node status & balance
- ✅ View Docker logs
- ✅ Node info from blockchain
- ✅ Monitoring service status

---

## 💻 Requirements

### Sistem Operasi
- Ubuntu 20.04 LTS atau lebih baru
- Debian 11 atau lebih baru
- Linux distro lain dengan `apt` package manager

### Spesifikasi Minimum
- CPU: 2 cores
- RAM: 4GB
- Storage: 20GB
- Internet: Koneksi stabil

### Akses
- User dengan sudo privileges
- Port 8080 harus terbuka (untuk komunikasi antar node)

---

## 📥 Instalasi

### Method 1: Menggunakan `curl`

```bash
curl -sO https://raw.githubusercontent.com/dwisyafriadi2/arciumnode-autoinstaller/main/arcium-autoinstaller.sh
chmod +x arcium-autoinstaller.sh
./arcium-autoinstaller.sh
```

### Method 2: Menggunakan `wget`

```bash
wget https://raw.githubusercontent.com/dwisyafriadi2/arciumnode-autoinstaller/main/arcium-autoinstaller.sh
chmod +x arcium-autoinstaller.sh
./arcium-autoinstaller.sh
```

### Method 3: Clone Repository

```bash
git clone https://github.com/dwisyafriadi2/arciumnode-autoinstaller.git
cd arciumnode-autoinstaller
chmod +x arcium-autoinstaller.sh
./arcium-autoinstaller.sh
```

---

## 🎯 Cara Menggunakan

### Setup Node Pertama Kali

1. **Jalankan script**
   ```bash
   ./arcium-autoinstaller.sh
   ```

2. **Pilih Menu 1: Setup Node**
   - Script akan otomatis install semua dependencies
   - Generate keypairs baru
   - Detect IP public
   - Fund accounts dengan devnet SOL
   - Initialize node on-chain
   - Deploy Docker container

3. **Start Monitoring (Recommended)**
   - Pilih Menu 3: Start Monitoring
   - Service akan jalan di background
   - Auto-refill SOL & restart node jika needed

4. **Join/Create Cluster**
   - Pilih Menu 4: Join/Create Cluster
   - Follow instruksi untuk join atau create cluster

### Import Existing Keys

Jika sudah punya keypairs sebelumnya:

1. **Pilih Menu 2: Import Existing Keys**
2. Masukkan path ke file keypairs:
   - `node-keypair.json`
   - `callback-kp.json`
   - `identity.pem`
3. Lanjutkan dengan Menu 1 untuk complete setup

---

## 📖 Menu

```
╔════════════════════════════════════════╗
║     Arcium Node Automation v1.0.0      ║
╚════════════════════════════════════════╝

1. Setup Node (Pertama kali)
2. Import Existing Keys
3. Start Monitoring
4. Join/Create Cluster
5. View Status & Logs
6. Stop Node
7. Uninstall Node Arcium
0. Exit
```

### Penjelasan Menu:

| Menu | Fungsi | Kapan Digunakan |
|------|--------|-----------------|
| **1** | Setup node lengkap dari awal | Pertama kali install |
| **2** | Import keypairs yang sudah ada | Sudah punya keys sebelumnya |
| **3** | Start background monitoring | Setelah node running |
| **4** | Cluster management | Join atau create cluster |
| **5** | Lihat status & logs | Monitoring node |
| **6** | Stop node & monitoring | Maintenance atau troubleshoot |
| **7** | Uninstall semua | Hapus node dari server |

---

## 🔍 Troubleshooting

### Error: "Solana CLI is not installed"

**Solusi:**
```bash
source ~/.bashrc
./arcium-autoinstaller.sh
```

### Error: "Docker permission denied"

**Solusi:**
```bash
sudo usermod -aG docker $USER
# Logout dan login kembali
```

### Error: "Airdrop failed"

**Solusi:**
- Gunakan web faucet: https://faucet.solana.com/
- Paste public key dari script output
- Request SOL manually

### Node tidak start setelah deploy

**Check logs:**
```bash
docker logs arx-node
```

**Restart node:**
```bash
docker restart arx-node
```

### Monitoring tidak jalan

**Check status:**
```bash
ps aux | grep monitor
```

**Restart monitoring:**
- Pilih Menu 6 (Stop)
- Pilih Menu 3 (Start Monitoring)

---

## 📁 File Structure

Setelah setup, file akan tersimpan di:

```
~/arcium-node-setup/
├── node-keypair.json          # Node authority keypair
├── callback-kp.json           # Callback authority keypair
├── identity.pem               # Identity keypair
├── node-config.toml           # Node configuration
├── arx-node-logs/             # Log directory
│   └── arx.log               # Node logs
├── monitor.log                # Monitoring logs
├── .node_pubkey              # Node public key
├── .callback_pubkey          # Callback public key
├── .node_offset              # Node offset ID
└── .public_ip                # Public IP address
```

---

## 🔐 Keamanan

⚠️ **PENTING: Jaga Keamanan Keypairs!**

- **JANGAN** share keypairs dengan siapapun
- **BACKUP** semua keypairs ke tempat aman
- **ENKRIPSI** backup files
- **GUNAKAN** password yang kuat jika menyimpan di cloud

### Backup Keypairs:

```bash
# Backup ke directory terpisah
mkdir -p ~/arcium-backup
cp ~/arcium-node-setup/*.json ~/arcium-backup/
cp ~/arcium-node-setup/*.pem ~/arcium-backup/

# Buat archive terenkripsi (opsional)
tar -czf arcium-backup.tar.gz ~/arcium-backup/
```

---

## 🔄 Update Script

Untuk update ke versi terbaru:

```bash
cd ~/arciumnode-autoinstaller
git pull
chmod +x arcium-autoinstaller.sh
./arcium-autoinstaller.sh
```

Atau download ulang:

```bash
curl -sO https://raw.githubusercontent.com/dwisyafriadi2/arciumnode-autoinstaller/main/arcium-autoinstaller.sh
chmod +x arcium-autoinstaller.sh
```

---

## 📊 Monitoring Commands

### Check Node Status
```bash
# Via script
./arcium-autoinstaller.sh
# Pilih Menu 5

# Manual
docker ps | grep arx-node
docker logs -f arx-node
```

### Check Balances
```bash
solana balance $(cat ~/arcium-node-setup/.node_pubkey) -u devnet
solana balance $(cat ~/arcium-node-setup/.callback_pubkey) -u devnet
```

### Check Node Info
```bash
NODE_OFFSET=$(cat ~/arcium-node-setup/.node_offset)
arcium arx-info $NODE_OFFSET --rpc-url https://api.devnet.solana.com
arcium arx-active $NODE_OFFSET --rpc-url https://api.devnet.solana.com
```

---

## 🆘 Mendapatkan Bantuan

### Community Support

- **Telegram Channel**: [@dasarpemulung](https://t.me/dasarpemulung)
- **Telegram Group**: [@parapemulung](https://t.me/parapemulung)

### Official Resources

- **Arcium Docs**: [docs.arcium.com](https://docs.arcium.com/)
- **Arcium Discord**: [discord.gg/arcium](https://discord.gg/arcium)

### Report Issues

Jika menemukan bug atau error:

1. **GitHub Issues**: [Report Issue](https://github.com/dwisyafriadi2/arciumnode-autoinstaller/issues)
2. Sertakan:
   - Error message lengkap
   - OS & version (`uname -a`)
   - Script output
   - Docker logs (`docker logs arx-node`)

---

## 🙏 Credits

- **Script Developer**: [@dasarpemulung](https://t.me/dasarpemulung)
- **Arcium Network**: [arcium.com](https://arcium.com)
- **Community**: Dasar Pemulung

---

## 📝 License

MIT License - Feel free to use and modify!

---

## ⭐ Support

Jika script ini membantu, berikan **⭐ Star** di GitHub!

```bash
https://github.com/dwisyafriadi2/arciumnode-autoinstaller
```

---

## 🚀 Quick Start Summary

```bash
# 1. Download script
curl -sO https://raw.githubusercontent.com/dwisyafriadi2/arciumnode-autoinstaller/main/arcium-autoinstaller.sh

# 2. Make executable
chmod +x arcium-autoinstaller.sh

# 3. Run
./arcium-autoinstaller.sh

# 4. Pilih Menu 1 untuk setup
# 5. Pilih Menu 3 untuk monitoring
# 6. Done! ✅
```

---

<div align="center">

**Happy Node Running! 🎉**

Made with ❤️ by Dasar Pemulung Community

</div>
