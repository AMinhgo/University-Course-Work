Method 1
```python
#Rooms
RA = 20
RB = 50
RC = 120

def RecRoom(SN):
  A = "Room A is usable"
  B = "Room B is usable"
  C = "Room C is usable"

  if SN < RA:
    return A
  elif SN < RB:
    return B
  else :
    return C
  
StudentNum = 48
Result = RecRoom(StudentNum)
print(Result)
```

Method 2
```python
all_room = {"A":20, "B": 50, "C": 120}
recommended_room = None

def rec_room(SN):
  for room, capacity in all_room.items():
  
    if SN <= capacity:
      recommended_room = room
      if recommended_room is not None:
        print(f"Room {recommended_room} is usable")
      else:
        print("No room is usable")  
      break
  
SN = 48
rec_room(SN)
```