

## Prerequisites

- Python $\geq$ 3.8
- Docker

## Installation



1. **Install the required Python packages:**

   ```bash
   pip install -r requirements.txt
   ```

## Benchmark Directory Structure

Each benchmark directory should follow this structure:

```
D-Link
├──DIR-806
├───BM-YYYY-XXXXX/        # Benchmark (一个固件版本对应一个benchmark)
│   └──auth/              # Authentication related files           
│   │   └── update.py     # Authentication update script
│   └──emulation/         # Emulation related files
│       ├── firmware/     # Firmware files directory
│       │     └── wr940nv4_us_3_...  # Firmware file
│       ├── Dockerfile    # Docker configuration
│       └── run.sh        # Emulation run script
└── benchmark.yml         # Benchmark configuration file
```

**Note:** The `auth` directory is optional and only needed if the firmware requires authentication.

## Usage

1. **Prepare your benchmark configuration:**

   Ensure you have a `benchmark.yml` file in your benchmark directory. This file should contain the necessary configuration for building and running the Docker container.

2. **Run the script (use `sudo` if necessary):**

   ```bash
   sudo python3 emulation.py -b <path-to-benchmark-directory>
   ```

   Replace `<path-to-benchmark-directory>` with the path to your benchmark directory containing the `benchmark.yml` file.

   For example:

   ```bash
   sudo python3 emulation.py -b ./D-Link/DIR-806/ICS-BM-0001
   ```



