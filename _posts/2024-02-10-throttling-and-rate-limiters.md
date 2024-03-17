---
title: "Designing a Petabyte-scale Rate Limiter"
date: 2024-02-09T15:34:30-04:00
categories:
  - System Design
tags:
  - System Design
---

Challenge: 
  Design a high traffic, petabyte-scale rate limiter

Significance: 

Rate limiters give services/applications the ability to set granular limits on the rate of incoming requests/data ingestion on a per ID/throttling key basis.

Further, this mitigates the risk of exhausting computational resources on the backend, protects from external abuse (intentional and unintentional), and ensures the fair usage/scheduling of clients accessing the service. 

Some key points:

1) Overload protection:
    - The sudden influx of requests won't overload the service, avoiding the risk of degraded performance & downtime. 

2) No DDos Attacks:
    - Protection against malcious traffic loads against a service.   

3) Fair resource allocation:
   - No single client will overallocate resources on the server-side

4) Adjustable limits:
   - Control limits on the server-side for different clients with different load requirements, ensuring high-priority clients receive their adequete resources.
  
5) Cost control: 
   - Control the computational resource costs on the backend.
   
Overall, rate limiters are a fundamental component in the design of state-of-the-art systems, playing a critical role in a service's performance, reliability, and security. 

Choosing an Throttling Algorithm: 

When selecting a catered rate limiting, there are plenty of options to choose from, all of which providing their own various trade-offs provided the required traffic/date ingestion system requirements. 

- token bucket
- leaky bucket
- fixed window counters. 

Assumptions / Requirements:

- Throughput: Relatively small payloads/request (1 MB - 4 MB)
- Traffic Pattern: Relatively uniform 
- High availiability/uptime
- Maintainability
- Adjustability

Architecture: 

Testing and Validation:

PLACEHOLDER
- Load testing


```ruby
def limiter(count)
  puts "Hi, #{count}"
end
limiter('10')
```

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/