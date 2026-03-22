# 📶 NetPulse

> A real-time browser-based network quality monitor that classifies your connection as **5G-like**, **4G-like**, **Fluctuating**, or **Offline** — all from a single HTML file, no dependencies, no installs.

---

## ✨ Features

- **Live latency measurement** — pings a lightweight endpoint every 8 seconds and tracks response time
- **Smart classification** — labels your connection as 5G / Fluctuating / 4G / Offline based on configurable thresholds
- **Latency chart** — scrolling sparkline showing the last 40 readings with color-coded data points
- **Stats panel** — current, average, and best latency at a glance
- **Switch log** — timestamped history of every network type change
- **Browser notifications** — get alerted the moment your signal drops or improves (opt-in)
- **Adjustable thresholds** — drag sliders to tune what counts as "5G" or "4G" for your environment
- **Zero dependencies** — pure HTML, CSS, and vanilla JavaScript; works offline-first after first load

---

## 🚀 Getting Started

No build step. No npm. Just open the file.

```bash
git clone https://github.com/YOUR_USERNAME/netpulse.git
cd netpulse
# Open index.html in any modern browser
open index.html
```

Or host it instantly:

```bash
npx serve .
```

---

## 📸 Preview

| 5G-like | Fluctuating | 4G-like | Offline |
|---------|-------------|---------|---------|
| 🟢 Fast | 🔵 Moving between bands | 🟠 Slower | 🔴 No connection |

---

## 🛠 How It Works

NetPulse fetches a 204-byte no-content response from Google's `gstatic.com` endpoint and measures the round-trip time using the browser's `performance.now()` API. It does **not** use the `navigator.connection` API (which is unreliable and often shows stale data) — instead it derives signal quality purely from measured latency.

| Classification | Default Threshold |
|----------------|-------------------|
| 5G-like | < 50 ms |
| Fluctuating | 50 – 65 ms |
| 4G-like | > 65 ms |
| Offline | Request failed |

Thresholds are fully adjustable via the sliders at the bottom of the app.

---

## 📂 File Structure

```
netpulse/
└── index.html   # Entire app — self-contained single file
```

---

## 🔔 Browser Notifications

Click **"Enable browser notifications"** to receive an alert whenever your connection type changes. Useful if you're running NetPulse in a background tab while working.

---

## 🌐 Browser Support

Works in all modern browsers that support the Fetch API and `performance.now()`:

- Chrome / Edge 80+
- Firefox 75+
- Safari 14+

---

## 📄 License

MIT — free to use, modify, and distribute.

---

## 🤝 Contributing

Pull requests are welcome! Some ideas for contributions:

- [ ] Export latency history as CSV
- [ ] Dark / light theme toggle
- [ ] Custom ping endpoint support
- [ ] PWA support with service worker
- [ ] Mobile app wrapper (Capacitor / Tauri)

---

> Built with ❤️ using zero dependencies. If NetPulse helped you, give it a ⭐!
