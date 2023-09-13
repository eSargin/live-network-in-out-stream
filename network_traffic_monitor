import psutil
import time
import sys

# coded by smokinyazilim.com @eSargin


def format_traffic(traffic_bytes):
    if traffic_bytes >= 1024 ** 3:  # 1 GB ve üzeri
        return f"{traffic_bytes / (1024 ** 3):.2f} GB"
    elif traffic_bytes >= 1024 ** 2:  # 1 MB ve üzeri
        return f"{traffic_bytes / (1024 ** 2):.2f} MB"
    else:
        return f"{traffic_bytes / 1024:.2f} KB"


def print_network_usage():
    prev_down_traffic = 0
    prev_up_traffic = 0

    # 1 Gbit/s hızına eşdeğer veri transferi (1 Gbit = 125 MB)
    one_gbit_bytes = 125 * (1024 ** 2)

    while True:
        net_io = psutil.net_io_counters()

        # Sunucuya gelen trafik (downstream)
        down_traffic = net_io.bytes_recv

        # Sunucudan çıkan trafik (upstream)
        up_traffic = net_io.bytes_sent

        down_diff = down_traffic - prev_down_traffic
        up_diff = up_traffic - prev_up_traffic

        formatted_diff_down = format_traffic(down_diff)
        formatted_diff_up = format_traffic(up_diff)

        sys.stdout.write(f"\rin/out: {formatted_diff_down}/{formatted_diff_up}")
        sys.stdout.flush()

        prev_down_traffic = down_traffic
        prev_up_traffic = up_traffic

        time.sleep(1)


if __name__ == "__main__":
    try:
        print_network_usage()
    except KeyboardInterrupt:
        print("\nStopped.")
