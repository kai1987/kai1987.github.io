---
title: nodejs,redis cluster
date: 2020-03-06 14:54:23
tags:
---

there are different redis client for node.js, how to choose when you start a new project.

* [ioredis](https://github.com/luin/ioredis#readme)

    A robust, performance-focused and full-featured Redis client for Node.js.

    If you want to use redis cluster model or some redis service like AWS elastcache, use this one.

* [node-redis or redis](https://github.com/NodeRedis/node-redis)

    most common used one.  
    if you have old codebase and want to try cluster, you can try [redis-clustr](https://github.com/gosquared/redis-clustr), but I think it's not a good idea.

-------

know problem with node-redis on aws elastcache

[CROSSSLOT Keys in request don't hash to the same slot](https://aws.amazon.com/cn/premiumsupport/knowledge-center/elasticache-crossslot-keys-error-redis/)



