# Perfomance Testing
<img width="1000" alt="image" src="https://user-images.githubusercontent.com/70295997/212999590-58796168-0ae9-4222-9560-29cc411adcd0.png">

## Smoke testing

A smoke test is a test configured for minimal load.

Each time you write a new test script, it's a good idea to run a smoke to test first, which helps you:
- Verify that your test script doesn't have errors.
- Verify that your system doesn't throw any errors when under minimal load.

The VU chart of a smoke test should look similar to this. You want to use only 1 or 2 VUs.

![image](https://user-images.githubusercontent.com/70295997/213001364-54174382-52e6-4f6f-a7d9-a1b8f70aa384.png)

If your smoke test produces any errors, you should either correct the script or fix your environment before you continue.

The test output should look similar to this:
<img width="1330" alt="Screenshot 2023-01-17 at 12 10 50 PM" src="https://user-images.githubusercontent.com/70295997/213001588-7a9a8fb6-e390-4450-872b-9cde96077758.png">

Once your smoke test shows zero errors, you can go to the next step and execute a __load__ test to assess the performance of your system.

## Load testing

Load Testing is primarily concerned with assessing the current performance of your system in terms of concurrent users or requests per second.

When you want to understand if your system is meeting the performance goals, this is the type of test you'll run.
<img width="918" alt="Screenshot 2023-01-17 at 12 14 18 PM" src="https://user-images.githubusercontent.com/70295997/213002223-6b982cab-b35e-4a3c-a62b-15d3627fbbd3.png">

You probably have some understanding about the amount of traffic your system is seeing on average and during peak hours. This information will be useful when deciding what your performance goals should be, in other words, how to configure the performance thresholds. Thresholds are a way of ensuring that your system is meeting the performance goals you set for it.

Let's say you're seeing around 60 concurrent users on average and 100 users during the peak hours of operation.

It's probably important to you to meet the performance goals both during normal hours and peak hours, therefore it's recommended to configure the load test with the high load in mind - 100 users in this case.

The VU chart of a typical load test looks similar to this:
![image](https://user-images.githubusercontent.com/70295997/213002518-52a66366-9de7-4b4c-868e-3005a18863ef.png)

Note that the number of users starts at 0, and slowly ramps up to the nominal value, where it stays for an extended period of time. The ramp down stage is optional.

We recommend you to always include a ramp-up stage in all your load tests because:

- It lets your system warm up or auto scale to handle the traffic.
- It lets you compare the response time between the low-load and nominal-load stages.
- If you run a load test using our SaaS cloud service, it allows the automated performance alerts to better understand the normal behaviour of your system.

You may also go one step further and configure the load test to resemble your normal and peak conditions more closely. In that case you could configure the load test to stay at 60 users for most of the day, and ramp-up to 100 users during the peak hours of operation, then ramp-down back to normal load.

Make sure you don't go over your normal number of VUs - that's not load testing, but __stress__ testing.

The VU chart for the above configuration should look like this:
![image](https://user-images.githubusercontent.com/70295997/213003831-1dd8d055-9f42-4a7d-be97-27678a91fe26.png)

Performance thresholds are a way to describe your expectations in a formal way, and automatically evaluate those expectations on each test run. Once you have configured the thresholds you'll see a Pass/Fail metric for each threshold, and you will know immediately if your system fulfills your expectations without analyzing the results in detail.
<img width="916" alt="Screenshot 2023-01-17 at 12 20 45 PM" src="https://user-images.githubusercontent.com/70295997/213004357-7429f4be-ab3b-4f96-ae8f-3d60117abcad.png">
If your system crashes under a load test, it means that your load test has morphed into a stress test.

## Stress testing

Stress testing is one of the many different types of load testing.

While load testing is primarily concerned with assessing the systems performance, the purpose of stress testing is to assess the availability and stability of the system under heavy load.

### What is stress testing?
Stress Testing is a type of load testing used to determine the limits of the system. The purpose of this test is to verify the stability and reliability of the system under __extreme conditions__.

To execute a proper stress test, you need a tool to push the system over its normal operations, to its limits, and _beyond the breaking point_.

You typically want to stress test an API or website to determine:
- How your system behaves under extreme conditions.
- What the maximum capacity of your system is in terms of users or throughput.
- What is the breaking point of your system and its failure mode.
- Whether your system will recover without manual intervention after the stress test is over.

When stress testing, configure the test to include more concurrent users or generate higher throughput than:
- Your application typically sees.
- You think your application can handle.

Note that a stress test doesn't overwhelm the system immediately — that's a __spike test__.

A stress test should be configured in many gradual steps, each step increasing the concurrent load of the system.

Classic examples of a need for stress testing are _Black Friday_ or _Cyber Monday_, two days each year that generate multiple times the normal traffic for many websites.

A stress test can be only a couple of steps, or it can be many. No matter how many steps you include, remember this type of test is about finding out what happens when pushing the performance limits of your system — so don’t worry about being too aggressive.

With this said, you probably don't want to run this test against your production environment. I recommend running a stress test in a UAT or staging environment.


### API Stress Test 
The point of this test is to gradually push your APIs beyond its breaking point.
You can create a stress test by properly configuring the options.
For stress tests, <code>ramping-arrival-rate</code> makes a suitable executor, as you can set raw throughput as a value in iterations per second.







----


[18 Top Computer Stress Test Software To Test CPU, RAM And GPU [2023 LIST]](https://www.softwaretestinghelp.com/computer-stress-test-software/)

[15 Best Free CPU Stress Test Software For Windows](https://listoffreeware.com/free-cpu-stress-test-software-windows/)

[Examples & Tutorials](https://k6.io/docs/examples/)



