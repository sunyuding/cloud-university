# Amazon CloudFront
CDN. Speeds up the delivery of your content to viewers across the globe.

Q. Your company provides media content via the Internet to customers through a paid subscription model. You leverage **Amazon CloudFront** to distribute content from an Amazon S3 bucket. What approach can you use to serve this private content securely to your paid subscribers?
1. [x] Provide signed CloudFront URLs to authenticated users.
2. Add subscriber IP addresses to the CloudFront security group.
3. Use the geo restriction feature to restrict access to all of the paid subscription media at the country level.
4. Provide subscribers with an **Origin Access Identity** to grant them access to the CloudFront distribution.

Q. What does Amazon CloudFront do when it uses HTTP Live Streaming(HLS), HTTP Dynamic Streaming (HDS), Smooth Streaming, and MPEG DASH formats for streaming video?
- Encapsulates video into pull (rather than push) formats that allow clients to adapt to changing conditions for improved performance

Question: Your company needs to provide streaming access to videos to authenticated users around
the world. What is a good way to accomplish this?
- A. Use Amazon Simple Storage Service (Amazon S3) buckets in each region with
website hosting enabled.
- B. Store the videos on Amazon Elastic Block Store (Amazon EBS) volumes.
- C. Enable Amazon CloudFront with geolocation and [signed URLs](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-signed-urls.html).
- D. Run a fleet of Amazon Elastic Compute Cloud (Amazon EC2) instances to host the
videos.

Answer: C. **Amazon CloudFront** provides the best user experience by delivering the data from a geographically advantageous edge location. Signed URLs allow you to control access to authenticated users.

