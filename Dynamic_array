import ctypes

class Mylist:
    def __init__(self):
        self.n = 0
        self.size = 1
        self.A = self._make_array(self.size)

    def _make_array(self,capacity):
        return (capacity*ctypes.py_object)()
    

    def append(self,item):
        if (self.n == self.size):
            self._resize(2*self.size)

        self.A[self.n] = item
        self.n += 1

    def _resize(self,new_capacity):

        #Making temporary array
        B = self._make_array(new_capacity)
        self.size = new_capacity

        for i in range(self.n):
            B[i] = self.A[i]

        self.A = B

    def __len__(self):
        return self.n

    def __getitem__(self,index):

        if(0 <= index <= self.n):
            return self.A[index]
        else:
            return "Index Error"


    def __str__(self):

        temp=""
        for i in range(self.n):
            temp=temp+str(self.A[i])+","

        return temp



    def insert(self,index,value):
        if (0 <= index <= self.n):
            if( self.n == self.size ):
                self._resize(2*self.size)

            for i in range(self.n-1,index-1,-1):
                self.A[i+1] = self.A[i]

            self.A[index] = value
            self.n += 1
        else:
            return "Index Error"

    def __delitem__(self,index):
        if (0 <= index <= self.n):
            for i in range(index,self.n-1):
                self.A[i] = self.A[i+1]

            self.n -= 1

        else:
            return "Index Error"
        

    def remove(self,value):
        flag=0
        for i in range(self.n):
            if self.A[i] == value:
                flag = 1
                for j in range(i,self.n-1):
                    self.A[j] = self.A[j+1]

                self.n =self.n - 1
                break
        if flag==0:
            return "Not found"

    def pop(self):
        self.n -= 1


    def clear(self):
        self.n=0
        self.size=1

    def find(self,value):
        flag=0
        for i in range(self.n):
            if (self.A[i]== value):
                flag=1
                return i
                #break
            #return i
        if flag==0:
            return "Not Found"
        #else:
         #   return i
            
################################################################################
arr=Mylist()
arr.append(10)
arr.append(20)
arr.append(30)
arr.append(40)
arr.append(50)
arr.append(60)


#arr.getitem(2)
print(arr)
print(len(arr))
print(arr[2])

print("Inserting")
arr.insert(2,100)
print(arr)

print("Deleting by index 4")
del arr[4]
print(arr)

print("Removing value 20")
arr.remove(20)
print(arr)


print(arr.find(100))
arr.find(400)



