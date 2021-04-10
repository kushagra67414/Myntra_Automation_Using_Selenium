## Script =>

```
package test_Auto_1;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
//import java.sql.Driver;
//import java.util.*;
//import java.util.concurrent.TimeUnit;
//import org.openqa.selenium.Alert;
import org.openqa.selenium.By;

import java.util.ArrayList;
//import org.openqa.selenium.By.ByXPath;
//import org.openqa.selenium.JavascriptExecutor;
//import org.openqa.selenium.Keys;	
//import org.openqa.selenium.WebElement;
import java.util.Set;
import static org.testng.Assert.*;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

//import com.aventstack.extentreports.utils.DateUtil;
//import java.util.concurrent.TimeUnit;
public class Myntra_3 {
	public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver","C:\\\\\\\\Users\\\\\\\\Dell\\\\\\\\Desktop\\\\\\\\New\\\\\\\\Semester-6\\\\\\\\Test Automation\\\\\\\\Chrome_Driver_89\\\\\\\\chromedriver.exe");
        WebDriver driver= new ChromeDriver();
        WebDriverWait wait=new WebDriverWait(driver,40);
        driver.manage().window().maximize();
        driver.get("https://www.myntra.com/");
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[2]/div/div[1]/span[1]"))).click();     
        //for click on profile logo
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[1]/div/div/header/div[2]/div[2]/div/div[2]/div[2]/div[2]/div[1]/a"))).click();    
        //for click on signup button
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/div[2]/div[2]/div[1]/input"))).sendKeys("8218672107");
        System.out.println("1");
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/div[2]/div[2]/div[3]"))).click(); 
        //for click on continue button
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div[3]/span"))).click();       
        //for click on password button
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/form/div/div[2]/input"))).sendKeys("Chitranshi@121");
        // Password
        System.out.println("2");
        wait.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div[2]/div[3]/div[2]/div/div/div[1]/div/div/form/div/div[3]/button"))).click();       
        //for click on continue button
        System.out.println("3");
            	
	}

}
```
