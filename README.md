# 6.
import time
from contextlib import contextmanager
class cm_timer_1:
    def __enter__(self):
        self.start_time = time.time()
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        end_time = time.time()
        elapsed_time = end_time - self.start_time
        print(f"time: {elapsed_time:.1f}")
 
if __name__ == "__main__":
    from time import sleep

    with cm_timer_1():
        sleep(5.5)

@contextmanager
def cm_timer_2():
    start_time = time.time()
    yield
    end_time = time.time()
    elapsed_time = end_time - start_time
    print(f"time: {elapsed_time:.1f}")

# Пример использования
if __name__ == "__main__":
    from time import sleep

    with cm_timer_2():
        sleep(5.5)
