package AscendTekPractise;

import Utilities.UtilityFiles;
import com.aventstack.extentreports.ExtentReports;
import com.aventstack.extentreports.reporter.ExtentSparkReporter;
import org.openqa.selenium.WebDriver;
import org.testng.Assert;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.DataProvider;
import org.testng.annotations.Test;
import AscendTekWebElements.ContactUsPage;

public class ContactUs_TestNg_dataProvider extends UtilityFiles {

    public WebDriver driver=UtilityFiles.browserLaunch("chrome");
    public ExtentReports extent;
    public ExtentSparkReporter spark;
    ContactUsPage cs =new ContactUsPage(driver);

    @BeforeClass
    void setUp(){
        getUrl("https://www.ascendtek.com/");
//        driver.findElement(By.xpath("//*[@id=\"et-boc\"]/div/div[1]/span/a")).click();

    }

    @Test(dataProvider = "TestDatas")
  public void contactUs(String firstname, String lastname, String email, String phonenumber, String Message) throws InterruptedException {
        clickBtn(cs.getMainMenuContactUs());
        sendKeysElement(cs.getFirstName(),firstname);
       sendKeysElement(cs.getLastName(),lastname);
       Thread.sleep(2000);
       sendKeysElement(cs.getEmail(),email);
       sendKeysElement(cs.getPhoneNumber(),phonenumber);
       sendKeysElement(cs.getMessage(),Message);
       clickBtn(cs.getSendMessageBtn());
       String expected="Contact Us - AscendTek";
       String actual = driver.getTitle();
       Assert.assertEquals(actual,expected);
    }
@DataProvider(name="TestDatas")
    public String[] [] datas(){

       String testDatas [] [] ={
               {"Vijay","M","vijay@gmail.com","9943924671","Hi Team,Im username, Im running a clothing firm, to sell my products i need static website from your organization.please let me know when we can work together."},
               {"Vicky","","vicky@gmail.com","8838138967","Hi Team,Im username, Im running a clothing firm, to sell my products i need static website from your organization.please let me know when we can work together."},
       };
       return testDatas;
}

}
