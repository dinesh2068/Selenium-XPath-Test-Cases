# SELENIUM XPATH – 20 TEST CASES

## Program

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import Select
import time


driver = webdriver.Chrome()

# TC01 - Open student registration page get()
driver.get("https://www.selenium.dev/selenium/web/web-form.html")
time.sleep(3)

# TC02 - Locate username Attribute XPath
username = driver.find_element(By.XPATH,"//input[@name='my-text']").send_keys("DK")
time.sleep(2)

# TC03 - Enter password Attribute XPath
password = driver.find_element(By.XPATH,"//input[@name='my-password']").send_keys("pass1234")
time.sleep(2)

# TC04 - Locate Submit text()
submit_button = driver.find_element(By.XPATH,"//button[text()='Submit']")
time.sleep(2)

# TC05 - Locate textbox dynamically contains()
textarea = driver.find_element(By.XPATH,"//textarea[contains(@name,'textarea')]").send_keys("This is Selenium XPath testing")
time.sleep(2)

# TC06 - Locate element with prefix starts-with()
datalist = driver.find_element(By.XPATH,"//input[starts-with(@name,'my-data')]").send_keys("One")
time.sleep(2)

# TC07 - Find input using two attributes and
password = driver.find_element(By.XPATH,"//input[@name='my-password' and @type='password']")
time.sleep(2)

# TC08 - Find input using alternatives or
text_or_password = driver.find_element(By.XPATH,"//input[@name='my-text' or @name='my-password']")
time.sleep(2)

# TC09 - Find parent form parent
parent = driver.find_element(By.XPATH,"//input[@name='my-text']/parent::*")
time.sleep(2)

# TC10 - Find form from input ancestor
form = driver.find_element(By.XPATH,"//input[@name='my-text']/ancestor::form")
time.sleep(2)

# TC11 - Find child inputs child
child_inputs = driver.find_elements(By.XPATH,"//form/descendant::input")
time.sleep(2)

# TC12 - Find next element following
following_element = driver.find_element(By.XPATH,"//input[@name='my-text']/following::input[1]")
time.sleep(2)

# TC13 - Find checkbox Attribute + XPath
checkbox = driver.find_element(By.XPATH,"//input[@name='my-check']")

if not checkbox.is_selected():
    checkbox.click()

time.sleep(2)

# TC14 - Find radio button Attribute + XPath
radio = driver.find_element(By.XPATH,"//input[@name='my-radio']")

if not radio.is_selected():
    radio.click()

print("Radio button selected")

time.sleep(2)


# TC15 - Select dropdown XPath + Select
dropdown = Select(driver.find_element(By.XPATH,"//select[@name='my-select']"))
dropdown.select_by_visible_text("Two")
time.sleep(2)

# TC16 - Find second textbox XPath index
second_textbox = driver.find_element(By.XPATH,"(//input)[2]")
time.sleep(2)

# TC17 - Verify submitted message text()
submit_button = WebDriverWait(driver, 10).until(EC.element_to_be_clickable((By.XPATH, "//button[text()='Submit']")))
submit_button.click()

time.sleep(3)

success_message = WebDriverWait(driver, 10).until(EC.visibility_of_element_located((By.XPATH, "//*[contains(text(),'Received')]")))

time.sleep(2)

# TC18 - Find all input fields find_elements()
driver.back()
time.sleep(2)
all_inputs = driver.find_elements(By.XPATH,"//input")
time.sleep(2)

# TC19 - Find dynamic element contains()

dynamic_element = driver.find_element(By.XPATH,"//input[contains(@name,'my-')]")

time.sleep(2)

# TC20 - Complete registration automation Multiple XPath concepts

username = driver.find_element(By.XPATH,"//input[@name='my-text']")
username.clear()
username.send_keys("DK")
time.sleep(1)


password = driver.find_element(By.XPATH,"//input[@name='my-password']")
password.clear()
password.send_keys("pass1234")
time.sleep(1)

textarea = driver.find_element(By.XPATH,"//textarea[contains(@name,'textarea')]")
textarea.clear()
textarea.send_keys("Complete XPath Automation Test")
time.sleep(1)


dropdown = Select(driver.find_element(By.XPATH,"//select[@name='my-select']"))
dropdown.select_by_visible_text("Three")
time.sleep(1)

checkbox = driver.find_element(By.XPATH,"//input[@name='my-check']")

if not checkbox.is_selected():
    checkbox.click()

time.sleep(1)


radio = driver.find_element(By.XPATH,"//input[@name='my-radio']")

if not radio.is_selected():
    radio.click()

time.sleep(2)


submit_button = WebDriverWait(driver, 10).until(EC.element_to_be_clickable((By.XPATH, "//button[text()='Submit']")))

submit_button.click()

time.sleep(3)
driver.quit()
```

## Output Images

<img width="1842" height="332" alt="image" src="https://github.com/user-attachments/assets/6723d2f5-babf-46e0-86a3-9e5fa6816e1d" />


<img width="1858" height="982" alt="image" src="https://github.com/user-attachments/assets/82812810-3b8d-4cae-89ed-a40ecec9bf5e" />
