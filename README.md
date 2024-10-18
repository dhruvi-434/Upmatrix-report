# Upmatrix-report
Performed testing on Upmatrix website and created automated tests:

Package multimodules;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;
public class ContactModule {
	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		
		// Initialize ChromeDriver
		WebDriver driver = new ChromeDriver();
		driver.get("https://dev.upmatrix.in/login");
		Thread.sleep(3000);
		// Create object of the Actions class
		Actions actions = new Actions(driver);
		// Maximize window
		driver.manage().window().maximize();
		Thread.sleep(1000);
		String title = driver.getTitle();
		Thread.sleep(1000);
		System.out.println("The title of login page is: " + title);
		Thread.sleep(1000);
		
		//Login page
				WebElement element = driver.findElement(By.name("email"));
				Thread.sleep(1000);
				// Enter Email
				element.sendKeys("kajal.karia@matrixhive.com");
				Thread.sleep(1000);
				// Enter password
				driver.findElement(By.name("password")).sendKeys("Kajal@123");
				Thread.sleep(1000);
				// Select checkbox remember me
				driver.findElement(By.id("remember_token")).click();
				Thread.sleep(1000);
				// Click on sign in button
				driver.findElement(By.xpath("/html/body/div/div[2]/div[1]/div/div[2]/button")).click();
				Thread.sleep(2000);
		//Contact Module
		
		  driver.findElement(By.xpath("/html/body/div/div/div/aside/div/div/div/ul/li[3]/div/a")).click();
		  Thread.sleep(3000);
		
		
		  //click on add contact button
		  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/div[1]/div/div/div[2]/button[1]")).click();
		  Thread.sleep(3000);
		 
		  //Enter text in Name field
		  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div[1]/input")).sendKeys("Automation 1");
		  Thread.sleep(3000);
		 
		  //Enter Email in Email field
		  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div[3]/input")).sendKeys("automation@test.com");
		  Thread.sleep(3000);
		 
		  //select ISD code
		  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div[5]/div/div[2]")).click(); actions.sendKeys(Keys.ENTER).build().perform();
		  Thread.sleep(3000);
		 
		  //enter phone number
		  driver.findElement(By.name("phone_no")).sendKeys("946382364");
		  Thread.sleep(3000);
		 
		 
		 
		  //Select from Org drop down
		  WebElement orgdropdown =
		  driver.findElement(By.xpath("//*[@id=\"slot_content\"]/div/span/div[1]/div[1]/div[7]/select")); orgdropdown.click();
		  Select dropdown1 = new Select(orgdropdown);
		  dropdown1.selectByValue("2");
		  Thread.sleep(3000);
		 
		  //click on Add address button //Scroll down till element found
		  JavascriptExecutor js = (JavascriptExecutor) driver; WebElement AddAddress =driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div[9]/p/button"));
		  js.executeScript("arguments[0].scrollIntoView();", AddAddress);
		  AddAddress.click();
		  Thread.sleep(3000);
		 
		  //Select address type
		  WebElement selectAddress = driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div/div[1]/select"));
		  selectAddress.click();
		  Select address = new Select(selectAddress);
		  address.selectByValue("Billing");
		  Thread.sleep(3000);
		 
		  //add street
		  driver.findElement(By.name("street")).sendKeys("Automation street");
		  Thread.sleep(3000);
		 
		  //Select country option1
		 
		  driver.findElement(By.xpath(
		  "/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div/div[3]/div/div[2]"
		  )).click(); WebElement menuoption = driver.findElement(By.xpath(
		  "/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div/div[3]/div/div[3]/ul/li[3]/span/span"
		  )); menuoption.click(); Thread.sleep(3000);
		 
		  //select Country Option 2 (need to work on this)
		 
		  WebElement country = driver.findElement(By.xpath(
		  "/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div/div[3]/div/div[2]"
		  )); country.click(); Thread.sleep(2000); country.sendKeys("India");
		  actions.sendKeys(Keys.ENTER).build().perform(); Thread.sleep(3000);
		 
		 
		 
		  //Select State
		  driver.findElement(By.xpath(
		  "/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div/div[4]/div/div[2]"
		  )).click(); WebElement selectState = driver.findElement(By.xpath(
		  "/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div/div[4]/div/div[3]/ul/li[1]/span/span"
		  )); selectState.click(); Thread.sleep(3000);
		 
		  //Add city name
		  driver.findElement(By.name("city_name")).sendKeys("Ahmedabad");
		  Thread.sleep(3000);
		 
		  //Add ZIP code driver.findElement(By.name("zip_code")).sendKeys("35272");
		  Thread.sleep(3000);
		 
		  //Save Address driver.findElement(By.id("action_slot")).click();
		  System.out.println("Address saved successfully"); Thread.sleep(5000);
		 
		 
		 
		  //Click on Save contact
		  driver.findElement(By.id("action_slot")).click();
		  System.out.println("Contact Added Successfully"); Thread.sleep(5000);
		 
		  //Edit contact
		  driver.findElement(By.xpath(
		  "/html/body/div/div/div/div/main/div[3]/div/div[2]/div[1]/div/div/div/table/tbody/tr[1]/td[6]/button[1]"
		  )).click(); Thread.sleep(3000);
		 
		  //Update contact driver.findElement(By.id("action_slot")).click();
		  System.out.println("Contact updated Successfully"); Thread.sleep(5000);
		 
		  // Delete contact
		  driver.findElement(By.xpath(
		  "/html/body/div/div/div/div/main/div[3]/div/div[2]/div[1]/div/div/div/table/tbody/tr[1]/td[6]/button[2]"
		  )).click(); Thread.sleep(5000);
		 
		  driver.findElement(By.xpath(
		  "//*[@id=\"slot_content\"]/div/span/div[1]/div[3]/button[1]")).click();
		  System.out.println("Contact deleted successfully"); Thread.sleep(5000);
		 
		 
		 
		/*
		 * // Search by contact
		 * driver.findElement(By.id("contacts-search")).sendKeys("Hiedi");
		 * actions.sendKeys(Keys.ENTER).build().perform();
		 * System.out.println("Search by contact done"); Thread.sleep(5000);
		 *
		 * driver.findElement(By.id("contacts-search")).clear();
		 */
		
		/*
		 * driver.findElement(By.id("contacts-search"));
		 * actions.sendKeys(Keys.ENTER).build().perform(); Thread.sleep(3000);
		 */
		
		/*
		 * driver.findElement(By.id("contacts-search")).clear(); Thread.sleep(2000);
		 *
		 * driver.findElement(By.id("contacts-search")).click();
		 * actions.sendKeys(Keys.ENTER).build().perform(); Thread.sleep(2000);
		 */
		 
		 
		 
		 
		  // Search by tag
			
			  driver.findElement( By.xpath(
			  "/html/body/div/div/div/div/main/div[3]/div/div[1]/div/div/div[1]/div/div/div[1]/input"
			  )).sendKeys("virgo"); Thread.sleep(2000); driver.findElement( By.xpath(
			  "/html/body/div/div/div/div/main/div[3]/div/div[1]/div/div/div[1]/div/div/div[2]/ul/li"
			  )).click(); Thread.sleep(2000);
			 
			  driver.findElement(By.xpath(
			  "/html/body/div/div/div/div/main/div[3]/div/div[1]/div/div/div[1]/div/div/div[1]/span/button"
			  )).click(); Thread.sleep(3000);
			 
			  driver.findElement( By.xpath(
			  "/html/body/div/div/div/div/main/div[3]/div/div[1]/div/div/div[1]/div/div/div[1]/input"
			  )).clear(); Thread.sleep(3000);
			
	}
}
2:20
Contact
2:20
package multimodules;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
//import org.openqa.selenium.interactions.Actions;
public class LoginPage {
	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		
		// Initialize ChromeDriver
				WebDriver driver = new ChromeDriver();
				driver.get("https://dev.upmatrix.in/login");
				Thread.sleep(3000);
				// Create object of the Actions class
				//Actions actions = new Actions(driver);
				// Maximize window
				driver.manage().window().maximize();
				Thread.sleep(1000);
				String title = driver.getTitle();
				Thread.sleep(1000);
				System.out.println("The title of login page is: " + title);
				Thread.sleep(1000);
		//Login page
				WebElement element = driver.findElement(By.name("email"));
				Thread.sleep(1000);
				// Enter Email
				element.sendKeys("kajal.karia@matrixhive.com");
				Thread.sleep(1000);
				// Enter password
				driver.findElement(By.name("password")).sendKeys("Kajal@123");
				Thread.sleep(1000);
				// Select checkbox remember me
				driver.findElement(By.id("remember_token")).click();
				Thread.sleep(1000);
				// Click on sign in button
				driver.findElement(By.xpath("/html/body/div/div[2]/div[1]/div/div[2]/button")).click();
				Thread.sleep(2000);
	}
}
2:20
Login
2:21
package multimodules;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
//import org.openqa.selenium.interactions.Actions;
public class OrganizationModule {
	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		
		// Initialize ChromeDriver
				WebDriver driver = new ChromeDriver();
				driver.get("https://dev.upmatrix.in/login");
				Thread.sleep(3000);
				// Create object of the Actions class
				//Actions actions = new Actions(driver);
				// Maximize window
				driver.manage().window().maximize();
				Thread.sleep(1000);
				String title = driver.getTitle();
				Thread.sleep(1000);
				System.out.println("The title of login page is: " + title);
				Thread.sleep(1000);
				
				//Login page
				WebElement element = driver.findElement(By.name("email"));
				Thread.sleep(1000);
				// Enter Email
				element.sendKeys("kajal.karia@matrixhive.com");
				Thread.sleep(1000);
				// Enter password
				driver.findElement(By.name("password")).sendKeys("Kajal@123");
				Thread.sleep(1000);
				// Select checkbox remember me
				driver.findElement(By.id("remember_token")).click();
				Thread.sleep(1000);
				// Click on sign in button
				driver.findElement(By.xpath("/html/body/div/div[2]/div[1]/div/div[2]/button")).click();
				Thread.sleep(2000);
				//Organization Module
				  driver.findElement(By.xpath("/html/body/div/div/div/aside/div/div/div/ul/li[4]/div/a")).click();
				  Thread.sleep(3000);
				 
				
				  ///Add Organization
				  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/div[1]/div/div/button")).click();
				  Thread.sleep(3000);
				 
				  //Organization name
				  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div[1]/input")).sendKeys("Automation Organization");
				  Thread.sleep(3000);
				 
				  //Org Email
				  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div[2]/input")).sendKeys("automation3@email.com");
				  Thread.sleep(3000);
				 
				  //Select ISD code
				  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div[3]/div/div[2]")).click();
				  Thread.sleep(3000);
				  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div[3]/div/div[3]/ul/li[97]/span")).click();
				  Thread.sleep(5000);
				 
				  //Enter Phone number
				  driver.findElement(By.name("phone_no")).sendKeys("5462819263");
				  Thread.sleep(5000);
				 
				  //Save Organization
				  driver.findElement(By.id("action_slot")).click();
				  Thread.sleep(5000);
				 
				 
				  //Edit Organization
				 
				//Click on Edit button
				  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/div[2]/div[1]/div/div/div/table/tbody/tr[1]/td[5]/button[1]")).click();
				  Thread.sleep(5000);
				 
				  //Update Org name field
				  WebElement Orgname = driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[1]/div[2]/input"));
				  Orgname.clear();
				  Thread.sleep(3000);
				  Orgname.sendKeys("Automation Organization Update");
				  Thread.sleep(5000);
				 
				  //Click on Save button
				  driver.findElement(By.id("action_slot")).click();
				  System.out.println("Organization Updated Successfully");
				  Thread.sleep(5000);
				 
				  //Click on Delete button
				  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/div[2]/div[1]/div/div/div/table/tbody/tr[1]/td[5]/button[2]")).click();
				  Thread.sleep(5000);
				 
				  //Click on Confirmation button "Yes"
				  driver.findElement(By.xpath("/html/body/div/div/div/div/main/div[3]/div/span/div[1]/div[3]/button[1]")).click();
				  Thread.sleep(5000);
				  System.out.println("Organization Deleted Successfully");
				 
	}
}
Organization
