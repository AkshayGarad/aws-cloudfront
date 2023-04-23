# CloudFront
## 1. What is AWS CloudFront?
AWS CloudFront is a content delivery network (CDN) offered by Amazon Web Services (AWS). It allows users to distribute content, such as web pages, videos, and other static and dynamic content, to edge locations around the world. This helps improve the performance of web applications and reduce latency for end-users by caching content closer to them.

CloudFront works by caching content at edge locations, which are AWS data centers located around the world. When a user requests content, CloudFront will route the request to the edge location closest to the user. If the content is already cached at that edge location, CloudFront will serve it directly from the cache, reducing the time it takes to deliver the content to the user. If the content is not cached, CloudFront will retrieve it from the origin server (such as an S3 bucket or an EC2 instance) and cache it at the edge location for future requests.

CloudFront also supports various features, such as SSL/TLS encryption, custom domain names, and access control, which allow users to secure their content and control who has access to it.

Overall, CloudFront provides a scalable and reliable way to distribute content globally, improving the performance and reliability of web applications for end-users around the world.

## 2. What are the benefits of AWS CloudFront?
AWS CloudFront offers several benefits, including:

1. Improved performance: By caching content at edge locations, CloudFront reduces the time it takes for end-users to access content, improving the performance of web applications.

2. Scalability: CloudFront can handle traffic spikes and scale to support growing user bases, ensuring that content is delivered quickly and reliably to all users.

3. Global coverage: With edge locations located around the world, CloudFront can distribute content globally, reaching users in various geographic regions.

4. Cost-effectiveness: CloudFront offers pay-as-you-go pricing, which means users only pay for the data transferred and the number of requests processed.

5. Security: CloudFront supports SSL/TLS encryption and various access control features, allowing users to secure their content and control who has access to it.

6. Integration with other AWS services: CloudFront integrates with various AWS services, such as S3, EC2, and Lambda, allowing users to easily distribute content stored in these services.

Overall, AWS CloudFront provides a reliable and scalable way to distribute content globally, improving the performance and reliability of web applications for end-users around the world.

## 3.	What are the Uses AWS CloudFront?
AWS CloudFront has several uses, including:

1. Content delivery: CloudFront can be used to distribute content, such as images, videos, and other static assets, to end-users around the world, improving the performance of web applications.

2. Live and on-demand streaming: CloudFront supports live and on-demand streaming of audio and video content, allowing users to stream content to a global audience.

3. API acceleration: CloudFront can be used to accelerate APIs, reducing the time it takes for end-users to access data and improving the performance of API-driven applications.

4. Security: CloudFront can be used to secure content by using SSL/TLS encryption and various access control features, such as IP whitelisting and geolocation-based blocking.

5. Website acceleration: CloudFront can be used to accelerate website performance by caching frequently accessed content, reducing the load on origin servers, and improving page load times.

6. Mobile app acceleration: CloudFront can be used to accelerate mobile app performance by caching frequently accessed content, reducing the time it takes for end-users to access content, and improving the user experience.

Overall, AWS CloudFront is a versatile service that can be used to improve the performance, security, and scalability of web applications and content delivery.

## 4. Is Digital Rights Management in built as part of cloudfront ?
CloudFront is a content delivery network (CDN) provided by Amazon Web Services (AWS), which is designed to accelerate the delivery of web content to users. 

Digital Rights Management (DRM) is a method of restricting access to copyrighted digital media, and it is not a built-in feature of CloudFront. However, CloudFront can work with DRM solutions that are provided by third-party vendors. 

For example, you can use CloudFront with AWS Elemental MediaConvert to encode and encrypt your video content, and then use a third-party DRM solution, such as Microsoft PlayReady or Google Widevine, to control access to that content. 

In summary, while CloudFront does not have built-in DRM capabilities, it can be used in conjunction with third-party DRM solutions to protect and control access to digital media content.

## 5.	When to use Amazon Cloudfront?
Amazon CloudFront is a content delivery network (CDN) provided by Amazon Web Services (AWS) that helps to deliver your website content, videos, APIs, and other web assets to users around the world with low latency, high transfer speeds, and high availability. Here are some scenarios where you might want to use Amazon CloudFront:

1. Accelerating content delivery: If you have a global user base and want to deliver your website content or other assets to them with low latency, you can use CloudFront to cache and serve that content from edge locations that are closer to the user, reducing the time it takes to fetch content from your origin server.

2. Reducing server load: By using CloudFront to serve your content from edge locations, you can reduce the load on your origin server, which can help to improve its performance and reduce costs.

3. Securing content: CloudFront provides several security features that can help to protect your content, including SSL/TLS encryption, access controls, and support for third-party digital rights management (DRM) solutions.

4. Scalability: CloudFront is highly scalable and can handle large amounts of traffic without any additional configuration or management, making it ideal for websites and web applications that experience high traffic volumes.

5. Cost-effective: With CloudFront, you only pay for the data transfer and requests that your users make, which can help to reduce costs compared to running your own content delivery infrastructure.

In summary, you can use Amazon CloudFront to accelerate content delivery, reduce server load, secure content, improve scalability, and reduce costs.

## 6.	How can we disable Cache for CloudFront?
You can disable caching for Amazon CloudFront in a few different ways, depending on your specific requirements. Here are a few methods you can use:

1. Disable caching for specific objects: You can disable caching for specific objects by adding a query string parameter to the URL of the object. For example, you can add "?nocache" to the end of the URL to indicate that the object should not be cached. This is useful if you have a specific object that you want to prevent from being cached.

2. Set Cache-Control headers: You can set Cache-Control headers in the HTTP response from your origin server to control how CloudFront caches your content. To disable caching, you can set the "Cache-Control: no-cache" or "Cache-Control: max-age=0" header. This will tell CloudFront not to cache the object, or to revalidate it with the origin server on every request.

3. Create a new cache behavior: You can create a new cache behavior in CloudFront that disables caching for a specific path pattern. To do this, go to the CloudFront distribution settings, select "Behaviors", and then click "Create Behavior". In the behavior settings, you can set the "Minimum TTL" to 0 to disable caching for that behavior.

4. Invalidate cached objects: If you want to disable caching for all objects in a CloudFront distribution, you can invalidate the cached objects. This will remove all cached objects from the edge locations, and subsequent requests will go back to the origin server for the latest version of the content.

In summary, you can disable caching for Amazon CloudFront by adding query string parameters to specific objects, setting Cache-Control headers, creating a new cache behavior, or invalidating cached objects.

## 7.	How can I update files on Amazon’s CDN?
To update files on Amazon's CDN (CloudFront), you need to follow these steps:

1. Upload the new version of the file(s) to your origin server, such as Amazon S3, where your CloudFront distribution is configured to fetch content from.
2. Optionally, you can change the name or path of the file to avoid any conflicts with the previous version of the file.
3. Invalidate the previous version of the file in CloudFront by creating an invalidation request.

To create an invalidation request:

1. Sign in to the AWS Management Console and navigate to the CloudFront console.
2. Click on the distribution for which you want to invalidate files.
3. Click on the "Invalidations" tab.
4. Click on the "Create Invalidation" button.
5. Enter the path or paths of the files that you want to invalidate, using the following format:
    - /path/to/file.ext
    - /path/to/directory/*
6. Click the "Create Invalidation" button to submit your request.

Note that invalidation requests can take some time to process, and there may be a delay before the new version of your files is propagated to all CloudFront edge locations. Additionally, invalidation requests incur charges, so it's important to use them judiciously.

## 8.	What are 2 main components of CloudFront?
The two main components of Amazon CloudFront are:
1. Distribution: A distribution is the main configuration object in CloudFront, which represents a set of edge locations where content is cached and served from. It is created for a specific origin server, such as Amazon S3, EC2 instances, or an HTTP server running outside of AWS. A distribution can have one or more cache behaviors, which specify how CloudFront should handle incoming requests for different URLs.
2. Edge Locations: An edge location is a physical location where CloudFront caches content. Each edge location acts as a gateway between the users and the origin server, providing low-latency access to the content. CloudFront uses a global network of edge locations that are spread across multiple continents to ensure that the content is delivered from the nearest location to the user, minimizing the latency and improving the performance. 
When a user requests a file from the CloudFront distribution, the request is routed to the nearest edge location. If the file is not already cached at that edge location, CloudFront fetches the file from the origin server, caches it at the edge location, and serves it to the user. If the file is already cached at the edge location and it has not expired, CloudFront serves the file directly from the cache, without contacting the origin server.

## 9.	What is CloudFront used for?
Amazon CloudFront is a content delivery network (CDN) service provided by Amazon Web Services (AWS) that is used for accelerating the delivery of static and dynamic content, such as web pages, images, videos, APIs, and software downloads. Here are some common use cases for CloudFront:
1. Static and dynamic content delivery: CloudFront can be used to distribute static and dynamic content across multiple edge locations, reducing the latency and improving the performance for end-users. It can be used to deliver content such as images, videos, HTML pages, JavaScript files, and API responses.
2. Website acceleration: CloudFront can be used to accelerate the delivery of entire websites, by caching static and dynamic content and delivering it from the edge locations. This can reduce the load on the origin server and improve the website's performance for global audiences.
3. Video streaming: CloudFront can be used to deliver on-demand and live video streaming, such as video-on-demand (VoD), live events, and live linear streams. It supports popular streaming protocols such as HTTP Live Streaming (HLS), Dynamic Adaptive Streaming over HTTP (DASH), and Microsoft Smooth Streaming.
4. Software delivery: CloudFront can be used to distribute software updates, patches, and installers, allowing users to download them quickly and reliably from the nearest edge location.
5. API acceleration: CloudFront can be used to accelerate APIs by caching responses at the edge locations and reducing the response time for API calls.
In summary, CloudFront is a versatile service that can be used for accelerating the delivery of various types of content and improving the performance and reliability of web applications and services.
