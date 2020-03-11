# CI-CD_Implemetation
This repo discusses CI/CD implementation details that includes automation test framework
# Integrating test automation framework into CI/CD environment

In order for the UI automation and API automation framework to be part of Continuous Integration environment, 
a CI/CD pipeline can be constructed using following components.

1. Source Code Repository (Git)
2. CI Tool (Jenkins)
3. Test Automation Framework based on project management tool such as Maven

In Jenkins, we can configure to run automated tests using 'mvn test' directive which executes TestNG suites.
We can configure mutiple profiles in pom.xml based on the test cases we want to run after certain type of build.
For example, sanity tests can be run every day and other types of tests are triggered when source code changes are
submitted to source control.

The choice of Jenkins is largely due to the fact that it is an open source tool with active community support as well as 
availability of plugins required to integrate different workflows. However, in an enterprise setup, level of customer support 
provided by CI tool vendor influences the choice of software more.

## Integration with cloud based services

To run UI automation tests, there are three options.

1. Local resources - including on-prem devices and virtual machine instances

    We can use devices owned locally and available for testing to implement Selenium hub/node framework and 
   run tests in parallel with different device/OS/browser configurations such as PC/Window10/Edge browser or 
   Mac/OS X/Chrome etc. The drawback with this approach is it requires that these devices and environments 
   are maintained and there's an upfront cost to it.
   
2. Cloud based VM/Containers - using AWS/Azure/GCP

    Another approach is to instead of owning the devices locally, we can run automated tests on cloud based
    instances. This saves cost to a degree but stil requires to setup and maintain configurations. You can 
    launch instances with images which needs to be updated with security vulnerability and OS upgrades etc.
    So there is some overhead that still remains.
    
3. Managed on-demand test environments such as SauceLab

    With on-demand solutions such as SauceLab, you can request desired test environment with many different 
    configurations and that does not require any maintenance of the OS or hardware. It makes testing process 
    agile and test resources readily available. Depending on the cost model of the vendor, this might be the 
    best approach among the three outlined here.
