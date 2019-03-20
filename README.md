# BA4318-Homerwork-2
import math

datapoints=[]
n = int(input("Write how many coordinates you are going to choose and tap on enter,continue choosing coordinates with one empty space between the coordinates "))

for i in range(0, n):
    inStr = input("")
    nums = inStr.split(" ")
    datapoints.append((float(nums[0]), float(nums[1])))
    
print("datapoints:", datapoints)    

totalX = 0.0
totalY = 0.0
for i in range(0, n):
    totalX += datapoints[i][0]
    totalY += datapoints[i][1]
    
print("total:", totalX, " ", totalY)   

centerOfMassX = totalX / n 
centerOfMassY = totalY / n

print("center of mass: (", centerOfMassX, ", ", centerOfMassY, ")")   

# Finding Distances
distances=[]
for i in range(0, n):
#for data in datapoints:
    distX = (datapoints[i][0] - centerOfMassX)**2
    distY = (datapoints[i][1] - centerOfMassY)**2
    totalDist = math.sqrt(distX + distY)
    distances.append(totalDist)
   
print("distances:", distances)       
   
# Finding Smallest and Largest Distance
smallIndex = 0
largeIndex = 0
for i in range(0, n):
    if distances[i] < distances[smallIndex]:
        smallIndex = i
    if distances[i] > distances[largeIndex]:
        largeIndex = i
        
print("Smallest Distance is coming from ", datapoints[smallIndex], " which is ", distances[smallIndex])
print("Largest Distance is coming from ", datapoints[largeIndex], " which is ", distances[largeIndex])
