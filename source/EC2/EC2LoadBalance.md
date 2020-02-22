# Elastic Load Balancer
Balance load a cross multiple web servers

## Types of Load Balanace
- Application Load Balancer
    - operates at ois 7
    - load balance via application layer
    - clever routing base via application layer
- Network Load Balancer
    - operates at layer 4
- Classic Load Balancer
    - legacy purposes
    - not recommended

### Application Load Balancer
- best suited for balancing of HTTP & HTTPS
- sends specific request to specific web servers.

### Network Load Balancer
- Best suited for load balancing of TCP traffic
- for extreme performance is required
- Operating at connection level (Layer 4)
- Capable of handling millions of requests

### Classic Load Balancer
- Legacy ELB
- Can load balance HTTP/HTTPS
- X-Forwaded-For
    - 
- Errors
    - 504
        - gateway timeout error
        - application is having issue
