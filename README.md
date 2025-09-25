from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

# Twoje dane logowania
email = "twoj_email@example.com"
password = "twoje_haslo"

# Uruchom przeglądarkę (wymaga zainstalowanego ChromeDriver)
driver = webdriver.Chrome()

# Wejdź na stronę logowania GitHub
driver.get("https://github.com/login")

# Wypełnij login
username_field = driver.find_element(By.ID, "login_field")
username_field.send_keys(email)

# Wypełnij hasło
password_field = driver.find_element(By.ID, "password")
password_field.send_keys(password)

# Zatwierdź formularz
password_field.send_keys(Keys.RETURN)

# Poczekaj chwilę
time.sleep(5)

# Sprawdź, czy się udało
if "GitHub" in driver.title:
    print("Prawdopodobnie zalogowano.")
else:
    print("Coś poszło nie tak.")

# Zatrzymaj przeglądarkę
# driver.quit()
