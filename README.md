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

The VU chart of a typical load test looks similar to this
![image](https://user-images.githubusercontent.com/70295997/213002518-52a66366-9de7-4b4c-868e-3005a18863ef.png)

Note that the number of users starts at 0, and slowly ramps up to the nominal value, where it stays for an extended period of time. The ramp down stage is optional.

We recommend you to always include a ramp-up stage in all your load tests because:

It lets your system warm up or auto scale to handle the traffic.
It lets you compare the response time between the low-load and nominal-load stages.
If you run a load test using our SaaS cloud service, it allows the automated performance alerts to better understand the normal behaviour of your system.

----

[Examples & Tutorials](https://k6.io/docs/examples/)
