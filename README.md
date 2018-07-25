# JenkinsProjectStudy
StudyJenkins
java -version

package TestNGProject;

import org.testng.annotations.Test;
import org.testng.annotations.Test;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.util.List;

import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.remote.CapabilityType;
import org.openqa.selenium.remote.DesiredCapabilities;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.Test;

public class BanglaWebsiteSecond {
	
	@Test(priority=2)

	public  void BanglaForTesting() throws InterruptedException, IOException {
		
		
		        //Load Browser
		
				System.setProperty("webdriver.chrome.driver", "./drivers/chromedrivers.exe");
				
				WebDriver driver = new ChromeDriver();
				
				DesiredCapabilities cap=DesiredCapabilities.chrome();
				
		        cap.setCapability(CapabilityType.ACCEPT_SSL_CERTS, true); 
				
				driver.get("https://www.banglamatrimony.com");
				
				driver.manage().window().maximize();
				
				Thread.sleep(2000);
				     
				//To Load Excel
				
				File excel = new File("C://Excel to Read//BanglaDatas.xlsx");
				
				FileInputStream input = new FileInputStream(excel);		
						
				XSSFWorkbook workbook = new XSSFWorkbook(input);
				
				XSSFSheet sheet = workbook.getSheet("BanglaDatas");	
				
				//Profile Created By
				
				WebElement Profile = driver.findElement(By.id("profilecreatedbySelect"));
						
				Select ProfileDropDown = new Select(Profile);
						
				String ProfileData = sheet.getRow(5).getCell(1).getStringCellValue();
						
				ProfileDropDown.selectByVisibleText(ProfileData);
						
				System.out.println("Profile Created By:  " +ProfileData);
			
				//Name
				
				String Namedata = sheet.getRow(0).getCell(1).getStringCellValue();
				
				driver.findElement(By.id("name")).sendKeys(Namedata);
				
				System.out.println("Name:  "+Namedata);
				
				//Gender
				
				WebElement Gender = driver.findElement(By.id("genderselect"));
						
				Select GenderDropDown = new Select(Gender);
						
				String GenderData = sheet.getRow(6).getCell(1).getStringCellValue();
						
				GenderDropDown.selectByVisibleText(GenderData);
						
				System.out.println("Gender:  " +GenderData );
				
				//Date of Birth
				
				//Date
						
				WebElement Date = driver.findElement(By.id("dobDayselect"));
						
			    Select DateDropDown = new Select(Date);
						
				String DateData = sheet.getRow(7).getCell(1).getStringCellValue();
						
				DateDropDown.selectByVisibleText(DateData);
						
				System.out.println("Date:  " +DateData );
						
				//Month
						
				WebElement Month = driver.findElement(By.id("dobMonthselect"));
						
				Select MonthDropDown = new Select(Month);
						
				String MonthData = sheet.getRow(8).getCell(1).getStringCellValue();
						
				MonthDropDown.selectByVisibleText(MonthData);
						
				System.out.println("Month:  " +MonthData );
						
				//Year
						
				WebElement Year = driver.findElement(By.id("dobYearselect"));
						
				Select YearDropDown = new Select(Year);
						
				String YearData = sheet.getRow(9).getCell(1).getStringCellValue();
						
				YearDropDown.selectByVisibleText(YearData);
						
				System.out.println("Year:  " +YearData );
				
		        //Religion
				
		        WebElement Religion = driver.findElement(By.id("religionselect"));
				
				Select ReligionDropDown = new Select(Religion);
				
				String ReligionData = sheet.getRow(10).getCell(1).getStringCellValue();
				
				ReligionDropDown.selectByVisibleText(ReligionData);
				
				System.out.println("Religion:  " +ReligionData );
				
				Thread.sleep(3000);
				
		        /*//Caste
				
			    WebElement caste = driver.findElement(By.id("caste"));
						
				Select castedropdown = new Select(caste);
						
				String casteData = sheet.getRow(11).getCell(1).getStringCellValue();
						
				castedropdown.selectByVisibleText(casteData);
						
				System.out.println("Caste:  " +casteData );
				
				Thread.sleep(3000);*/
				
		        //MotherTongue
				
		        WebElement MotherTongue = driver.findElement(By.id("mothertongueselect"));
				
				Select MotherTongueDropDown = new Select(MotherTongue);
				
				String MotherTongueonData = sheet.getRow(12).getCell(1).getStringCellValue();
				
				MotherTongueDropDown.selectByVisibleText(MotherTongueonData);
				
				System.out.println("MotherTongue:  " +MotherTongueonData );
				
				//Email
				
				String EmailData = sheet.getRow(1).getCell(1).getStringCellValue();
				
				driver.findElement(By.id("inputEmail")).sendKeys(EmailData);
				
				System.out.println("Email Id:  " +EmailData);
				
		        //LivingIn
				
		        WebElement LivingIn = driver.findElement(By.id("countryselect"));
				
				Select LivingInDropDown = new Select(LivingIn);
				
				String LivingInData = sheet.getRow(13).getCell(1).getStringCellValue();
				
				LivingInDropDown.selectByVisibleText(LivingInData);
				
				System.out.println("LivingIn:  " +LivingInData );
				
				Thread.sleep(3000);
				
				//CountryCode
				
		        String CountryCodedata = sheet.getRow(2).getCell(1).getStringCellValue();
				
				driver.findElement(By.name("countryCode")).sendKeys(CountryCodedata);
				
				System.out.println("CountryCode:  "+CountryCodedata);
				
				//Mobile
				
				String Mobiledata = sheet.getRow(3).getCell(1).getStringCellValue();
				
				driver.findElement(By.name("mobile")).sendKeys(Mobiledata);
				
				System.out.println("Mobile:  "+Mobiledata);
				
				//Password
				
				String PasswordData = sheet.getRow(4).getCell(1).getStringCellValue();
				
				driver.findElement(By.id("pwd")).sendKeys(PasswordData);
				
				System.out.println("Password:  "+PasswordData);
				
				Thread.sleep(3000);
				
				//To Verify already selected country In
				
				//driver.findElement(By.xpath("//input[@diabled='']"));
				
				//clickRegister Free
				
				driver.findElement(By.xpath("//button[@class='btn btn-default']")).click();
				
				System.out.println();
				
				System.out.println("Page one Registered");
				
				System.out.println();
				
				Thread.sleep(2000);
				
				//Your Current Location
				
				//Residing State
				
				String ResidingState = sheet.getRow(14).getCell(1).getStringCellValue();
				
				driver.findElement(By.name("residingState")).sendKeys(ResidingState);
				
				System.out.println("ResidingState:  "  +ResidingState );
				
				//Residing City / District
				
		       String ResidingCity = sheet.getRow(15).getCell(1).getStringCellValue();
				
				driver.findElement(By.name("residingCity")).sendKeys(ResidingCity);
				
				System.out.println("ResidingState:  "  +ResidingCity );
				
				Thread.sleep(500);
				
				//CitizenShip
				
				WebElement Citizenship = driver.findElement(By.name("citizenship"));
				
				Select CitizenshipDropDown = new Select(Citizenship);
				
				String CitizenShipExcel  = sheet.getRow(29).getCell(1).getStringCellValue();
				
				CitizenshipDropDown.selectByVisibleText(CitizenShipExcel);
				
				System.out.println("Citizenship:  "+CitizenShipExcel);
				
				//Personal Details
				
				//Martial Status
				
				List<WebElement> MartialStatus = driver.findElements(By.xpath("//input[@type='radio' and @name='maritalStatus']"));
				
				for(WebElement Ele:MartialStatus) {
					
					String MartialStatusData = Ele.getAttribute("value");
					
					String MartialStatusData1 = sheet.getRow(16).getCell(1).getStringCellValue();
							
					if(MartialStatusData.equalsIgnoreCase(MartialStatusData1)) {
						
						Ele.click();
						
						System.out.println("Martial Status:  "+MartialStatusData1);
						
						break;
					}
				    }
				
//				//If Widow/Widower,Separated,Married,Divorced
//				
//				WebElement NoOfChildren = driver.findElement(By.name("noOfChildren"));
//				
//				Select childrenStatus = new Select(NoOfChildren);
//				
//				String SelectChildrens = sheet.getRow(29).getCell(1).getStringCellValue();
//				
//				childrenStatus.selectByVisibleText(SelectChildrens);
//				
//				//If Children were living with them?
//				
//				List<WebElement> LivingWith = driver.findElements(By.xpath("//input[@type='radio' and @name='childrenLivingWithMe']"));
//				
//				for(WebElement Elem : LivingWith) {
//					
//					String SelectLivingWith = Elem.getAttribute("value");
//					
//					String ChildrenLivivngStatus = sheet.getRow(30).getCell(1).getStringCellValue();
//					
//					//System.out.println("Children Living Status:  "  +SelectLivingWith);
//					
//					if(SelectLivingWith.equalsIgnoreCase(ChildrenLivivngStatus)) {
//						
//						Elem.click();
//						
//						System.out.println("Children Living Status:  "  +SelectLivingWith);
//						
//						break;
//					}
//					
//				}
				
		        //Height
				
				WebElement Height = driver.findElement(By.name("heightFeet"));
				
				Select HeightFeet = new Select(Height);
				
				String HeightFeetData = sheet.getRow(17).getCell(1).getStringCellValue();
				
				HeightFeet.selectByVisibleText(HeightFeetData);
				
				System.out.println("Height:  "+ HeightFeetData);
				
				//Physical Status		
				
		       List<WebElement> PhysicalStatus = driver.findElements(By.xpath("//input[@type='radio' and @name='physicalStatus']"));
				
				for(WebElement Element:PhysicalStatus) {
					
					String PhysicalStatusData = Element.getAttribute("value");
					
					String PhysicalStatusData1 = sheet.getRow(18).getCell(1).getStringCellValue();
					
					if(PhysicalStatusData.equalsIgnoreCase(PhysicalStatusData1)) {
						
						Element.click();
						
						System.out.println("Physical Status:  "+PhysicalStatusData);
						
						break;
			         }
		             }
				
				//Family Value
				
		        List<WebElement> FamilyValue = driver.findElements(By.xpath("//input[@type='radio' and @name='familyValue']"));
				
				for(WebElement Elements:FamilyValue) {
					
					String FamilyValueData = Elements.getAttribute("value");
					
					String FamilyValueData1 = sheet.getRow(19).getCell(1).getStringCellValue();
					
					if(FamilyValueData.equalsIgnoreCase(FamilyValueData1)) {
						
						Elements.click();
						
						System.out.println("Family Value:  "+FamilyValueData1);
						
						break;
			        }
					}
				
				//Family Type
				
				List<WebElement> FamilyType = driver.findElements(By.xpath("//input[@type='radio' and @name='familyType']"));
				
				for (WebElement FamilyEle : FamilyType) {
					
					String FamilyTypeElements = FamilyEle.getAttribute("value");
					
					String FamilyTypedata = sheet.getRow(20).getCell(1).getStringCellValue();
					
					if(FamilyTypeElements.equalsIgnoreCase(FamilyTypedata)) {
						
						FamilyEle.click();
						
						System.out.println("Family Type:  "+FamilyTypedata);
						
						break;
					}
				}
				
				//Family Status
				
				List<WebElement> FamilyStatus = driver.findElements(By.xpath("//input[@type ='radio' and @name='familyStatus']"));
				
				for(WebElement StatusEle :FamilyStatus ) {
					
					String FamilyStatusdata = StatusEle.getAttribute("value");
					
					String FamilyStatusdata1=sheet.getRow(21).getCell(1).getStringCellValue();
					
					if(FamilyStatusdata.equalsIgnoreCase(FamilyStatusdata1)) {
						
						StatusEle.click();
						
						System.out.println("Family Status:  "+FamilyStatusdata1);
						
					}
					}
				
				// for selecting ethinicity
				
				
				WebElement el4=driver.findElement(By.name("ethnicity"));
				
				Select s1=new Select(el4);
				
				s1.selectByVisibleText("Bengali");
				
				//Ethnicity
				
				//WebElement Ethnicity = driver.findElement(By.name("ethnicity"));
				
				//Select Ethnicityvalue = new Select(Ethnicity);
				
				//String EthnicityData = sheet.getRow(22).getCell(1).getStringCellValue();
				
				//System.out.println("Ethnicity:  "+EthnicityData);
				
				//Ethnicityvalue.selectByVisibleText(EthnicityData);
				
				//Thread.sleep(3000);
				
				//Professional Details
				
				//Education Level
				
		        WebElement EducationLevel = driver.findElement(By.name("educationCategory"));
				
				Select EducationLevelSelect = new Select(EducationLevel);
				
				String EducationLevelData = sheet.getRow(23).getCell(1).getStringCellValue();
				
				System.out.println("Education Level:  "+EducationLevelData);
				
				EducationLevelSelect.selectByVisibleText(EducationLevelData);
				
				
				//Field Of Education
		        
				WebElement FieldOfEducation = driver.findElement(By.name("fieldofeducation"));
				
				Select FieldOfEducationSelect = new Select(FieldOfEducation);
				
				String FieldOfEducationData = sheet.getRow(24).getCell(1).getStringCellValue();
				
				System.out.println("Field Of Education:  "+FieldOfEducationData);
				
				FieldOfEducationSelect.selectByVisibleText(FieldOfEducationData);
				
				//Employed In
				
		        List<WebElement> EmployedIn = driver.findElements(By.xpath("//input[@type ='radio' and @name='emp_in']"));
				
				for(WebElement EmployedInEle :EmployedIn ) {
					
					String EmployedIndata = EmployedInEle.getAttribute("value");
					
					String EmployedIndata1 = sheet.getRow(25).getCell(1).getStringCellValue();
					
					if(EmployedIndata.equalsIgnoreCase(EmployedIndata1)) {
						
						EmployedInEle.click();
						
						System.out.println("Employed In:  "+EmployedIndata1);
						
						break;
						
					}
					}
				
				  //Occupation Level
				
		        WebElement OccupationLevel = driver.findElement(By.name("occupation"));
				
				Select OccupationLevelSelect = new Select(OccupationLevel);
				
				String OccupationLevelData = sheet.getRow(26).getCell(1).getStringCellValue();
				
				System.out.println("Occupation Level:  "+OccupationLevelData);
				
				OccupationLevelSelect.selectByVisibleText(OccupationLevelData);
				
				//Annual Income
				
		        WebElement AnnualIncome = driver.findElement(By.name("annualIncomeCurrency"));
				
				Select AnnualIncomeSelect = new Select(AnnualIncome);
				
				String AnnualIncomeData = sheet.getRow(27).getCell(1).getStringCellValue();
				
				System.out.println("Annual Income:  "+AnnualIncomeData);
				
				AnnualIncomeSelect.selectByVisibleText(AnnualIncomeData);
				
				//per Year
				
				String AnnualIncomePerYear = sheet.getRow(28).getCell(1).getStringCellValue();
				
				WebElement PerYear = driver.findElement(By.name("incomeRangeBDT"));
				
				Select SelectPerYear = new Select(PerYear);
				
				SelectPerYear.selectByVisibleText(AnnualIncomePerYear); 
				
				System.out.println("Annual Income Per Year:  " +AnnualIncomePerYear );
				
				Thread.sleep(4000); 
				
				//To complete Registration
				
				//driver.findElement(By.xpath("//input[@class='submit']")).click();
				
				System.out.println("Registration Completed");
				
				
				
				
				}

			    }



