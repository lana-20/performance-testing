# Perfomance Testing

Performance testing is one of the key testing areas in every software development project and especially for mobile apps. Mbile performance testing is a really important and critical part of app development. Mobile users expect an app to start/load within two seconds; otherwise they are unhappy and may delete it.

Testers and developers can use performance tests to discover potential bottlenecks in their software application. Normally, performance testing is done on servers or backend systems to check how the systems or software can handle huge numbers of requests, to meet acceptable results for the users.

Performance tests must be executed in a defined state of the application with hardware resources that are equal to the live backend environment. The collected data must then be analyzed to find possible bottlenecks and problems in the software. Performance testing is a complex topic that should never be underestimated or postponed to the end of the project; it should be done as early
as possible. Key performance figures should be part of the requirements phase of app development in order to start planning right from the beginning.

For mobile apps, performance tests are more complex and need to cover more systems in order to get meaningful results that improve performance.

The typical mobile app relies on a backend system (server) with which it communicates. The app sends requests to the server, which then handles those requests and sends back a response. To send a simple request to a backend system, there are three critical performance areas that need to be covered:
- The server
- The mobile data networks
- The mobile device and app itself

To test the performance of mobile apps, you need to performance-test at least the backend system and the app itself. It is not possible to test the performance of the mobile data networks, and it makes no sense for you as a mobile tester. The network speed and latency can be simulated during the testing phase, but the network speed will be totally different while a user is on the move in real data networks.

Keep the backend system performance in mind and look for further information on the Internet. There are plenty of good tools available to help you set up a performance testing suite. If you want to do performance testing within your project and use tools to do so, keep the following steps in mind as they will help you to define a clear strategy:

1. Plan performance tests early in the development phase.
2. Design the performance tests for your app.
3. Prepare test data and infrastructure (these should be the same as for the live environment).
4. Execute the performance tests.
5. Collect, analyze, and evaluate the data.
6. Find potential bottlenecks and refine the app.
7. Monitor the application changes again to see if the refinements were good enough.

My job, as a Software Quality Engineer, is to focus on performance testing of the mobile app itself.

### Mobile App Performance Testing
When testing the performance of a mobile app, keep it simple and focus on the UI of the app. For example, use a stopwatch and measure the application launch or the delays between certain operations. Measure the loading time of the content such as images, text, or animations that need to be created or processed by the app. Perform those tests several times and note the performed steps in order to reproduce and track possible performance issues. Also, write down how often the problem occurred. If it happens all the time, that’s fine; that is an easy fix. But some problems, especially performance problems, may happen only three out of ten times. It’s therefore important to find the bug and reproduce the behavior.

While testing the app, write down everything that seems slow as it could be a potential performance issue. Manual performance testing should be done on
several devices with different hardware specifications in order to get meaningful results.

Another test that should be done is a comparison between the current app version that is live and available for download in the app stores and the new
release candidate app. Compare both versions in terms of app launch time and all other areas. The new release candidate should not be slower than the current version; otherwise the app will get bad feedback from users.

💥 The comparison should be done on the same hardware; otherwise the results will differ.

If your app contains third-party elements such as advertising or news feeds, check that those elements have no impact on the performance of the app. As an example, you can use a Web proxy tool like Charles Proxy or Fiddler to send the 3rd-party request to a time-out to see that it has no impact on the app’s performance.

Another way to test the performance of the app is to profile and measure the process and operation time of the code. There are plenty of profiler tools available to check the app code for potential bottlenecks and performance issues. This task should be done by the developers, so encourage them to use such tools.

To summarize the simple mobile app performance tests:
- Measure the app’s launch time.
- Check for delays during operations or user interactions.
- Measure the loading time of the content.
- Note everything that seems slow.
- Test on different hardware, especially on slower phones.
- Compare the live app version with the new release candidate.
- Check for third-party elements.
- Use profiling tools to measure the process and operation time of methods
and classes.

These are simple steps to test the performance of a mobile app. If you want more complex and detailed data about the performance of the app, the backend, and the data networks, you’ll need to use a performance testing tool or solution that covers all parts. There are plenty of mobile app performance providers available, so search for them on the Internet and see which one best fits your development and test environment.

# Types of Performance Testing

<img width="800" alt="image" src="https://user-images.githubusercontent.com/70295997/213017758-b5c5e076-a362-466d-9942-a2fcbb28b461.png">

You can use the same test logic for multiple test types. The only thing that changes is the test workload configuration.
Each test type teaches you something different about your system.
- Smoke tests verify that your system can handle minimal load, without any problems.
- Load tests assess system performance in terms of concurrent users or requests per second.
- Stress and Spike tests assess the limits and stability of your system under extreme conditions.
- Soak tests assess the reliability and performance of your system over an extended period of time.

Start with a Smoke test and see how easy it is to run your first load test! After you know that the script works and the system responds to minimal load correctly, you can move on to other test types.

## Smoke testing

A smoke test is a test configured for minimal load.

Each time you write a new test script, it's a good idea to run a smoke to test first, which helps you:
- Verify that your test script doesn't have errors.
- Verify that your system doesn't throw any errors when under minimal load.

The VU chart of a smoke test should look similar to this. You want to use only 1 or 2 VUs.

<img src="https://user-images.githubusercontent.com/70295997/213001364-54174382-52e6-4f6f-a7d9-a1b8f70aa384.png" width=600>

If your smoke test produces any errors, you should either correct the script or fix your environment before you continue.

The test output should look similar to this:
<img width="800" alt="Screenshot 2023-01-17 at 12 10 50 PM" src="https://user-images.githubusercontent.com/70295997/213001588-7a9a8fb6-e390-4450-872b-9cde96077758.png">

Once your smoke test shows zero errors, you can go to the next step and execute a __load__ test to assess the performance of your system.

## Load testing

Load Testing is primarily concerned with assessing the current __system performance in terms of concurrent users or requests per second__.

When you want to understand if your system is meeting the performance goals, this is the type of test you'll run.
<img width="800" alt="Screenshot 2023-01-17 at 12 14 18 PM" src="https://user-images.githubusercontent.com/70295997/213002223-6b982cab-b35e-4a3c-a62b-15d3627fbbd3.png">

You probably have some understanding about the amount of traffic your system is seeing on average and during peak hours. This information will be useful when deciding what your performance goals should be, in other words, how to configure the performance thresholds. Thresholds are a way of ensuring that your system is meeting the performance goals you set for it.

Let's say you're seeing around 60 concurrent users on average and 100 users during the peak hours of operation.

It's probably important to you to meet the performance goals both during normal hours and peak hours, therefore it's recommended to configure the load test with the high load in mind - 100 users in this case.

The VU chart of a typical load test looks similar to this:

<img src="https://user-images.githubusercontent.com/70295997/213002518-52a66366-9de7-4b4c-868e-3005a18863ef.png" width=600>

Note that the number of users starts at 0, and slowly ramps up to the nominal value, where it stays for an extended period of time. The ramp down stage is optional.

We recommend you to always include a ramp-up stage in all your load tests because:

- It lets your system warm up or auto scale to handle the traffic.
- It lets you compare the response time between the low-load and nominal-load stages.
- If you run a load test using our SaaS cloud service, it allows the automated performance alerts to better understand the normal behaviour of your system.

You may also go one step further and configure the load test to resemble your normal and peak conditions more closely. In that case you could configure the load test to stay at 60 users for most of the day, and ramp-up to 100 users during the peak hours of operation, then ramp-down back to normal load.

Make sure you don't go over your normal number of VUs - that's not load testing, but __stress__ testing.

The VU chart for the above configuration should look like this:

<img src="https://user-images.githubusercontent.com/70295997/213003831-1dd8d055-9f42-4a7d-be97-27678a91fe26.png" width=600>

Performance thresholds are a way to describe your expectations in a formal way, and automatically evaluate those expectations on each test run. Once you have configured the thresholds you'll see a Pass/Fail metric for each threshold, and you will know immediately if your system fulfills your expectations without analyzing the results in detail.
<img width="800" alt="Screenshot 2023-01-17 at 12 20 45 PM" src="https://user-images.githubusercontent.com/70295997/213004357-7429f4be-ab3b-4f96-ae8f-3d60117abcad.png">

If your system crashes under a load test, it means that your load test has morphed into a stress test.

## Stress testing

Stress testing is one of the many different types of load testing.

While load testing is primarily concerned with assessing the systems performance, the purpose of stress testing is to assess the __availability and stability of the system under heavy load__.

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
For stress tests, for example, when using JS scripts in Grafana k6, <code>ramping-arrival-rate</code> makes a suitable executor, as you can set raw throughput as a value in iterations per second. The script also includes a recovery stage at the end, where the system is gradually decreasing the load to 0.

<img width="600" alt="Screenshot 2023-01-17 at 12 52 05 PM" src="https://user-images.githubusercontent.com/70295997/213009780-e41007ba-3c42-4e1b-bd8e-7b3c4a6c6175.png">

If your infrastructure is configured to auto-scale, this test will help you to determine:
- How quickly the auto-scaling mechanisms react to increased load.
- Whether any failures happen during scaling events.
The point of the recovery stage is to determine if the system can serve requests once the load decreases to a normal level. If you are testing auto-scaling, you may want to scale down in steps as well to determine if down-scaling is working as you expect it to.

### Spike Testing
Spike testing is a type of stress testing that immediately overwhelms the system with an extreme surge of load.

Spike testing is a variation of a stress testing, but it does not gradually increase the load. Instead it spikes to extreme load over a very short period of time. While a stress test allows the SUT (System Under Test) to gradually scale up its infrastructure, a spike test does not.

Execute spike tests to determine:
- How your system will perform under a sudden surge of traffic.
- Whether your system will recover once the traffic has subsided.
A classic need for a spike testing is if you've bought advertising on a big television event, such as the Super Bowl or a popular singing competition, which will cause a large number of people to see your advertisement and immediately visit your website. If you haven't tested for this scenario and made performance optimizations in advance, the extra traffic can end up being a marketing disaster instead of a great success.

Another typical example is a "HackerNews hug of death": someone links to your website on one of the popular internet forums, like Reddit or HackerNews, which brings thousands of people to your system at once.

Success or failure of a spike test depends on your expectations. Systems generally react in 4 different ways:
- Excellent: system performance is stable during the surge of traffic. Response time is similar during low traffic and high traffic.
- Good: Response time is slower, but the system does not produce any errors. All requests are handled.
- Poor: The system produces errors during the surge of traffic, but recovers to normal after the traffic subsides.
- Bad: System crashes, and does not recover after the traffic subsides.

### API Spike Test

Remember that the point of this test is to suddenly overwhelm the system. Don't be afraid to increase the number of VUs beyond your worst-case prediction. Depending on your needs, you may want to extend the recovery stage to 10 or more minutes to see when the system finally recovers.

Here's a config code snippet for a spike test. As with stress testing, <code>ramping-arrival-rate</code> is a good executor for a spike test.

<img width="600" alt="Screenshot 2023-01-17 at 1 33 51 PM" src="https://user-images.githubusercontent.com/70295997/213017010-39122080-1b02-4b68-8b72-21408e04d315.png">

∴ Stress and spike testing help you prepare for the extreme conditions your system will inevitably encounter in production. Preparing for the inevitable is a sign of maturity in a technical organization. Stress testing not only makes your system more reliable but also decreases the stress level of your Ops and Dev teams. Once your system is stress-proof, you may want to run a soak test to see if other reliability issues don't surface over an extended period.

## Soak Testing

While load testing is primarily concerned with performance assessment, and stress testing is concerned with system stability under extreme conditions, soak testing is concerned with __reliability over a longer period of time__.

...

----

🔗 References:

1. [18 Top Computer Stress Test Software To Test CPU, RAM And GPU [2023 LIST]](https://www.softwaretestinghelp.com/computer-stress-test-software/)

2. [15 Best Free CPU Stress Test Software For Windows](https://listoffreeware.com/free-cpu-stress-test-software-windows/)

3. [Grafana k6](https://k6.io/docs/): [Examples & Tutorials](https://k6.io/docs/examples/) and [Automated performance testing](https://k6.io/docs/testing-guides/automated-performance-testing/)

4. _Hands-On Mobile App Testing: A Guide for Mobile Testers and Anyone Involved in the Mobile App Business_ by _Daniel Knott_. ISBN 978-0-13-419171-3. 2015 Pearson Education, Inc.





