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


OutPuts =>

A.
![Screenshot (1566)](https://user-images.githubusercontent.com/46487696/114280146-9ce3bb00-9a55-11eb-8916-450de13d9344.png)

B.

![Screenshot (1567)](https://user-images.githubusercontent.com/46487696/114280149-9f461500-9a55-11eb-962d-92e07368e41a.png)

C.

![Screenshot (1568)](https://user-images.githubusercontent.com/46487696/114280151-9fdeab80-9a55-11eb-9106-f7bb1fa398f0.png)

D.

![Screenshot (1569)](https://user-images.githubusercontent.com/46487696/114280152-a0774200-9a55-11eb-9832-bc099789ca80.png)

E.

![Screenshot (1570)](https://user-images.githubusercontent.com/46487696/114280154-a2d99c00-9a55-11eb-84e5-c3af8f39a13c.png)

F.

![Screenshot (1571)](https://user-images.githubusercontent.com/46487696/114280155-a2d99c00-9a55-11eb-94ea-d4b64992e307.png)

G.

![Screenshot (1572)](https://user-images.githubusercontent.com/46487696/114280157-a3723280-9a55-11eb-9a8c-49ebb7e0e31e.png)
