import socket
import threading

def scan_port(target, port):
    try:
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.settimeout(1)
        result = sock.connect_ex((target, port))
        if result == 0:
            print(f"Port {port} is open")
        sock.close()
    except Exception as e:
        print(f"Error: {e}")

def main():
    target = input("Enter target IP address: ")
    start_port = int(input("Enter starting port number: "))
    end_port = int(input("Enter ending port number: "))

    print(f"Scanning target {target} from port {start_port} to port {end_port}...")

    for port in range(start_port, end_port + 1):
        threading.Thread(target=scan_port, args=(target, port)).start()

if __name__ == "__main__":
    main()
