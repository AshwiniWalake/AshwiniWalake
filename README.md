import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from webdriver_manager.chrome import ChromeDriverManager

driver = webdriver.Chrome(ChromeDriverManager().install())
driver.get("http://your-web-app-url.com")  # Replace with your web app URL

try:
    for i in range(50):
        # Replace with actual locators and actions for creating a record
        driver.find_element(By.ID, "add_button").click()
        driver.find_element(By.ID, "input_field").send_keys(f"Record {i+1}")
        driver.find_element(By.ID, "save_button").click()
        time.sleep(0.2)  # Adjust as needed

    # Trigger the submit CTA
    driver.find_element(By.ID, "submit_button").click()
finally:
    time.sleep(2)
    driver.quit()
