## Script =>
```
package test_Auto_1;

import java.lang.reflect.Method;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
//import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.*;
import com.relevantcodes.extentreports.ExtentReports;
import com.relevantcodes.extentreports.ExtentTest;
import com.relevantcodes.extentreports.LogStatus;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import java.util.Set;

import java.util.ArrayList;


public class Myntra_Extent_Report {

	
	static ExtentReports report;
	static ExtentTest test;

	WebDriver driver;
	String baseurl="https://www.myntra.com/";
	String driverpath="C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Chrome_Driver_89\\chromedriver.exe";
    

	@BeforeClass
	public void initReport(){
		report = new ExtentReports("C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Report Results\\result.html");
	}
	
	
		@BeforeTest
		public void launchBrowser(){
			System.setProperty("webdriver.chrome.driver",driverpath);
			driver=new ChromeDriver();
			driver.get(baseurl);
			driver.manage().window().maximize();
			WebDriverWait wait=new WebDriverWait(driver,40);
		}
		
	
	@BeforeMethod
	public static void startReport(Method result){
		test = report.startTest("Extent Report - "+result.getName());
	}
	
	@AfterMethod
	public void endReport(){
		report.endTest(test);
		report.flush();
	}
	
	
	
	@Test(priority=0)
	public void clickSignin(){
		WebDriverWait wait=new WebDriverWait(driver,40);
		
		 wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[2]/div/div[1]/span[1]"))).click();     
	        //for click on profile logo
	        
	        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[2]/div/div[2]/div[2]/div[2]/div[1]/a"))).click();    
	        //for click on signup button
	        
		test.log(LogStatus.INFO, "Starting login");
		
		if(wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/div[2]/div[2]/div[1]/input")))!=null){
			test.log(LogStatus.PASS, "Email input box present");
		}
		else{
			test.log(LogStatus.FAIL, "Email input box absent");
		}
		
		test.log(LogStatus.WARNING, "Moving to next step");
		System.out.println("1");
	}
	
	@Test(priority=1)
	public void enterUsername(){
		WebDriverWait wait=new WebDriverWait(driver,40);

		
		wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/div[2]/div[2]/div[1]/input"))).sendKeys("8218672107");
		
		if(!wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/div[2]/div[2]/div[1]/input"))).getAttribute("value").equals("")){
			test.log(LogStatus.PASS, "Entered email successfully");
			wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/div[2]/div[2]/div[3]"))).click(); 
	        //for click on continue button
		}
		else{
			test.log(LogStatus.FAIL, "Couldn't enter email");
		}
		test.log(LogStatus.WARNING, "Moving to next step");
		
		System.out.println("2");
	}

	
	@Test(priority=2)
	public void enterPassword(){
		WebDriverWait wait=new WebDriverWait(driver,40);		 
		 wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div[3]/span"))).click();       
	        //for click on password button
		 wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/form/div/div[2]/input"))).sendKeys("Chitranshi@121");
	        // Password               

		
		if(!wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/form/div/div[2]/input"))).getAttribute("value").equals("")){
			test.log(LogStatus.PASS, "Entered password successfully");
			 wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/form/div/div[3]/button"))).click();       
		        //for click on continue button
		}
		else{
			test.log(LogStatus.FAIL, "Couldn't enter password");
		}
		test.log(LogStatus.WARNING, "Moving to next step");
		System.out.println("3");
	
	}
		
	@Test(priority=3)
	public void Searching() throws InterruptedException{
		WebDriverWait wait=new WebDriverWait(driver,40);

		wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[3]/input"))).click();
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[3]/input"))).sendKeys("mobile covers");
        // Product Searching		
		if(!wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[3]/input"))).getAttribute("value").equals("")){
			test.log(LogStatus.PASS, "Shoe Product Searching is done");
			wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[3]/a/span"))).click();
		}
		else{
			test.log(LogStatus.FAIL, "Wrong Product is Searched");
		}
		
		test.log(LogStatus.WARNING, "Product Searching is Done");
		Thread.sleep(100);
		System.out.print("4");
	}
		
	@Test(priority=4)
	public void Click_On_Product() throws InterruptedException{
		WebDriverWait wait=new WebDriverWait(driver,40);

		WebElement btn= wait.until(ExpectedConditions.elementToBeClickable(By.cssSelector("#desktopSearchResults > div.search-searchProductsContainer.row-base > section > ul > li:nth-child(1) > a > div.product-imageSliderContainer > div > div > div > picture > img")));
		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Product description is enabled and clickable");
			btn.click();		}
		else{
			test.log(LogStatus.FAIL, "product item is not clickable");
		}		
		Thread.sleep(100);
		System.out.print("5");
	}
	
	@Test(priority=5)
	public void Size_Selection() throws InterruptedException{
		WebDriverWait wait=new WebDriverWait(driver,40);

		WebElement btn= wait.until(ExpectedConditions.elementToBeClickable(By.cssSelector("#sizeButtonsContainer > div.size-buttons-size-buttons > div:nth-child(4) > div.size-buttons-buttonContainer > button > p")));
		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Specific Size has been selected ");
			btn.click();
		}
		else{
			test.log(LogStatus.FAIL, "Size button is not available");
		}		
		System.out.println("6\n");
	}
	
	@Test(priority=6)
	public void ADD_To_Bag() throws InterruptedException{
		
		System.out.println(driver.getCurrentUrl().toString());
		
		ArrayList<String> noOftabs = new 	ArrayList<String>(driver.getWindowHandles());
	      System.out.println("No of tbs" +  noOftabs);
		driver.switchTo().window(noOftabs.get(1));
		WebDriverWait wait=new WebDriverWait(driver,40);
		System.out.println(driver.getCurrentUrl().toString());

		WebElement btn= wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"mountRoot\"]/div/div/div/main/div[2]/div[2]/div[3]/div/div[1]")));
		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Product is added to the cart ");
//			wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\\\"mountRoot\\\"]/div/div/div/main/div[2]/div[2]/div[3]/div/div[1]"))).click();
//			btn = driver.findElement(By.xpath("//*[@id=\"mountRoot\"]/div/div/div/main/div[2]/div[2]/div[3]/div/div[1]"));
			btn.click();
		}
		else{
			test.log(LogStatus.FAIL, "Product is not available right now");
		}		
		
		Thread.sleep(100);
		System.out.println("7\n");

	}
	
	@Test(priority=7)
	public void Enter_To_Bag() throws InterruptedException{
		WebDriverWait wait= new WebDriverWait(driver,40);

		WebElement btn = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"mountRoot\"]/div/div/div/main/div[2]/div[2]/div[3]/div/a")));

		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "We are inside the Myntra's Bag");
//			wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"mountRoot\"]/div/div/div/main/div[2]/div[2]/div[3]/div/a"))).click();
//			btn = driver.findElement(By.xpath("//*[@id=\\\"mountRoot\\\"]/div/div/div/main/div[2]/div[2]/div[3]/div/a"));
			btn.click();
		}
		else{
			test.log(LogStatus.FAIL, "Myntra Bag is not accessible");
		}		
		Thread.sleep(100);
		System.out.println("8\n");

	}
	
	
	@Test(priority=8)
	public void Pincode_Verification() throws InterruptedException{
		WebDriverWait wait= new WebDriverWait(driver,40);
		WebElement btn = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div/div[1]/div[1]/div[2]")));

		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Pincode availability is here");
			btn.click();
		}
		else{
			test.log(LogStatus.FAIL, "Can't check product availability using pincode ");
		}		
		Thread.sleep(100);
		System.out.println("9\n");

	}
	@Test(priority=9)
	public void Enter_Pincode() throws InterruptedException{
		WebDriverWait wait = new WebDriverWait(driver,40);
		wait.until(ExpectedConditions.elementToBeClickable(By.id("pincode"))).click();
		wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div/div[1]/div[2]/div/div[2]/div[1]/input"))).sendKeys("245101");

		if(!wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div/div[1]/div[2]/div/div[2]/div[1]/input"))).getAttribute("value").equals("")){
			test.log(LogStatus.PASS, "Pincode insertion is successful");
		}
		else{
			test.log(LogStatus.FAIL, "Pincode doesn't valid");
		}	
		Thread.sleep(100);
		System.out.println("10\n");

		
	}	
	
	@Test(priority=10)
	public void Verify_Entered_Pincode() throws InterruptedException{
		WebDriverWait wait = new WebDriverWait(driver,40);
		WebElement btn = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div/div[1]/div[2]/div/div[2]/div[2]")));

		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Pincode Verification is completed");
			btn.click();			
		}
		else{
			test.log(LogStatus.FAIL, "Can not verify it recheck it");
		}	
		Thread.sleep(100);
		System.out.println("11\n");

		
	}
	
	@Test(priority=11)
	public void Place_Order() throws InterruptedException{
		WebDriverWait wait = new WebDriverWait(driver,40);
		WebElement btn = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"appContent\"]/div/div/div/div/div/div[2]/div[3]/a/div")));

		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Placed an order, ready for the further process");
			btn.click();			
		}
		else{
			test.log(LogStatus.FAIL, "Can't placed an order look again");
		}		
		Thread.sleep(100);
		System.out.println("12\n");
		
	}
	@Test(priority=12)
	public void Enter_name() throws InterruptedException{
		WebDriverWait wait = new WebDriverWait(driver,40);

		wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"name\"]"))).click();
		wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div[1]/div/div/div[1]/div[2]/div[1]/input"))).sendKeys("Kushagra Bansal");
		
		if(!wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div[1]/div/div/div[1]/div[2]/div[1]/input"))).getAttribute("value").equals("")){
			test.log(LogStatus.PASS, "Name is entered correcly");
		}
		else{
			test.log(LogStatus.FAIL, "Wrong name entered");
		}	
		Thread.sleep(100);
		System.out.println("13\n");
		
	}
	
	@Test(priority=13)
	public void Enter_Mobile_No() throws InterruptedException{
		
		WebDriverWait wait = new WebDriverWait(driver,40);
		wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div[1]/div/div/div[1]/div[2]/div[2]/input"))).click();
		wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div[1]/div/div/div[1]/div[2]/div[2]/input"))).sendKeys("8755210395");
		
		if(!wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div[1]/div/div/div[1]/div[2]/div[2]/input"))).getAttribute("value").equals("")){
			test.log(LogStatus.PASS, "Name is entered correcly");
		}
		else{
			test.log(LogStatus.FAIL, "Wrong name entered");
		}	
		Thread.sleep(100);
		System.out.println("14\n");
		
	}
	
	@Test(priority=14)
	public void Enter_Adrress() throws InterruptedException{
		
		WebDriverWait wait = new WebDriverWait(driver,40);
		wait.until(ExpectedConditions.elementToBeClickable(By.id("streetAddress"))).sendKeys("231, New Shivpuri, hapur");
		
		if(!wait.until(ExpectedConditions.elementToBeClickable(By.id("streetAddress"))).getAttribute("value").equals("")){
			test.log(LogStatus.PASS, "Name is entered correcly");
		}
		else{
			test.log(LogStatus.FAIL, "Wrong name entered");
		}	
		
		Thread.sleep(100);
		System.out.println("15\n");
	}
	
	@Test(priority=15)
	public void Enter_Hometown() throws InterruptedException{
		
		WebDriverWait wait = new WebDriverWait(driver,40);
		
		wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"locality\"]"))).click();
		wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"locality\"]"))).sendKeys("hapur");
		
		if(!wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"locality\"]"))).getAttribute("value").equals("")){
			test.log(LogStatus.PASS, "Name is entered correcly");
		}
		else{
			test.log(LogStatus.FAIL, "Wrong name entered");
		}	
		Thread.sleep(100);
		System.out.println("16\n");
		
	}
	
	@Test(priority=16)
	public void Default_Address() throws InterruptedException{
		
		WebDriverWait wait = new WebDriverWait(driver,40);
		WebElement btn = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"isDefault-icon\"]/svg")));
		
		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "selected as default address");
			btn.click();		}
		else{
			test.log(LogStatus.FAIL, "Not able to selected as default address");
		}	
		Thread.sleep(100);
		System.out.println("17\n");
		
	}
	
	@Test(priority=17)
	public void Add_Address() throws InterruptedException{
		
		WebDriverWait wait = new WebDriverWait(driver,40);
		WebElement btn = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div[1]/div/div/div[2]/div")));
		
		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Address is updates succesfully");
			btn.click();
			
		}
		else{
			test.log(LogStatus.FAIL, "NOT FOUND: Reconfirm the address might have some issues");
		}	
		Thread.sleep(100);
		System.out.println("18\n");

	}
	
	@Test(priority=18)
	public void Address_Continuation() throws InterruptedException{
		
		WebDriverWait wait = new WebDriverWait(driver,40);
		WebElement btn = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div[3]/div[5]/div")));
		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Shipping address has been selected");
			btn.click();
			
		}
		else{
			test.log(LogStatus.FAIL, "Shipping address not found");
		}
		Thread.sleep(100);
		System.out.println("19\n");

	}
	
	
	
}

```
