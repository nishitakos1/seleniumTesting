# seleniumTesting

package SeleniumTest;


import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class SeleniumAssignment {

	public static void main(String[] args) throws InterruptedException {

		System.setProperty("webdriver.chrome.driver", "/home/nishita/Downloads/chromedriver");//to set the properties for the chrome browser 
		WebDriver driver = new ChromeDriver();

		driver.manage().window().maximize();//to maximaize the screen

		
		driver.get("https://lasertruf.github.io/aoiskea/");//it is used for opening the website

		
		driver.findElement(By.xpath("//*[@id=\"mat-input-0\"]")).sendKeys("nishitakoshta10@gmail.com");//it is used for providing email id to the input field 


		driver.findElement(By.xpath("//*[@id=\"mat-input-1\"]")).sendKeys("123456789");//it is used for providing password  to the input field 

		driver.findElement(By.xpath("/html/body/app-root/div[1]/mat-card/form/button")).click();//it is used for clicking the submit button

		Thread.sleep(5000);//it is used to stop the execution of the script for the 5sec 
		driver.quit();//it is used for closing the execution window
		System.out.println("Done");

	}

}

https://user-images.githubusercontent.com/54737258/175028993-7149eb16-ba93-4c88-95f3-da473aea2037.mp4


