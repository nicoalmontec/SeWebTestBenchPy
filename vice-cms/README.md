# VICE CMS-Horoscopes 

qa-fe is our Front-End testing branch which houses our automated test cases. These tests are written in Python using Pytest. Tests are seperated out into `Vertical Specific` tests such as VICE, i-D, Noisey etc. 

Tests are housed here and then run using `Circle CI` see below for more information on components and getting setup to begin working on this branch. 

Our tests are designed to allow for inheritance because most pages share similar functionalities but differ in how they are laid out or by which components they contain.
All functions are contained in the `smoke_test_case` file which can be found in the `smoke` folder.

Supported Browsers: [Supported Browsers](https://vicedev.atlassian.net/wiki/spaces/QA/pages/190808184/Supported+Browsers)

| Browser | OS | Market Share % |
| ------------- |-------------| -----|
|Safari |OS-X| 15%|
|Safari |iOS| 17%|
|Stock |Android| 24%|
|Chrome |OS-X + Windows| 34%|


## Getting Started:

Begin by cloning the branch onto your machine. 

To run tests locally use: `pytest smoke/test_front_end.py -v -M n`

Defaults on tests are currently set to `VICE` as the default vertical and `EN_US` as default locale. 

Styling guide can be found here: [Pytest Styling](http://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html)


## Components:

**Pytest & Github:** 
The pytest framework makes it easy to write small tests, yet scales to support complex functional testing for applications and libraries. 

We used pytest to create encapsulated functionality test which we are using for smoke testing the site. 

All our tests are housed on Github in their respective QA branch. 
1. QA-FE: [QA-FE Github](https://github.com/VICEMedia/qa-fe)
2. QA-VV: [QA-VV Github](https://github.com/VICEMedia/qa-vv)


**CircleCI:** Allows users to create custom environments, apply workflows for control over your build pipeline, enjoy flexible resource allocation, and more.

**Circle CI Instance:** [Circle CI](https://69-127147638-gh.circle-artifacts.com/0/test-reports/staging-video/index.html#)

Circle CI provides a Plethora of information which we can be consumed by checking on the CircleCI instance or by using our integrated plugin **Allure**


**Browserstack**
Browserstack integration gives us the ability to run tests on a wide range of platforms and provides information. 


## How to add a test 

To add a test, create a new method in the `smoke_test_cases.py` and call this method in the specific `vertical` 


## Command Line Examples

python3 attack.py <vertical>  <platform>  <base_url>(optional)


**Locally:**
* pytest smoke/test_*.py -v -M n

**Mobile & Web**
* pytest smoke/test_*.py -v -B all

**Mobile**
* pytest smoke/test_*.py -v -B mobile

**Web**
* pytest smoke/test_*.py -v -B web

**Specific browsers**
* pytest smoke/test_*.py -v -B <specific platform-browser>

**Paramater Options**

Tests can be run on any number of platforms & verticals using the options in the table below.

`all`, `web` and `mobile` can be used as args to run the lists below. 

| Vertical Options | Platform Options - all |Platform Options - web | Platform Options mobile |
| ------------- |-------------|--|--
|VICE |OSX-Sierra-Chrome-65|OSX-Sierra-Chrome-65 | iPhone-6-Safari|
|i-D |Windows-8-Chrome-65|Windows-8-Chrome-65 | iPhone-7-Safari |
|Noisey |Windows-10-Chrome-65|Windows-10-Chrome-65 | iPad-Pro-Safari |
|Munchies |iPhone-6-Safari||Motorola-Moto-X-Chrome|
|Broadly |iPhone-7-Safari| |Google-Nexus-6-Chrome|
|FREE|iPad-Pro-Safari| | Google-Pixel-Chrome| 
|Garage|Motorola-Moto-X-Chrome| |Samsung-Galaxy-S8-Chrome|
|Amuse|Google-Nexus-6-Chrome|
|Tonic|Google-Pixel-Chrome|
|VICE IMPACT|Samsung-Galaxy-S8-Chrome|
|VICE Sports||


## Additional information

Skeleton Documents: [FE Skeleton Document](https://docs.google.com/document/d/1SpnPmQd42Umd0EbxF9IasrG18fZf4CcgX3yY2j-qO8g/edit#heading=h.vh51d6onhmju)

VICE QA Jira Instance: [Jira](https://viceqa.atlassian.net/secure/Dashboard.jspa)

