# STM32-GW-Board Zephyr Project

This repository contains Zephyr-based examples for the STM32 Nucleo G070RB board.

---

## Zephyr SDK Setup & Workflow

### 1️⃣ Update System Packages

```bash
sudo apt update
sudo apt upgrade
```

---

### 2️⃣ Install Required Dependencies

```bash
sudo apt install --no-install-recommends git cmake ninja-build gperf \
  ccache dfu-util device-tree-compiler wget python3-dev python3-venv python3-tk \
  xz-utils file make gcc gcc-multilib g++-multilib libsdl2-dev libmagic1
```

---

### 3️⃣ Verify Tools

```bash
cmake --version
python3 --version
dtc --version
```

---

### 4️⃣ Create Virtual Environment

```bash
python3 -m venv ~/zephyrproject/.venv
source ~/zephyrproject/.venv/bin/activate
```

---

### 5️⃣ Install West

```bash
pip install west
```

---

### 6️⃣ Initialize Zephyr Workspace

```bash
west init ~/zephyrproject
cd ~/zephyrproject
west update
west zephyr-export
west packages pip --install
```

---

### 7️⃣ Install Zephyr SDK (Optional)

```bash
cd ~/zephyrproject/zephyr
west sdk install
```

---

### 8️⃣ Build a Project (Full Path Required)

Example: `hello_world` app

```bash
west build -p always -b nucleo_g070rb project_path/examples/hello_world
```

* `-p always` → forces a clean build
* `-b nucleo_g070rb` → selects board
* **Full path is required** when building outside the Zephyr workspace.

---

### 9️⃣ Flash Firmware

```bash
west flash
```

---

### 📚 Official Documentation

[Zephyr Getting Started Guide](https://docs.zephyrproject.org/latest/develop/getting_started/index.html)