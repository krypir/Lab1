
from typing import Generic, TypeVar, List, Optional
T = TypeVar('T')
class Stack(Generic[T]):
    def __init__(self) -> None:
        self._items: List[T] = []
    def push(self, item: T) -> None:
        self._items.append(item)
    def pop(self) -> T:
        if self.is_empty():
            raise IndexError("pop from empty stack")
        return self._items.pop()
    def peek(self) -> T:
        if self.is_empty():
            raise IndexError("peek from empty stack")
        return self._items[-1]
    def is_empty(self) -> bool:
        return len(self._items) == 0
    def size(self) -> int:
        return len(self._items)
    def __repr__(self) -> str:

class Queue(Generic[T]):
    def __init__(self) -> None:
        self._items: List[T] = []
    def enqueue(self, item: T) -> None:
        self._items.append(item)    
    def dequeue(self) -> T:
        if self.is_empty():
            raise IndexError("dequeue from empty queue")
        return self._items.pop(0)
    def front(self) -> T:
        if self.is_empty():
            raise IndexError("front of empty queue")
        return self._items[0]
    def is_empty(self) -> bool:
        return len(self._items) == 0
    def size(self) -> int:
        return len(self._items)
    def __repr__(self) -> str:
        return f"Queue({self._items})"
