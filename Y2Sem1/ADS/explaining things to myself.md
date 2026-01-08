why use self.x for classes/objects

self. prefix attaches the values to the object itself, without it its just a local variable that disappears after the method ends, not stored on the object so can't be used for later

	class Numbers:
	    def __init__(self, value):
	        self.value = value

	    def addValue(self):
	        return Numbers(self.value + 10)

	    def printValue(self):
	        print(self.value)

		obj1 = Numbers(10)
		obj1.printValue()
		obj2 = obj1.addValue()
		obj1.printValue()
		obj2.printValue()

		[10, 10, 20]



