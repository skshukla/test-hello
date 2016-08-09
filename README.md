import org.junit.After;
import org.junit.AfterClass;
import org.junit.Before;
import org.junit.BeforeClass;
import org.junit.Ignore;
import org.junit.Test;


public class BasicAnnotationTest {

		
	@BeforeClass
	public static void runOnceBeforeClass()
	{
		System.out.println("@BeforeClass "+"runOnceBeforeClass()");
		
	}
	
	@AfterClass
	public static void runOnceAfterClass()
	{
		
		System.out.println("@AfterClass "+"runOnceAfterClass()");
	}
	@Before
	public  void runBeforeTestMethod()
	{
		
		System.out.println("@Before "+"runBeforeTestMethod()");
		
	}
	
	@After
	public void runAfterTestMethod()
	{
		System.out.println("@After"+"runAfterTestMethod()");
		
	}
	 //test case
	   @Test
	   public void test() {
	      System.out.println("in test");
	   }
		
	   //test case ignore and will not execute
	   @Ignore
	   public void ignoreTest() {
	      System.out.println("in ignore test");
	   }
	
	
}


import org.junit.runner.JUnitCore;
import org.junit.runner.Result;
import org.junit.runner.notification.Failure;


public class TestRunner {

	/**
	 * @param args
	 */
	public static void main(String[] args) {
		
		Result result =JUnitCore.runClasses(BasicAnnotationTest.class);
		for (Failure failure:result.getFailures())
		{
			System.out.println(failure.toString());
		}
		System.out.println(result.wasSuccessful());
}
}

