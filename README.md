# How to upload file on [LambdaTest](https://www.lambdatest.com/?utm_source=github&utm_medium=repo&utm_campaign=Pytest-upload-file) for automation test in Pytest 

If you want to upload a file to the LambdaTest and use it in your Pytest automation test, you can follow the below steps. You can refer to sample test repo [here](https://github.com/LambdaTest/pytest-selenium-sample).

# Steps:

### Step 1: Upload the file to LamdbaTest using API

Use the LambdaTest file upload API to upload the file to the backend -https://api.lambdatest.com/automation/api/v1/user-files


### Step 2: Pass file in capabilities

In the `conftest.py` file, you need to update the test capabilities and add the filename for the `lambda:userFiles` capability. For example, if two files with filenames `photo1.png` and `photo2.png`, it has to be passed like so in the capability:

```
capabilities = {
        "build": "Sample PY Build",
        "platformName": "Windows 11",
        "browserName": "Chrome",
        "browserVersion": "latest",
		"lambda:userFiles": ["photo1.png","photo2.png"]
}
```

### Step 3: Use the file in your test

The files can be used in your test like so:

* For Windows:
```python
elm = driver.find_element_by_xpath("//input[@type='file']")
elm.send_keys("C:\\Users\\ltuser\\Downloads\\photo1.png")
```
* For MacOS:
```python
elm = driver.find_element_by_xpath("//input[@type='file']")
elm.send_keys("/Users/ltuser/Downloads/photo1.png")
```
### Step 4: Run your test

```bash
cd tests //navigate to tests directory
python sample_todo.py
```

# Links:

[LambdaTest Community](http://community.lambdatest.com/)

