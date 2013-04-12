Selendroid
==========

[![Build Status](https://api.travis-ci.org/DominikDary/selendroid.png)](https://travis-ci.org/DominikDary/selendroid)


Selendroid is an attempt to implement the Selenium JSON Wire Protocol for Android native and hybrid apps.

Latest News:
------------

* Selendroid Version 0.3 is released [List of Features](https://github.com/DominikDary/selendroid/blob/master/changelog.md))

Getting started
---------------

Selendroid is based on the Android instrumentation framework, so therefor only testing one specific app is supported.
Selendroid-server in combination with the application under test (aut) must be installed on the device in order to be able to run automated end-to-end tests.

To write and run tests with selendroid, first a customized selendroid-server for your aut must be created. To simplify this process I have created a Ruby gem:

		sudo gem install selendroid
		selendroid build-and-start pathToYour.apk
		
Run your tests
--------------

A sample test looks like:

```java
		driver = new AndroidDriver(new URL("http://localhost:8080/wd/hub"), getDefaultCapabilities());
		driver.findElement(By.id("startUserRegistration")).click();
		
		WebDriverWait wait = new WebDriverWait(driver, 5);
		WebElement inputUsername =
         	wait.until(ExpectedConditions.presenceOfElementLocated(By.id("inputUsername")));
		inputUsername.sendKeys(user.getUsername());
		Assert.assertEquals(nameInput.getText(), "Mr. Burns");
		nameInput.clear();
		nameInput.sendKeys(user.getName());
		takeScreenShot("User data entered.");
		driver.findElement(By.id("btnRegisterUser")).click();
```

You want more details?
----------------------

Check out our [wiki](https://github.com/DominikDary/selendroid/wiki/).

