# Zabbix Trigger Templates

This folder includes trigger configurations used in the monitoring project.

---

## 🔥 Trigger 1: CPU Usage High

- **Name**: High CPU Usage
- **Expression**: `{host:system.cpu.util[,user].last(300)}>80`
- **Severity**: High
- **Description**: Triggers if user CPU usage exceeds 80% in the last 5 minutes.

---

## 💾 Trigger 2: Low Disk Space

- **Name**: Low Free Disk Space on `/`
- **Expression**: `{host:vfs.fs.size[/,pfree].last(300)}<20`
- **Severity**: Warning
- **Description**: Triggers if less than 20% disk space is free on root partition.

---

## 🧠 Trigger 3: Memory Usage

- **Name**: High Memory Usage
- **Expression**: `{host:vm.memory.size[available].last(300)}<512000000`
- **Severity**: Average
- **Description**: Triggers if available RAM drops below 512 MB.

---

## 📨 Trigger 4: Zabbix Agent Unreachable

- **Name**: Zabbix Agent on {HOST.NAME} is unreachable
- **Expression**: `{host:agent.ping.nodata(600)}=1`
- **Severity**: Disaster
- **Description**: Triggers if the agent doesn't respond for 10 minutes.

---

## 💡 Notes

- Replace `host` with the actual hostname or template name.
- These triggers are manually added via:  
  `Configuration > Hosts > Triggers > Create Trigger`
