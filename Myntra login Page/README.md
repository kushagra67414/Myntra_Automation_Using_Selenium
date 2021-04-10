## Script =>

```
package test_Auto_1;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import java.sql.Driver;
import java.util.*;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.By.ByXPath;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebElement;
import com.aventstack.extentreports.utils.DateUtil;


public class Myntra_2 {
	
	
	public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver","C:\\\\Users\\\\Dell\\\\Desktop\\\\New\\\\Semester-6\\\\Test Automation\\\\Chrome_Driver_89\\\\chromedriver.exe");
        WebDriver driver= new ChromeDriver();
   

        driver.manage().window().maximize();
        driver.get("https://www.myntra.com/login/password");

        WebElement Number = driver.findElement(By.id("mobileNumberPass"));
        Number.sendKeys("8755210395");
        System.out.println("1");
        
        WebElement password = driver.findElement(By.cssSelector("#reactPageContent > div > div > form > div > div:nth-child(2) > input"));  
        password.sendKeys("Aaaaaaaa@121");
//        password.submit();
        System.out.println("2");
        
//        WebElement clickable = driver.findElement(By.className("btn primary  lg block submitButton"));
        WebElement clickable = driver.findElement(By.cssSelector("#reactPageContent > div > div > form > div > div:nth-child(3) > button"));
        clickable.click();
        System.out.println("3");
        
        ArrayList<String> tabs = new ArrayList<String>(driver.getWindowHandles());
        System.out.println("No. of tabs: " + tabs.size());
        System.out.println("4");

    
        
	}

}

```
