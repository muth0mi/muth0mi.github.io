---
title: Networking and Logging with KMM
date: 2022-07-16 12:00:00 +0300
categories: [Presentation, Android254]
tags: [mobile, kmm, ktor, kermit]
toc: true
comments: false
media_subpath: /assets/media/post/2022-07-16-networking-and-logging-with-kmm/
image:
  path: /img/banner.png
  lqip: data:image/jpg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAgGBgcGBQgHBwcJCQgKDBQNDAsLDBkSEw8UHRofHh0aHBwgJC4nICIsIxwcKDcpLDAxNDQ0Hyc5PTgyPC4zNDL/2wBDAQkJCQwLDBgNDRgyIRwhMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjL/wAARCAAIABADASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwDl9T01WtyyjpXKlvIkOOooorZu7M4qx//Z
  alt: Networking and Logging with KMM
description: >-
  A presentation for the Android254 community on handling networking and logging with Kotlin Multiplatform Mobile.
---

## Introduction
In this presentation, I get into the essential aspects of networking and logging in Kotlin Multiplatform Mobile (KMM).

When it comes to logging, I emphasize its importance in monitoring, debugging, and ensuring application stability. 
I introduce Kermit, a logging library specifically designed for KMM by [Touchlab](https://github.com/touchlab/Kermit). 
I walk through the process of adding the Kermit dependency, creating and customizing loggers, logging events, 
and even streaming logs. 

On the networking side, I highlight why traditional tools like Retrofit, while powerful, are not ideal for KMM 
projects due to their dependency on platform-specific APIs and Java classes. 
Instead, I showcase Ktor, a lightweight and versatile networking library built for multiplatform use.
I explain the steps to integrate Ktor into a KMM project, from adding dependencies and initializing a networking client to setting up an SDK and making network requests. 

Finally, I tie everything up together and showcase a [Chat application](https://github.com/muth0mi/KmmNetworkingAndLogging.git) 
to demostrate the logging procedures and networking for both REST and Socket events.

## Presentation
This presentation is not recorded. 
It work presented to a live audience at iHub, Nairobi Kenya.

![Presenting KMM Networking and Logging at iHub](img/speaker.jpg){:
  .shadow 
  .normal
  width="1200" 
  lqip="data:image/jpg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAgGBgcGBQgHBwcJCQgKDBQNDAsLDBkSEw8UHRofHh0aHBwgJC4nICIsIxwcKDcpLDAxNDQ0Hyc5PTgyPC4zNDL/2wBDAQkJCQwLDBgNDRgyIRwhMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjIyMjL/wAARCAAIABADASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwDl9T01WtyyjpXKlvIkOOooorZu7M4qx//Z"
}
_Presenting KMM Networking and Logging at iHub_

## Resources
> You can download this presentation from [this link](/assets/media/post/2022-07-16-networking-and-logging-with-kmm/ppt/Android254 - Networking and Logging with KMM.pptx).
{: .prompt-tip }

> You can view source code for this presentation from [this link](https://github.com/muth0mi/KmmNetworkingAndLogging.git).
{: .prompt-tip }
