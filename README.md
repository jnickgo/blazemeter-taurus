# BlazeMeter Taurus

Exploratory repo to showcase features of Taurus, an open source Automation-friendly framework for Continuous Testing

Why You Need Taurus for JMeter Scripts¶
JMeter is a very popular open source tool for testing your website or webapp. Although it’s quite powerful, it’s not very easy to use and its reporting abilities are very limited. Taurus is a free and open source framework for Continuous Testing which helps you by hiding the complexities of running performance tests. Think of it as an automation-friendly wrapper - it cloaks nicely around JMeter, neatly covering all of its complexities and imperfections.

When running JMeter through Taurus you can:

* Run an existing JMeter script
* Create a new JMeter script very easily using a YAML text file
* Automate your script with Jenkins
* Installation

## Getting Started
Browse through the presentation (Taurus.pptx) and the Taurus documentation.  Then install Taurus and write your first test, it's as easy as:

Create a file named simple-test.yaml, put the following in it.

```yaml
execution:
- concurrency: 100
  ramp-up: 1m
  hold-for: 5m
  scenario: quick-test

scenarios:
  quick-test:
    requests:
    - http://blazedemo.com
```

Open a terminal and run `bzt simple-test.yaml`


## Running Tests
Taurus (bzt) is a Command Line tool so tests will be invoked from the terminal.

### CLI Tool

`bzt <config file>`

#### Basic Example:

`bzt existing-jmeter.yaml`

#### loud exection with options override**
In this example we're using environment variables from our CI Platform, to override the cloud token for BlazeMeter.

`bzt cloud-scale.yaml -q -o modules.cloud.token=${BLAZE_PUBLIC_KEY}:${BLAZE_SECRET_KEY}`

## Helpful Links

### Combining Test 
* [Installing Taurus](https://gettaurus.org/install/Installation/)
* [Running JMeter and Selenium Scripts](https://gettaurus.org/kb/Scripting/)
* [Reporting results with Taurus](https://gettaurus.org/docs/Reporting/)
