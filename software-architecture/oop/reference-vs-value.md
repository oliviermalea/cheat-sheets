# Reference type vs. Value type

## Concept : Heap and Stack allocation in memory

The heap is most often used for data that has a longer life, meaning that it is able to have more than one variable pointing to the same referenced data.

The stack is where short-living data are stored like *Stucts, int32, DateTime and Double*.

## Reference Types

A ref. type variable contains a ref. to data stored in memory (heap), **Objects** are example of ref types.

If two variables are equals as ref type, it means they are pointing to the same object in memory, as an obvious result, change one will change the data in memory and the other object.

```c#
class ReferenceTypeExample 
{
	static void Enroll(Student student)
	{
		student.Enrolled = true; // This changes the student variable that was passed in outside of the method.
		student = new Student(); // This does not change the student variable outside of the method but creates a new reference. Since student now points to a new reference, the student variable outside of the method is no longer affected after this line.
		student.Enrolled = false; // This changes the local student inside the method.
	}

	static void Main()
	{
		var student = new Student
		{
			Name = "Susan",
			Enrolled = false
		};

		Enroll(student);

		// student.Name is still Susan
		// student.Enrolled is now true
	}
}

public class Student {
	public string Name {get;set;}
	public bool Enrolled {get;set;}
}
```

## Value Types

A value type variable is the immutable data stored in memory (no reference), it has short lives and is typically stored in the stack memory.

```c#
class ReferenceTypeExample 
{
	static void Enroll(bool enrollmentStatus)
	{
		// This will not change any value outside the method.
		enrollmentStatus = true;
	}

	static void Main()
	{
		var student = new Student
		{
			Name = "Susan",
			Enrolled = false
		};

		Enroll(student.Enrolled);
		// student.Enrolled still equals false.
	}
}

public class Student {
	public string Name {get;set;}
	public bool Enrolled {get;set;}
}
```

## Modifiers : ref, in and out

- ref is used to state that the parameter passed may be modified by the method.
- in is used to state that the parameter passed cannot be modified by the method.
- out is used to state that the parameter passed must be modified by the method.

Both the ref and in require the parameter to have been initialized before being passed to a method. The out modifier does not require this and is typically not initialized prior to being used in a method.