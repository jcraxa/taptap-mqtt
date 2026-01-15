# taptap-mqtt

Docker image for **taptap-mqtt**, intended for use with **Home Assistant Container**  
(**not** Home Assistant OS).

This is not a multi-arch image and runs only on linux/amd64

If there are any updates to the upstream files, re-download the changed files and restart the container.

---

## Requirements

To make this work, you will need the following files:

- `taptap-mqtt.py` from the  
  👉 [TapTap MQTT GitHub Repo](https://github.com/litinoveweedle/taptap-mqtt)

- `config.ini.example` from the same repository  
  👉 [TapTap MQTT GitHub Repo](https://github.com/litinoveweedle/taptap-mqtt)  
  Rename this file to `config.ini` and edit with your configuration

- The `taptap` binary from  
  👉 [TapTap GitHub Repo](https://github.com/litinoveweedle/taptap)

---

## Setup

1. Place all **three files** in the same directory on your host:
   - `taptap-mqtt.py`
   - `config.ini`
   - `taptap`

2. Ensure the `taptap` binary is executable:
   ```bash
   chmod +x taptap
   ```
3. Mount this directory into the container at `/app`.


---

## Installation

### Docker Compose

```yaml
taptap:
  image: ghcr.io/jcraxa/taptap-mqtt:latest
  hostname: taptap-mqtt
  volumes:
    - ~/docker/taptap:/app
  restart: unless-stopped

```

---

## Notes

This image is designed for Home Assistant Container installations. It will not work with Home Assistant OS. Refer to the original [taptap-mqtt](https://github.com/litinoveweedle/taptap-mqtt) for HA OS.

All required files must exist in `/app` inside the container.

Ensure your `config.ini` is correctly configured. Refer to [taptap-mqtt](https://github.com/litinoveweedle/taptap-mqtt)

## Credits

taptap and taptap-mqtt projects by
   👉(https://github.com/litinoveweedle)
