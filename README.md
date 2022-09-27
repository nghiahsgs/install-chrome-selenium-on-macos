# install-chrome-selenium-on-macos
install chrome selenium on macos

## Step1: Install chrome
Like windows, you can use mac to download and install chrome in normal way


## Step2: Download suitable chromedriver for mac (fit for current version of chrome)
```
https://chromedriver.chromium.org/downloads
```

choose mac intel or mac m1, download and extract file

## Step3: Install chromeselenium
```
pip install chromeselenium
```
## Step4: run code here
```
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
CHROMEDRIVER_PATH = '/usr/local/bin/chromedriver'
WINDOW_SIZE = "1920,1080"
chrome_options = Options()
chrome_options.add_argument("--headless")
chrome_options.add_argument("--window-size=%s" % WINDOW_SIZE)
chrome_options.add_argument('--no-sandbox')
driver = webdriver.Chrome(executable_path=CHROMEDRIVER_PATH,
                          chrome_options=chrome_options
                         )
driver.get("https://www.google.com")
print(driver.title)
driver.close()
```

## Step 5: fix error
```
“chromedriver” cannot be opened because the developer cannot be verified.
```

```
cd usr/local/Caskroom/chromedriver 
xattr -d com.apple.quarantine chromedriver 
```

```
spctl --add --label 'Approved' chromedriver
```
