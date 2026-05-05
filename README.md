# 🚀 Port Monitoring & Slack Alert System

A lightweight DevOps monitoring tool to check service availability and send Slack alerts.

---

## 🏗️ Architecture Diagram

```
        +----------------------+
        |   Cron / Service     |
        +----------+-----------+
                   |
                   v
        +----------------------+
        |     monitor.sh       |
        +----------+-----------+
                   |
        +----------+-----------+
        |                      |
        v                      v
+---------------+     +------------------+
| Port Check    |     | notifier.sh      |
| (nc command)  |     | (Slack Alert)    |
+-------+-------+     +--------+---------+
        |                      |
        v                      v
   Service UP/DOWN        Slack Webhook
                               |
                               v
                         +-------------+
                         |   Slack     |
                         +-------------+
```

---

## ⚙️ How It Works

1. Script runs via cron or Linux service  
2. Checks defined ports  
3. If service is DOWN → sends Slack alert  
4. Logs everything locally  

---

## 🚀 Quick Setup

```bash
git clone <repo>
cd port-monitoring-system
bash install.sh
```

### Configure

```bash
cp config/config.example config/config
nano config/config
```

---

## ⚠️ Disclaimer

This project is intentionally kept **simple and easy to use**.

- Just add your **hosts and ports** in the config file  
- Run the script or schedule it  
- Can be easily run as a **Linux service or cron job**  

⚠️ Do NOT commit:
- Real Slack webhook URLs  
- Production IPs or internal hostnames  

---

## ▶️ Run

```bash
bash monitor.sh
```

---

## ⏰ Run as Service (Example)

```bash
crontab -e

*/5 * * * * /path/to/monitor.sh
```

---

## 🔐 Security

- No secrets stored in repo  
- Config separated  
- Safe for GitHub  

---

## 📈 Future Improvements

- Retry logic  
- Alert threshold  
- Email alerts  
- Dashboard UI  

---

## 💡 Use Cases

- Monitor internal services  
- Lightweight alternative to heavy tools  
- Quick DevOps setups  

