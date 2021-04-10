## Script =>

```
package test_Auto_1;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.By;
import java.util.List;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

//import com.aventstack.extentreports.utils.DateUtil;
//import java.util.concurrent.TimeUnit;



public class UnloadingProducts	 {
	
	
	public static void main(String[] args) throws InterruptedException {
        System.setProperty("webdriver.chrome.driver","C:\\\\\\\\Users\\\\\\\\Dell\\\\\\\\Desktop\\\\\\\\New\\\\\\\\Semester-6\\\\\\\\Test Automation\\\\\\\\Chrome_Driver_89\\\\\\\\chromedriver.exe");
        WebDriver driver= new ChromeDriver();
        
        WebDriverWait wait=new WebDriverWait(driver,40);

        driver.manage().window().maximize();
        driver.get("https://www.myntra.com/");

 
        
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[2]/div/div[1]/span[1]"))).click();     
        //for click on profile logo
        
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[2]/div/div[2]/div[2]/div[2]/div[1]/a"))).click();    
        //for click on signup button
        
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/div[2]/div[2]/div[1]/input"))).sendKeys("8766226307");
        System.out.println("1");
        
        
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/div[2]/div[2]/div[3]"))).click(); 
        //for click on continue button
        
        
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div[3]/span"))).click();       
        //for click on password button
       
        
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/form/div/div[2]/input"))).sendKeys("Shivani16#");
        // Password
        System.out.println("2");
        
        
                
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/form/div/div[3]/button"))).click();       
        //for click on continue button
        System.out.println("3");
      
      
      
       wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//*[@id=\"desktop-header-cnt\"]/div[2]/div[2]/a[2]/span[1]"))).click();       
       System.out.println("4");
// Go to BAG
       
//       wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div/div[1]/div[6]/div[1]/div/div/div/div[3]/div[1]/button"))).click(); 
//       System.out.println("5");
       
       List <WebElement> listofItems = driver.findElements(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div/div[1]/div[6]/div/div/div/div/div[3]/div[1]/button"));
       
       for(int i =0 ; i< listofItems.size();i++) {
    	   System.out.println(i);
         wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div/div[1]/div[6]/div[1]/div/div/div/div[3]/div[1]/button"))).click(); 
         wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div/div[1]/div[6]/div[1]/div/div/div/div[4]/div/div/div[2]/div[2]/button"))).click();
         
         driver.navigate().refresh();
       }
       
       System.out.println("5");
//       wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div[2]/div/div/div/div/div/div/div[1]/div[6]/div[1]/div/div/div/div[4]/div/div/div[2]/div[2]/button"))).click();
//       System.out.println("6");
	
	}

}

```
