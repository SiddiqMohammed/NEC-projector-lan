# NEC projector control

The NEC projector has a web remote that can be used to control the projector. The issue is I still have to go to the browser and click on the buttons. So I have automated the process using selenium.

The code was written such that I could press a button placed on the couch and the projector would mute/unmute the display, and the button was connected to an Arduino which sends signals to my main PC running the code. 

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install Selenium.

```bash
pip install selenium
```
You also need to get the webdriver depending on which browser you want to use. I used firefox so I had to get the geckodriver and paste it in my root.



On the projector:

1. Make sure that you have DHCP turned off. 

2. Check the IP and note it down. 

3. Remove security password.



On the PC:

1. Set the IP to any of your choices but make sure it has the same subnet masking as the projector
## Usage
```python
driver.get("http://192.168.0.103/index.html")
```
This is the default IP of the NEC projector. Set it to whatever your NEC is set to that you found in step 2 above.

```python
driver.switch_to.frame(driver.find_element_by_name("consoleN"))
accordion = driver.find_element_by_name('mute_pic')
```
Change the element from 'mute pic' to any other element of your choosing. You can do an inspect element of the page to get the name of the button that you want to press.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
