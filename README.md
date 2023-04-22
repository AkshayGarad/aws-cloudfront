# CloudFront
## 1. What is AWS CloudFront?
AWS CloudFront is a content delivery network (CDN) offered by Amazon Web Services (AWS). It allows users to distribute content, such as web pages, videos, and other static and dynamic content, to edge locations around the world. This helps improve the performance of web applications and reduce latency for end-users by caching content closer to them.

CloudFront works by caching content at edge locations, which are AWS data centers located around the world. When a user requests content, CloudFront will route the request to the edge location closest to the user. If the content is already cached at that edge location, CloudFront will serve it directly from the cache, reducing the time it takes to deliver the content to the user. If the content is not cached, CloudFront will retrieve it from the origin server (such as an S3 bucket or an EC2 instance) and cache it at the edge location for future requests.

CloudFront also supports various features, such as SSL/TLS encryption, custom domain names, and access control, which allow users to secure their content and control who has access to it.

Overall, CloudFront provides a scalable and reliable way to distribute content globally, improving the performance and reliability of web applications for end-users around the world.