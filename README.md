# IT314 : Lab 8 - JUnit Testing

### Name        : Shrey Shah
### Student ID  : 202001431


## Eclipse Project and Package

![8_1](https://user-images.githubusercontent.com/123163386/233597973-b883ec00-91a0-47cf-a6bf-2d4ee2e1e74a.JPG)

## Boa Class
```
package lab8;

//represents a boa constrictor
public class Boa {
	private String name;
	private int length; // the length of the boa, in feet
	private String favoriteFood;
	
	public Boa (String name, int length, String favoriteFood){
		this.name = name;
		this.length = length;
		this.favoriteFood = favoriteFood;
	}
	
	//returns true if this boa constrictor is healthy
	public boolean isHealthy(){
		return this.favoriteFood.equals("granola bars");
	}
	
	//returns true if the length of this boa constrictor is
	//less than the given cage length
	public boolean fitsInCage(int cageLength){
		return this.length < cageLength;	
	}
}

```


## BoaTest JUnit

It is not necessary to develop tests for both ken and jen objects in order to test the fitsInCage() method
because the function is the same for both, and the results of test cases depend only on whether the
specified length is greater than, less than, or equal to the actual length of the object. In both situations, the
behavior will be comparable.
 The @Before annotation ensures that the setUp() method is run before each test method is executed, so the jen and ken objects will be available to all the test methods in the class.

![8_2](https://user-images.githubusercontent.com/123163386/233598736-6e9d413b-5baa-48c8-9ab3-9f803adb6d8f.JPG)

On running the above tests we get a green bar. All possibilities are tested in the testcases.

## Adding New Method in Boa class

```
public int lengthInInches(){
  return this.length*12;
}
```

## Adding New Test in BoaTest class

```
@Test
public void testLengthInInches() {
  assertEquals(24, jen.lengthInInches());
  assertEquals(36, ken.lengthInInches());
}

```

## Test Results
![8_3](https://user-images.githubusercontent.com/123163386/233599327-d3278800-1267-4f79-98ca-74c2f75ab285.JPG)

After running the tests, the JUnit pane displays a green bar indicating that all tests have passed.

As a result, test cases have been created for the specified Boa class, and the necessary Junit test cases have
been used to test all three methods.
