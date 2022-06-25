# seleniumTesting

package SeleniumTest;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.DataProvider;
import org.testng.annotations.Test;

public class SeleniumAssignment {

	@Test(dataProvider="TestCases")
	public void TestChrome(String uname, String password) throws InterruptedException {
		
		//to set the properties for the chrome browser
		System.setProperty("webdriver.chrome.driver", "/home/nishita/Downloads/chromedriver");
		WebDriver driver = new ChromeDriver();
		
		//to maximize the screen
		driver.manage().window().maximize();
		
		//to open the particular website
		driver.get("https://lasertruf.github.io/aoiskea/");
		
		//clear email field
		driver.findElement(By.id("mat-input-0")).clear();
		//enter username
		driver.findElement(By.id("mat-input-0")).sendKeys(uname);
		Thread.sleep(1000);
		
		//clear password field
		driver.findElement(By.id("mat-input-1")).clear();
		//enter password
		driver.findElement(By.id("mat-input-1")).sendKeys(password);
		Thread.sleep(1000);
		
		//to click on the drop-down option
		driver.findElement(By.xpath("/html/body/app-root/div[1]/mat-card/form/div[1]/mat-form-field/div")).click();
		//to select option from the drop-down
		driver.findElement(By.xpath("//mat-option[@id=\"mat-option-3\"]")).click();
		Thread.sleep(1000);
		
		//to click on the radio buttons
		driver.findElement(By.xpath("//mat-radio-button[@id=\"mat-radio-2\"]")).click();
		Thread.sleep(1000);
		
		//to click on the submit button
		driver.findElement(By.xpath("/html/body/app-root/div[1]/mat-card/form/button")).click();
		Thread.sleep(1000);
		driver.quit();
		
		
		//To check if the Email Id and Password fields are not empty 
		if(uname=="" && password == "") {
		        System.out.println("Email id and password is required");
		    }
		//to check username field
		else if (uname == "") {
			System.out.println("Username is required");
		}
		//to check the password field
		else if (password == "") {
			System.out.print("Password is required");
		}
		//to check password length 
		else if (password.length() < 8) {
			  System.out.println("Password should be atleat 8 Character long and your password length is " + password.length()+ " character" );
			} 
	
	}
	
	
	//to pass multiple parameters to a single test in a single execution
	@DataProvider(name = "TestCases")
	public Object[][] TestData() {
		Object[][] EnteredData = new Object[5][2];
		EnteredData[0][0] = "nishitakoshta10@gmail.com";
		EnteredData[0][1] = "123456789";
		EnteredData[1][0] = "nissssssssssssssssssssssssitakoshta10@gmail.com";
		EnteredData[1][1] = "12";
		EnteredData[2][0] = "";
		EnteredData[2][1] = "123456789";
		EnteredData[3][0] = "";
		EnteredData[3][1] = "";
		EnteredData[4][0] = "nishitakoshta10@gmail.com";
		EnteredData[4][1] = "";
		return EnteredData;

	}

}


https://user-images.githubusercontent.com/54737258/175767607-35d9a707-bd68-4b79-a74a-6cac4b6eb26b.mp4



