
from typing import TypeVar, Dict, Any, List

T = TypeVar('T')

def create_stack() -> Dict[str, Any]:
    return {"items": [], "size": 0}

def push(stack: Dict[str, Any], item: Any) -> None:
    stack["items"].append(item)
    stack["size"] += 1

def pop_stack(stack: Dict[str, Any]) -> Any:
    if stack["size"] == 0:
        raise IndexError("pop from empty stack")
    item = stack["items"].pop()
    stack["size"] -= 1
    return item

def peek_stack(stack: Dict[str, Any]) -> Any:
    if stack["size"] == 0:
        raise IndexError("peek from empty stack")
    return stack["items"][-1]

def is_empty_stack(stack: Dict[str, Any]) -> bool:
    return stack["size"] == 0

def get_size_stack(stack: Dict[str, Any]) -> int:
    return stack["size"]


def create_queue() -> Dict[str, Any]:
    return {"items": [], "size": 0}

def enqueue(queue: Dict[str, Any], item: Any) -> None:
    queue["items"].append(item)
    queue["size"] += 1

def dequeue(queue: Dict[str, Any]) -> Any:
    if queue["size"] == 0:
        raise IndexError("dequeue from empty queue")
    item = queue["items"].pop(0)
    queue["size"] -= 1
    return item

def front_queue(queue: Dict[str, Any]) -> Any:
    if queue["size"] == 0:
        raise IndexError("front of empty queue")
    return queue["items"][0]

def is_empty_queue(queue: Dict[str, Any]) -> bool:
    return queue["size"] == 0

def get_size_queue(queue: Dict[str, Any]) -> int:
    return queue["size"]
