# Lab-8_202001063

Class:- 

```
package testcases;

public class Boa {
	
  private String name;
	private int length; // the length of the boa, in feet
	private String favoriteFood;
	public Boa (String name, int length, String favoriteFood){
		this.name = name;
		this.length = length;
		this.favoriteFood = favoriteFood;
	}
	// returns true if this boa constrictor is healthy
	public boolean isHealthy(){
		return this.favoriteFood.equals("granola bars");
	}
	// returns true if the length of this boa constrictor is
	// less than the given cage length
	
  public boolean fitsInCage(int cageLength){
		return this.length < cageLength;
	}
	
	public int lengthInInches() {
	    return this.length * 12;
	}
}
```

Testcases:-
```
package testcases;

import static org.junit.Assert.*;

import org.junit.After;
import org.junit.AfterClass;
import org.junit.Before;
import org.junit.BeforeClass;
import org.junit.Test;

public class BoaTest {

	private Boa jen;
	private Boa ken;

	@Before
	public void setUp() throws Exception {
		jen = new Boa("Jennifer", 2, "grapes");
		ken = new Boa ("Kenneth", 3, "granola bars");
	}

	@After
	public void tearDown() throws Exception {
	}

	@Test
	public void testIsHealthy1() {
		assertEquals("healthy diet",false,jen.isHealthy());
  }

	@Test
	public void testIsHealthy2() {
    assertEquals("Not a healthy diet",true,ken.isHealthy());
	}
  
	@Test
	public void testFitsInCage1() {
		assertEquals("Doesnt fit",false,jen.fitsInCage(1));
		assertEquals("Doesnt fit",false,jen.fitsInCage(2));
		assertEquals("fits",true,jen.fitsInCage(4));
	}

	@Test
	public void testFitsInCage2() {
		assertEquals(false,ken.fitsInCage(1));
		assertEquals(false,ken.fitsInCage(2));
		assertEquals(false,ken.fitsInCage(3));
		assertEquals(true,ken.fitsInCage(10));
	}
	

	@Test
	public void testLengthInInches() {
	    assertEquals(24, jen.lengthInInches());
	    assertEquals(36, ken.lengthInInches());
	}
}
```

Screen-Shots:-

![image](https://user-images.githubusercontent.com/84339207/233038783-b6bbc866-1b19-4cb5-a270-99ef66231654.png)
