# my-first-project
python



import psutil
import subprocess

def check_traffic_threshold(threshold):
    # Отримання інформації про загальний обсяг трафіку
    network_info = psutil.net_io_counters()
    # Перевірка, чи перевищений поріг трафіку
    if network_info.bytes_sent > threshold or network_info.bytes_recv > threshold:
        return True
    return False

def notify_high_traffic():
    # Відкриття вікна блокнота з повідомленням
    subprocess.Popen(['notepad.exe', 'high_traffic.txt'])

if __name__ == "__main__":
    # Встановлення порогу трафіку (в байтах)
    traffic_threshold = 100000000  # Наприклад, 100 МБ
    if check_traffic_threshold(traffic_threshold):
        notify_high_traffic()
