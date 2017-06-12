# farmlogics
It is a product of iwad
Admin Code


package pack1;



import java.awt.AWTException;
import java.awt.Robot;
import java.awt.event.KeyEvent;
import java.util.List;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeSuite;
import org.testng.annotations.AfterSuite;
import org.testng.asserts.SoftAssert;

import com.relevantcodes.extentreports.ExtentReports;
import com.relevantcodes.extentreports.ExtentTest;

import org.testng.annotations.AfterClass;
import org.testng.annotations.Test;



































import java.io.File;
import java.io.IOException;












import junit.framework.Assert;


//import java.util.concurrent.TimeUnit;
import org.apache.commons.io.FileUtils;
import org.apache.commons.lang3.RandomStringUtils;
//import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebElement;
//import org.openqa.selenium.WebDriver;
//import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
//import org.testng.annotations.BeforeMethod;
//import org.testng.annotations.Test;
//import org.testng.annotations.BeforeTest;
import org.testng.annotations.AfterTest;

import com.relevantcodes.extentreports.LogStatus;
import com.relevantcodes.extentreports.model.ITest;
public class Admin_test{
	
	WebDriver driver;
	String s,k,f;
	String s1;
	String p,p1;
	public ExtentReports reports;
	 public ExtentTest test;
	  public SoftAssert softAssert;
	 
	  @Test(priority=0)
	  public void login() throws InterruptedException
	  {
		 
		  
		  test = reports.startTest("Login FarmLogics");

			
		  test.log(LogStatus.INFO, "FarmLogics Test Started");
		  test.log(LogStatus.PASS,"Application URL was opened.");

		  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/div/div/div/div/form/div/div[1]/input")).sendKeys("ritesh");
		  driver.findElement(By.name("password")).sendKeys("123456");
		 
		  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/div/div/div/div/form/div/div[3]/button")).click();	
	 Thread.sleep(2000);
	 driver.findElement(By.xpath("html/body")).click();
	 test.log(LogStatus.PASS,"Login  successful.");
	 
	 Thread.sleep(3000);
	 
	  }
	  
	  //admin-->user management-->user control-->screenshot
	  
	  @Test(priority=1)
	  public void Admin() throws InterruptedException, IOException
	  
	  {
		  test = reports.startTest("Administrator");
		 
		  Thread.sleep(2000);
		
		driver.findElement(By.linkText("Administrator")).click();
		  Thread.sleep(2000); 
		//  test.log(LogStatus.PASS,"Administrator was opened");
		  test.log(LogStatus.PASS,"Admin menu contains....");
		  for(int i=1;i<=4;i++)
			{
			  
String kk=driver.findElement(By.xpath(".//*[@id='sidebar-wrapper']/div[2]/uib-accordion/div/div[1]/div[2]/div/uib-accordion/div/div["+i+"]/div[1]/h4/a/span/span")).getText();
test.log(LogStatus.INFO,"..."+kk);

			}
		  reports.endTest(test);
		  test = reports.startTest("Setup");
			 //setup click
			  driver.findElement(By.xpath(".//*[@id='sidebar-wrapper']/div[2]/uib-accordion/div/div[1]/div[2]/div/uib-accordion/div/div[4]/div[1]/h4/a/span/span")).click();
			  Thread.sleep(3000);
			  test.log(LogStatus.PASS,"Setup: ");
			  test.log(LogStatus.PASS,"Set up is opened");
				test.log(LogStatus.INFO,"-----------");
			 // reports.endTest(test);
			  //location
			//  test = reports.startTest("Location");
	  }
			  @Test(priority=2)
			  public void location() throws InterruptedException
			  {
			  driver.findElement(By.xpath("/html/body/div/div/ng-include/div/div[2]/uib-accordion/div/div[1]/div[2]/div/uib-accordion/div/div[4]/div[2]/div/ul[1]/li[1]/a/span")).click();
			  test.log(LogStatus.PASS,"Location");
			
			  Thread.sleep(2000);
				 driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-header/div/div/div/button[2]")).click();
			 
				 Thread.sleep(3000);
				// s=RandomStringUtils.randomAlphabetic(4);
			 driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/input")).sendKeys("India");
			  Thread.sleep(2000);
			  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[2]/div/button[2]")).click();
			 // test.log(LogStatus.PASS,"New Location saved successfully");
			  Thread.sleep(3000);
		
				
			  try
				 {
				 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
				  
					  test.log(LogStatus.INFO," Location India is existing"); 
					  driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).click();
					  Thread.sleep(2000);
						 driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/input")).clear();

					 
				 }
				 catch(Exception e)
				 {
					  test.log(LogStatus.PASS,"Location India added");
					
				  }

				driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/input")).sendKeys("Kerala");
				  Thread.sleep(2000);
				  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[2]/div/button[3]")).click();
				 // test.log(LogStatus.PASS,"New Location saved successfully");
				  Thread.sleep(3000);
			
					
				  try
					 {
					 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
					  
						  test.log(LogStatus.INFO," Location KERALA is existing"); 
						  driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).click();
						  Thread.sleep(2000);
							// driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/input")).clear();
						  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[2]/div/button[4]")).click();

						 
					 }
					 catch(Exception e)
					 {
						  test.log(LogStatus.PASS,"Location KERALA added");
						
					  }
					test.log(LogStatus.INFO,"-----------");
				  }
				 
			  
			 

			  
			  
			  
			  
			  
			 // s=RandomStringUtils.randomAlphabetic(1);
			
			//  test = reports.startTest("Division");
			  @Test(priority=3)
			  public void division() throws InterruptedException
			  {
			  Thread.sleep(3000);
			  //click division
			  driver.findElement(By.xpath("html/body/div[1]/div/ng-include/div/div[2]/uib-accordion/div/div[1]/div[2]/div/uib-accordion/div/div[4]/div[2]/div/ul[1]/li[2]/a/span")).click();
			  Thread.sleep(2000);
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-header/div/div/div/button[2]")).click();
			  test.log(LogStatus.PASS,"Division");
		
			  
			 // reports.endTest(test);
			//  test.log(LogStatus.PASS,"division is clicked");
			 // test = reports.startTest("Division.Addnew");
				 // test = reports.startTest("Division.Addnew");
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/input")).sendKeys("1");
			
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[2]/div/input")).sendKeys("Kerala");
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[3]/div/div/div/div[1]")).click();
driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[3]/div/div/div/div[1]/input")).sendKeys("India");
Thread.sleep(2000);
driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[3]/div/div/div/div[1]/input")).sendKeys(Keys.TAB);


			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[5]/div/button[2]")).sendKeys(Keys.TAB);

			  
			  Thread.sleep(3000);
			  //save and close
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[5]/div/button[3]")).click();
			  //driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[5]/div/button[3]")).sendKeys(Keys.ENTER);
			  Thread.sleep(3000);
				
			  try
				 {
				 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
				  
					  test.log(LogStatus.INFO," Division KERALA is Existing"); 
					  driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).click();
					  Thread.sleep(2000);
					  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[5]/div/button[4]")).click();
				 }
				 catch(Exception e)
				 {
					  test.log(LogStatus.PASS,"Divison KERALA is added");
					
				  }
				test.log(LogStatus.INFO,"-----------");
		
			  }
			  @Test(priority=4)
			  public void crop1() throws InterruptedException
			  {
			  //crop
			  Thread.sleep(3000);
			  driver.findElement(By.xpath("/html/body/div/div/ng-include/div/div[2]/uib-accordion/div/div[1]/div[2]/div/uib-accordion/div/div[4]/div[2]/div/ul[1]/li[3]/a")).click();
				
			  test.log(LogStatus.PASS,"Crop ");
			 
		
			  //Addnew
			  Thread.sleep(3000);
	 driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-header/div/div/div/button[2]")).click();
				 
				 
				 Thread.sleep(3000);
			 // s=RandomStringUtils.randomAlphabetic(5);
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/input")).sendKeys("Rice");
			  Thread.sleep(3000);
			 
			  //save and close
			  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[3]/div/button[3]")).click();
				 Thread.sleep(3000);
			  try
				 {
				 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
				  
					  test.log(LogStatus.INFO,"RICE is Existing"); 
					  driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).click();
					  Thread.sleep(2000);
					  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[3]/div/button[4]")).click();
				 }
				 catch(Exception e)
				 {
					  test.log(LogStatus.PASS," Crop RICE is added");
					
				  }
			  }
			  
			  @Test(priority=5)
			  public void crop2() throws InterruptedException
			  {
	
			  
				  Thread.sleep(3000);
					 driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-header/div/div/div/button[2]")).click();
								 
					 
								 Thread.sleep(3000);
							 // s=RandomStringUtils.randomAlphabetic(5);
							  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/input")).sendKeys("Cocoa");
							  Thread.sleep(3000);
							 
							  //save and close
							  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[3]/div/button[3]")).click();
								 Thread.sleep(3000);
							  try
								 {
								 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
								  
									  test.log(LogStatus.INFO,"COCOA is Existing"); 
									  driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).click();
									  Thread.sleep(2000);
									  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[3]/div/button[4]")).click();
								 }
								 catch(Exception e)
								 {
									  test.log(LogStatus.PASS," Crop COCOA is added");
									
								  }
								test.log(LogStatus.INFO,"-----------");
							  }


@Test(priority=6)
public void exchangerate() throws InterruptedException, IOException
{
			 //Exchange rate
	Thread.sleep(3000); 		
				driver.findElement(By.xpath("/html/body/div/div/ng-include/div/div[2]/uib-accordion/div/div[1]/div[2]/div/uib-accordion/div/div[4]/div[2]/div/ul[1]/li[6]/a/span")).click();
				
			  test.log(LogStatus.PASS,"Exchange Rate  ");
			  Thread.sleep(2000);
			  
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-header/div/div/div/button[2]")).click();
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[1]/div/div[1]/div/div/input")).sendKeys("01.01.2016");
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[1]/div/div[2]/div/div/input")).sendKeys("31.12.2016");
			  Thread.sleep(3000);
			  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]")).click();
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div/div[1]/input")).sendKeys("USD");
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div/div[1]/input")).sendKeys(Keys.TAB);

			//  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]")).sendKeys(Keys.TAB);
			 // driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]/input")).sendKeys(Keys.TAB);

			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[2]/div/div/input")).sendKeys("3.5");
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[3]/div/div/input")).sendKeys("3.5");
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[2]/button[1]")).click();
			  Thread.sleep(2000);
			//  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div[1]/div/div/div[1]/input")).click();
			  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]")).click();
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div/div[1]/input")).sendKeys("GHC");
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div/div[1]/input")).sendKeys(Keys.TAB);

			//  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]")).sendKeys(Keys.TAB);
			 // driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]/input")).sendKeys(Keys.TAB);

			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[2]/div/div/input")).sendKeys("1");
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[3]/div/div/input")).sendKeys("1");
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[2]/button[1]")).click();
			  Thread.sleep(5000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/div/button[3]")).click();
			 // driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/div/button[3]")).sendKeys(Keys.ENTER);
			  Thread.sleep(3000);
	
			 // driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/div/button[3]")).click();

			  Thread.sleep(4000);
			 // test.log(LogStatus.PASS,"Exchange rate of 2016 is Added");
			
			  try
				 {
				 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
				  
					  test.log(LogStatus.INFO,"Closing date 31.12.2016 already existing"); 
					  driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).click();
					  Thread.sleep(2000);
					  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/div/button[4]")).click();
				 }
				 catch(Exception e)
				 {
					  test.log(LogStatus.PASS,"Exchange rate  of  2016 is added");
					
				  }
				 
			 

			  
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-header/div/div/div/button[2]")).click();
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[1]/div/div[1]/div/div/input")).sendKeys("01.01.2017");
			  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[1]/div/div[2]/div/div/input")).sendKeys("31.12.2017");
			  Thread.sleep(3000);
			  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]")).click();
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div/div[1]/input")).sendKeys("USD");
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div/div[1]/input")).sendKeys(Keys.TAB);

			//  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]")).sendKeys(Keys.TAB);
			 // driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]/input")).sendKeys(Keys.TAB);

			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[2]/div/div/input")).sendKeys("1");
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[3]/div/div/input")).sendKeys("1");
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[2]/button[1]")).click();
			  Thread.sleep(2000);
			//  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div[1]/div/div/div[1]/input")).click();
			  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]")).click();
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div/div[1]/input")).sendKeys("GHC");
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div/div[1]/input")).sendKeys(Keys.TAB);

			//  driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]")).sendKeys(Keys.TAB);
			 // driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[1]/div/div/div[1]/input")).sendKeys(Keys.TAB);

			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[2]/div/div/input")).sendKeys("4");
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[3]/div/div/input")).sendKeys("4");
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[2]/button[1]")).click();
			  Thread.sleep(5000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/div/button[3]")).click();
			 // driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/div/button[3]")).sendKeys(Keys.ENTER);
			  Thread.sleep(3000);
	
			 // driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/div/button[3]")).click();

			  Thread.sleep(4000);
			
			  try
				 {
				 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
				  
					  test.log(LogStatus.INFO,"Closing date 31.12.2017 already existing"); 
					  driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).click();
					  Thread.sleep(2000);
					  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/div/button[4]")).click();
				 }
				 catch(Exception e)
				 {
					  test.log(LogStatus.PASS,"Exchange rate  of 2017 is added");
					
				  }
				
				test.log(LogStatus.INFO,"-----------");
			
				
		
			
		
			 // driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[3]/div/button[3]")).sendKeys(Keys.ENTER);
			 //Edit Exchange rate 
		/*	 Thread.sleep(3000);
			 driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/farm-overview-grid/div[1]/div/div/div[3]/div/div[2]/div/div[2]/div/div/div/div[2]")).click();

		// driver.findElement(By.xpath(".//*[@id='1495170181167-1-uiGrid-00MW-cell']/div/div[2]")).click();
			 Thread.sleep(2000);
			 driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[2]/div/div[1]/div/div[2]/div/div[2]/div/div[1]/div/div/div")).click();
			 Thread.sleep(3000);
			 driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[3]/div/input")).click();

			 driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[3]/div/input")).clear();

			 driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[1]/div[3]/div/input")).sendKeys("4");
			 Thread.sleep(2000);
			 driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[1]/div/div[2]/button[1]")).click();
			 Thread.sleep(4000);
			 driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/div/button[3]")).click();
			 Thread.sleep(4000);
		//driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[2]/div/div[1]/div/div[1]/div[2]/div/div[1]/div/div[3]/input")).click();
			 driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/div/farm-overview-grid/div[1]/div/div/div[3]/div/div[2]/div/div[2]/div/div/div/div[2]")).click();
	
			 Thread.sleep(4000);
			 String sr=driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[2]/div/div[1]/div/div[1]/div[2]/div/div[1]/div/div[3]/input")).getText();
	System.out.println("val"+sr);
			String sr2=driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form[2]/div[2]/div/div[1]/div/div[1]/div[2]/div/div[1]/div/div[2]/input")).getText();
			  System.out.println("val sr1"+sr);
			  System.out.println(sr2);
			 if(sr.equals(sr2))
			 {
				 test.log(LogStatus.WARNING,"Exchange rate is not editable");
				 File scrFile = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
			
			 
			      FileUtils.copyFile(scrFile,new File("screenshot12.png"));
			      FileUtils.copyFile(scrFile,new File("src/screenshot12.png"));
				   
			      Thread.sleep(20000);  
			      test.log(LogStatus.WARNING,"Exchange rate"+test.addScreenCapture("screenshot12.png"));
			 }*/
			 
			
			  
}


	 

@Test(priority=7)
public void unit() throws InterruptedException
{
	driver.findElement(By.xpath("/html/body/div/div/ng-include/div/div[2]/uib-accordion/div/div[1]/div[2]/div/uib-accordion/div/div[4]/div[2]/div/ul[1]/li[7]/a/span")).click();

	  test.log(LogStatus.PASS,"Unit  ");

	  
	  //Add new
	  Thread.sleep(2000);
	  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-header/div/div/div/button[2]")).click();
	  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/input")).sendKeys("cm");
	  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[2]/div/input")).sendKeys("Centimeter");
	  
	  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[4]/div/button[3]")).click();
	  driver.findElement(By.xpath("/html/body/div/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[4]/div/button[3]")).sendKeys(Keys.ENTER);
	  Thread.sleep(2000);
	  try
		 {
		 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
		  
			  test.log(LogStatus.INFO," Unit CENTIMETER is existing"); 
			  driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).click();
			  Thread.sleep(2000);
			  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[4]/div/button[4]")).click();
		 }
		 catch(Exception e)
		 {
			  test.log(LogStatus.PASS," Unit CENTIMETER is  added");
			
		  }
		 
		test.log(LogStatus.INFO,"-----------");
}
@Test(priority=8)
public void cfset() throws InterruptedException
{
	driver.findElement(By.xpath("html/body/div[1]/div/ng-include/div/div[2]/uib-accordion/div/div[1]/div[2]/div/uib-accordion/div/div[4]/div[2]/div/ul[1]/li[9]/a")).click();
	
	test.log(LogStatus.PASS,"CF Settings");

	driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/div/input")).click();
	driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/div/input")).clear();
	Thread.sleep(2000);

	driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/div/input")).sendKeys("31.12.2015");
	Thread.sleep(2000);
	driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[4]/div/button[1]")).click();
	Thread.sleep(5000);
	  try
		 {
		 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
		  test.log(LogStatus.INFO,"Entered closed date 31.12.2015 is existing");
		  		
			  driver.findElement(By.xpath("html/body/div[3]/div/div/div[3]/button[2]")).click();
			  Thread.sleep(2000);
			//  driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[4]/div/button[2]")).click();
		 }
		 catch(Exception e)
		 {
			  test.log(LogStatus.PASS,"Closed date  31.12.2015 is  added");
			
		  }
		test.log(LogStatus.INFO,"-----------");
	  }
@Test(priority=9)

public void whset() throws InterruptedException
{
	Thread.sleep(3000);
	driver.findElement(By.xpath("html/body/div[1]/div/ng-include/div/div[2]/uib-accordion/div/div[1]/div[2]/div/uib-accordion/div/div[4]/div[2]/div/ul[1]/li[11]/a")).click();
Thread.sleep(2000);
test.log(LogStatus.PASS,"WH Settings ");

driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/div/input")).click();
driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/div/input")).clear();


driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[1]/div/div/input")).sendKeys("31.01.2016");

Thread.sleep(2000);
driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[2]/div/div/input")).click();
driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[2]/div/div/input")).clear();

driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[2]/div/div/input")).sendKeys("31.12.2015");

driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[2]/div/div/input")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("html/body/div[1]/div/div/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[7]/div/button[1]")).click();

Thread.sleep(3000);
try
	 {
	 driver.findElement(By.xpath("html/body/div[3]/div/div/div/button")).isDisplayed();
	  test.log(LogStatus.INFO,"Last Store  closed date 31.01.2016 is existing"); 
	  test.log(LogStatus.INFO,"Last Voucher  date 31.12.2015 is existing"); 
		
		
		  driver.findElement(By.xpath("html/body/div[3]/div/div/div[3]/button[2]")).click();
		  Thread.sleep(2000);
		 // driver.findElement(By.xpath(".//*[@id='content-wrapper']/div/div/div/rd-widget/div/rd-widget-body/div/div/div/form/div[7]/div/button[2]")).click();
	 }
	 catch(Exception e)
	 {
		 test.log(LogStatus.PASS,"Last Store  closed date 31.01.2016 is added"); 
		  test.log(LogStatus.PASS,"Last Voucher  date 31.12.2015 iis added"); 
	  }
test.log(LogStatus.INFO,"-----------");
}

  @BeforeMethod
  public void beforeMethod() throws AWTException {
	  Robot robot = new Robot();
		robot.keyPress(KeyEvent.VK_ESCAPE);
		robot.keyRelease(KeyEvent.VK_ESCAPE);

  }

  @AfterMethod
  public void afterMethod() {
  }

  @BeforeClass
  public void beforeClass() {
  }

  @AfterClass
  public void afterClass() {
  }

  @BeforeTest
  public void beforeTest() {
	  System.setProperty("webdriver.chrome.driver", "src/chromedriver.exe");
		driver=new ChromeDriver();
		
		driver.manage().timeouts().implicitlyWait(5000, TimeUnit.MILLISECONDS);
		driver.get("http://52.31.238.31/farmlogics/#/login");
		 reports = new ExtentReports("src/TestResults2.html", true);
  }

  
  
  @AfterTest
  public void afterTest() {
	 // driver.quit();
		reports.endTest(test);
		  reports.flush();
  }

  @BeforeSuite
  public void beforeSuite() {
  }

  @AfterSuite
  public void afterSuite() {
  }

}

