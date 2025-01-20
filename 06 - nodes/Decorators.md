#coding/python 

Modify behavior of a function without modifying the function.

```python
from datetime import datetime
import time

def logger(func):
	def wrapper():
	print("-"*50)
	print("> Execution started {}".format(datetime.today().strftime("%Y-%m-%d %H:%M:%S")))
	func()
	print("> Execution completed {}".format(datetime.today().strftime("%Y-%m-%d %H:%M:%S")))
		print("-"*50)
	return wrapper

@logger
def demo_function():
	print("Executing task!")
	time.sleep(3)
	print("Task completed!")

demo_function()

```