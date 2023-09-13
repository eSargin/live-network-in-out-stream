# Network Traffic Monitor

This is a Python script that monitors network traffic in real-time using the `psutil` library. It displays incoming (download) and outgoing (upload) network traffic in a human-readable format.

## Prerequisites

Before you can run this script, make sure you have the following prerequisites installed:

- Python 3.x
- [psutil](https://pypi.org/project/psutil/)

You can install `psutil` using pip:

```bash
pip install psutil
```

## Usage

To run the script, simply execute the `network_traffic_monitor.py` file. The script will continuously display incoming and outgoing network traffic in kilobytes (KB), megabytes (MB), or gigabytes (GB) per second.

```bash
python network_traffic_monitor.py
```

To stop the monitoring, press `Ctrl + C`.

## Output

The script displays network traffic in the following format:

```
in/out: XX.XX KB/XX.XX KB
```

Where:
- `in` represents incoming (download) traffic.
- `out` represents outgoing (upload) traffic.
- `XX.XX` represents the amount of traffic in KB, MB, or GB per second, depending on the magnitude of the traffic.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to [smokinyazilim.com](https://smokinyazilim.com) for the initial code.
```
