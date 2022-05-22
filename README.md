# go_video_application

__Constructed a video web service using Go that supports concurrent processing of client requests in high volumes__

* Used Beego Framework to write Restful APIs, and Object Relational Mapping (ORM) to achieve CRUD operations in MySQL.
* Integrated Aliyun AsparaVideo Player SDK for Web to support both Video-on-demand (VOD) and URL-based playback.
* Implemented the viewer real-time on-video-top comment feature (danmu) using WebSocket protocol to enable real-time data transfer between clients and the web server.
* Built the connection pool of Redis server to cache frequently hit information. In combination with the concurrency by Goroutines and Go Channels, we achieved a time speedup of over 3x for listing comments and most popular videos.
* Applied RabbitMQ to asynchronously update ranking information cached in Redis server and send huge amounts of messages, reducing client waiting time by over 230%.
* Accelerated video searching by over 4x in databases with huge amounts of records through Elasticsearch.
* Code for backend part is in the folder ```gyoukuapi```, the frontend part is in the folder ```fyouku```
