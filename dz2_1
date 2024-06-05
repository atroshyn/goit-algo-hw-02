import queue
import threading
import time
import random

# Створити чергу заявок
request_queue = queue.Queue()

# Унікальний ідентифікатор для заявок
request_id = 0

# Функція для генерування нових заявок
def generate_request():
    global request_id
    while True:
        request_id += 1
        request = f"Request-{request_id}"
        request_queue.put(request)
        print(f"Generated {request}")
        time.sleep(random.uniform(0.5, 2))  # Імітація часу для генерування нової заявки

# Функція для обробки заявок
def process_request():
    while True:
        if not request_queue.empty():
            request = request_queue.get()
            print(f"Processing {request}")
            # Імітація часу обробки заявки
            time.sleep(random.uniform(1, 3))
            print(f"Finished processing {request}")
            request_queue.task_done()
        else:
            print("Queue is empty, waiting for new requests...")
            time.sleep(1)  # Час очікування до наступної перевірки черги

# Створення потоків для генерування та обробки заявок
generator_thread = threading.Thread(target=generate_request)
processor_thread = threading.Thread(target=process_request)

# Запуск потоків
generator_thread.start()
processor_thread.start()

# Зупинка потоків при завершенні програми (наприклад, через KeyboardInterrupt)
try:
    generator_thread.join()
    processor_thread.join()
except KeyboardInterrupt:
    print("Program interrupted.")
    generator_thread.join()
    processor_thread.join()
