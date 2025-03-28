---
title: Web 性能
slug: Web/Performance
---
Web 性能是客观的衡量标准，是用户对加载时间和运行时的直观体验。Web 性能指页面加载到可交互和可响应所消耗的时间，以及页面在交互时的流畅度——滚动是否顺滑？按钮能否点击？弹窗能否快速打开，动画是否平滑？Web 性能既包括客观的度量如加载时间，每秒帧数和到页面可交互的时间；也包括用户的对页面内容加载时间的主观感觉。

页面响应时间越长，越多的用户就会放弃该网站。重要的是，通过使体验尽可能早地变得可用和交互，同时异步地加载长尾体验部分，来最大程度地减少加载和响应时间，并添加其他功能以降低延迟。

有很多工具，API 和最佳实践帮助我们测量和改进网页性能。本章对此有所讲解。

## 关键性能指南

{{LandingPageListSubpages}}

## 初学者教程

MDN [Web 性能学习专区](/zh-CN/docs/Learn/Performance) 有着涵盖性能要素的最新教程。 如果您是性能新手，请从这里开始：

- [Web 性能：概述](/zh-CN/docs/Learn/Performance/web_performance_overview)
  - : Web 性能学习路径概述。 在这里开始您的旅程。
- [什么是 Web 性能？](/zh-CN/docs/Learn/Performance/What_is_web_performance)
  - : 该文从一个模块开始，很好地讲述了性能到底是什么——包括我们在考虑性能时需要考虑的工具、指标、API、网络和人群，以及如何使性能成为 Web 开发工作流程的一部分。
- [用户如何看待性能？](/zh-CN/docs/Learn/Performance/perceived_performance)
  - : 比网站在毫秒内响应速度更重要的是，用户对网站的感知速度有多快。这些感知受到页面实际加载时间、空闲、用户交互响应以及滚动和其他动画的平滑度的影响。在本文中，我们将随着最佳练习来提升用户感知（而不是实际时间）并讨论各种加载指标、动画和响应性指标。
- [Web 性能基础](/zh-CN/docs/Learn/Performance/web_performance_basics)
  - : 除了 HTML，CSS，JavaScript 和媒体文件这些前端模块之外，还有其他影响 Web 性能的因素，它们可能会导致应用程序变慢，或在主观和客观上使应用程序变快。有许多与 Web 性能相关的 API、开发人员工具、最佳实践和不当做法。我们将在基础层面上介绍这些影响因素，并提供进阶优化其中每一项性能的链接。
- [HTML 性能特性](/zh-CN/docs/Learn/Performance/HTML)
  - : 标签的某些属性和顺序可能会影响网站性能。 通过最大程度地减少 DOM 节点的数量，确保使用最佳顺序和属性，包括样式、脚本、媒体和第三方脚本等内容，可以大大改善用户体验。 该文详细介绍了如何使用 HTML 来确保最佳性能。
- [多媒体：图像与视频](/zh-CN/docs/Learn/Performance/Multimedia)
  - : Web 性能的最小代价通常是媒体优化。基于每个用户代理的能力、大小和像素密度来服务不同的媒体文件已成为可能。另外，如从背景图像中删除音频轨迹，可进一步提升性能。该文讨论视频、音频和图像内容对性能的影响，以及确保影响尽可能小的方法。
- [CSS 性能特性](/zh-CN/docs/Learn/Performance/CSS_performance)
  - : CSS 对于提高性能来说可能是一个不太重要的优化点，但是某些 CSS 特性对性能的影响比其他特性更大。在该文中，我们将研究一些影响性能的 CSS 属性，并提供样式处理的建议方法，以确保性能不受负面影响。
- [JavaScript 性能最佳实践](/zh-CN/docs/Learn/Performance/JavaScript)
  - : 如果正确使用 JavaScript，则可以提供交互式和身临其境的 Web 体验——否则可能会严重损害下载时间、渲染时间、应用内性能、电池寿命和用户体验。 该文概述了一些值得思考的 JavaScript 最佳实践，以确保即使复杂的内容也尽可能地具有高性能。
- [移动端性能](/zh-CN/docs/Learn/Performance/Mobile)
  - : 随着移动设备上的 Web 访问普及，并且所有移动平台都具有功能完善的 Web 浏览器，但由于受限于带宽、CPU、电池续航等因素，因此考虑这些平台上 Web 内容的性能非常重要。 本文着眼于特定于移动设备的性能注意事项。

## 使用 Performance API

- [Performance API](/zh-CN/docs/Web/API/Performance_API/Using_the_Performance_API)
  - : 该指南介绍了如何使用 [High-Resolution Time](https://w3c.github.io/hr-time/) 标准中定义的 [`Performance`](/zh-CN/docs/Web/API/Performance) 接口。
- [Resource Timing API](/zh-CN/docs/Web/API/Resource_Timing_API/Using_the_Resource_Timing_API)
  - : [资源加载和定时加载](/zh-CN/docs/Web/API/Resource_Timing_API) 这些资源，包括管理资源缓冲区和处理 CORS
- [性能时间线](/zh-CN/docs/Web/API/Performance_Timeline/Using_Performance_Timeline)
  - : [Performance Timeline](/zh-CN/docs/Web/API/Performance_Timeline) 标准定义了对 [`Performance`](/zh-CN/docs/Web/API/Performance) 接口的扩展，以支持应用程序中的客户端延迟测量。这些接口一起可以用来帮助识别应用程序的性能瓶颈。
- [User Timing API](/zh-CN/docs/Web/API/User_Timing_API/Using_the_User_Timing_API)
  - : 使用创建特定于应用程序的时间戳 [user timing API](/zh-CN/docs/Web/API/User_Timing_API)'s “标记”和“度量”条目类型 - 它们是浏览器性能时间轴的一部分。
- [Beacon API](/zh-CN/docs/Web/API/Beacon_API/Using_the_Beacon_API)
  - : 使用 [Beacon](/zh-CN/docs/Web/API/Beacon_API) 接口调度发送给服务器的异步非阻塞请求。
- [Intersection Observer API](/zh-CN/docs/Web/API/Intersection_Observer_API/Timing_element_visibility)
  - : 通过 [Intersection Observer API](/zh-CN/docs/Web/API/Intersection_Observer_API) 学习对元素可见性的监测，并在关注的元素变得可见时被异步通知。

## 其他文档

- [开发者工具中与性能相关的功能](/zh-CN/docs/Tools/Performance)
  - : 本节提供有关如何使用和理解开发人员工具中的性能特性的信息，包括 [Waterfall](/zh-CN/docs/Tools/Performance/Waterfall), [Call Tree](/zh-CN/docs/Tools/Performance/Call_Tree), 和 [Flame Charts](/zh-CN/docs/Tools/Performance/Flame_Chart).
- [使用内置分析器进行分析](/zh-CN/docs/Performance/Profiling_with_the_Built-in_Profiler)

  - : 了解如何使用 Firefox 的内置分析器来分析应用程序性能。

## 各种术语

- {{glossary('Beacon')}}
- {{glossary('Brotli compression')}}
- {{glossary('Client hints')}}
- {{glossary('Code splitting')}}
- {{glossary('CSSOM')}}
- {{glossary('Domain sharding')}}
- {{glossary('Effective connection type')}}
- {{glossary('First contentful paint')}}
- {{glossary('First CPU idle')}}
- {{glossary('First input delay')}}
- {{glossary('First interactive')}}
- {{glossary('First meaningful paint')}}
- {{glossary('First paint')}}
- {{glossary('HTTP')}}
- {{glossary('HTTP_2', 'HTTP/2')}}
- {{glossary('Jank')}}
- {{glossary('Latency')}}
- {{glossary('Lazy load')}}
- {{glossary('Long task')}}
- {{glossary('Lossless compression')}}
- {{glossary('Lossy compression')}}
- {{glossary('Main thread')}}
- {{glossary('Minification')}}
- {{glossary('Network throttling')}}
- {{glossary('Packet')}}
- {{glossary('Page load time')}}
- {{glossary('Page prediction')}}
- {{glossary('Parse')}}
- {{glossary('Perceived performance')}}
- {{glossary('Prefetch')}}
- {{glossary('Prerender')}}
- {{glossary('QUIC')}}
- {{glossary('RAIL')}}
- {{glossary('Real User Monitoring')}}
- {{glossary('Resource Timing')}}
- {{glossary('Round Trip Time (RTT)')}}
- {{glossary('Server Timing')}}
- {{glossary('Speculative parsing')}}
- {{glossary('Speed index')}}
- {{glossary('SSL')}}
- {{glossary('Synthetic monitoring')}}
- {{glossary('TCP handshake')}}
- {{glossary('TCP slow start')}}
- {{glossary('Time to first byte')}}
- {{glossary('Time to interactive')}}
- {{glossary('TLS')}}
- {{glossary('TCP', 'Transmission Control Protocol (TCP)')}}
- {{glossary('Tree shaking')}}
- {{glossary('Web performance', 'Web 性能')}}

## 即将编写的文档

- [JavaScript 性能最佳实践](/zh-CN/docs/Learn/Performance/JavaScript)
  - : JavaScript，如果使用得当，可以提供交互式和身临其境的 web 体验...或者它会严重影响下载时间、渲染时间、应用内性能、电池寿命和用户体验。本文概述了一些 JavaScript 最佳实践，这些实践可以确保即使是复杂内容的性能也是最高的。
- [移动端性能](/zh-CN/docs/Learn/Performance/Mobile)
  - : 由于移动设备上的 web 访问非常流行，而且所有移动平台都有成熟的 web 浏览器，但带宽、CPU 和电池寿命可能有限，因此考虑这些平台上 web 内容的性能非常重要。本文还讨论了移动设备特定的性能考虑因素。
- Web 字体性能
  - : 性能方面一个经常被忽视的方面是 web 字体。Web 字体在 Web 设计中比以往任何时候都更加突出，然而许多开发人员只是简单地将它们从第三方服务中嵌入而不考虑它。在本文中，我们将介绍如何使用高效的文件格式和子设置使字体文件尽可能小。从那以后，我们将继续讨论浏览器如何文本，以及如何使用 CSS 和 JavaScript 功能，以确保您的字体快速呈现，并将对用户体验的干扰降到最低。
- 性能瓶颈

  理解带宽

  - : 带宽是以兆位（Mb）或千位（Kb）为单位的每秒可发送的数据量。本文将解释带宽在富媒体 internet 应用程序中的作用，如何测量带宽，以及如何优化应用程序以最大限度地利用可用带宽。

- TLS 在性能中的作用
  - : TLS 或 HTTPS（我们通常称之为 TLS）对于创建安全和安全的用户体验至关重要。虽然硬件降低了 TLS 对服务器性能的负面影响，但它仍然代表了我们等待浏览器连接到服务器所花费的大量时间。本文解释了 TLS 握手过程，并提供了一些减少时间的技巧，例如 OCSP 装订、HSTS 预加载头，以及资源提示在为第三方屏蔽 TLS 延迟方面的潜在作用。
- 阅读性能图表
  - : 开发人员工具提供有关性能、内存和网络请求的信息。知道如何阅读 [waterfall](/zh-CN/docs/Tools/Performance/Waterfall) charts, [call trees](/zh-CN/docs/Tools/Performance/Call_Tree), traces, [flame charts](/zh-CN/docs/Tools/Performance/Flame_Chart) ,和 [allocations](/zh-CN/docs/Tools/Performance/Allocations) 在浏览器中，开发人员工具将帮助您理解其他性能工具中的瀑布图和火焰图。
- 其他媒体格式
  - : 当涉及到图像和视频时，有比你可能意识到的更多的格式。其中一些格式可以通过进一步减小文件大小来进一步优化富媒体页面。在本指南中，我们将讨论一些替代的媒体格式，如何负责任地使用它们，使不受支持的浏览器不被冷落，以及一些关于将现有资源转换为它们的高级指导。
- 分析 JavaScript bundle
  - : 毫无疑问，JavaScript 是现代 web 开发的重要组成部分。虽然您应该一直努力减少在应用程序中使用的 JavaScript 数量，但是很难知道从哪里开始。在本指南中，我们将向您展示如何分析应用程序的脚本捆绑包，以便您知道您在使用什么，以及如何检测应用程序在捆绑包之间是否包含重复的脚本。
- [延迟加载](/zh-CN/docs/Web/Performance/Lazy_loading)
  - : 在初始页面加载时并不总是需要加载所有 web 应用程序资产。延迟加载是将页面上的资产（如脚本、图像等）的加载推迟到稍后的时间点，即实际需要这些资产的时候。
- 使用动态 import 延迟加载 JavaScript
  - : 当开发人员听到术语“延迟加载”时，他们会立即想到当滚动到视口时加载的折叠图像下方。但是你知道你也可以延迟加载 JavaScript 吗？在本指南中，我们将讨论 dynamic import（）语句，这是现代浏览器中按需加载 JavaScript 模块的功能。当然，由于这个特性不是到处都可用的，我们还将向您展示如何配置您的工具以广泛兼容的方式使用此特性。
- [使用资源提示（resource hints）控制资源传输](/zh-CN/docs/Web/Performance/Controlling_resource_delivery_with_resource_hints)
  - : 浏览器通常比我们更了解资源的优先级和交付，但是他们离克莱里奥万特还很远。本机浏览器特性使我们能够在浏览器应该连接到另一个服务器时提示浏览器，或者在浏览器知道它需要资源之前预先加载资源。如果使用得当，这可以使快速体验看起来更快。在本文中，我们将介绍诸如 rel=preconnect、rel=dns prefetch、rel=prefetch 和 rel=preload 等本机浏览器功能，以及如何使用它们来发挥您的优势。
- [性能预算](/zh-CN/docs/Web/Performance/Performance_budgets)
  - : 营销、设计和销售需求，以及开发人员的经验，通常是广告膨胀、第三方脚本和其他会降低 web 性能的功能。为了帮助设置优先级，设置一个性能预算是很有帮助的：一组在开发阶段不能超过的限制。在本文中，我们将讨论创建和坚持绩效预算。
- [Web 性能检查清单](/zh-CN/docs/Web/Performance/Checklist)
  - : 一个在开发应用程序时要考虑性能清单，其中包含如何实现每个特性的教程链接，包括 Service Worker、性能问题诊断、字体加载最佳实践、客户端提示、创建高效的动画等。
- [Mobile](/zh-CN/docs/Web/Performance/Mobile_performance_checklist) [性能检查清单](/zh-CN/docs/Web/Performance/Checklist)
  - : A concise checklist of performance considerations impacting mobile network users on hand-held, battery operated devices.

## 也可以看看

HTML

- [`<picture>` 元素](/zh-CN/docs/Web/HTML/Element/picture)
- [`<video>` 元素](/zh-CN/docs/Web/HTML/Element/video)
- [The `<source>` Element](/zh-CN/docs/Web/HTML/Element/source)
- [The `<img> srcset` attribute](/zh-CN/docs/Web/HTML/Element/img#Attributes)

  - 响应式图片

- [使用 `rel="preload"` 预加载内容 ——](/zh-CN/docs/Web/HTML/Preloading_content) [(https://w3c.github.io/preload/](https://w3c.github.io/preload/)

CSS

- [will-change](/zh-CN/docs/Web/CSS/will-change)
- GPU v CPU
- 测量布局
- 字体加载最佳实践

JavaScript

- [DOMContentLoaded](/zh-CN/docs/Web/Events/DOMContentLoaded)
- [垃圾回收机制（GC）](/zh-CN/docs/Glossary/Garbage_collection)
- [requestAnimationFrame](/zh-CN/docs/Web/API/window/requestAnimationFrame)

APIs

- [Performance API](/zh-CN/docs/Web/API/Performance_API)
- [Navigation Timing API](/zh-CN/docs/Web/API/Navigation_timing_API)
- [Media Capabilities API](/zh-CN/docs/Web/API/Media_Capabilities_API/Using_the_Media_Capabilities_API)
- [Network Information API](/zh-CN/docs/Web/API/Network_Information_API)
- [PerformanceNavigationTiming](/zh-CN/docs/Web/API/PerformanceNavigationTiming)
- [Battery Status API](/zh-CN/docs/Web/API/Battery_Status_API)
- [Navigator.deviceMemory](/zh-CN/docs/Web/API/Navigator/deviceMemory)
- [Intersection Observer](/zh-CN/docs/Web/API/Intersection_Observer_API)
- [Using the User Timing AP](/zh-CN/docs/Web/API/User_Timing_API/Using_the_User_Timing_API)I
- [Long Tasks API](/zh-CN/docs/Web/API/Long_Tasks_API)
- [High Resolution Timing API](/zh-CN/docs/Web/API/DOMHighResTimeStamp) ([https://w3c.github.io/hr-time/)](https://w3c.github.io/hr-time/)
- [Resource Timing API](/zh-CN/docs/Web/API/Resource_Timing_API/Using_the_Resource_Timing_API)
- [页面可见性](/zh-CN/docs/Web/API/Page_Visibility_API)
- [Cooperative Scheduling of Background Tasks API](/zh-CN/docs/Web/API/Background_Tasks_API)

  - [requestIdleCallback()](/zh-CN/docs/Web/API/Window/requestIdleCallback)

- [Beacon API](/zh-CN/docs/Web/API/Beacon_API/Using_the_Beacon_API)
- 资源提示 - [dns-prefetch](/zh-CN/docs/Web/HTTP/Headers/X-DNS-Prefetch-Control), preconnect, [prefetch](/zh-CN/docs/Web/HTTP/Link_prefetching_FAQ), and prerender
- [Fetchevent.navigationPreload](/zh-CN/docs/Web/API/FetchEvent/navigationPreload)
- [Performance Server Timing API](/zh-CN/docs/Web/API/PerformanceServerTiming)

Headers

- [Content-encoding](/zh-CN/docs/Web/HTTP/Headers/Content-Encoding)
- HTTP/2
- [gZip](/zh-CN/docs/Glossary/GZip_compression)
- Client Hints

工具

- [Firefox 开发者工具中的性能面板](/zh-CN/docs/Tools/Performance)
- 火焰图
- 网络面板
- 瀑布图

其他指标

- 速度指数（Speed Index）和感知速度指数（Perceptual Speed Index）

最佳实践

- [使用 Service Workers](/zh-CN/docs/Web/API/Service_Worker_API/Using_Service_Workers)
- [使用 Web Workers](/zh-CN/docs/Web/API/Web_Workers_API/Using_web_workers)

  - [Web Workers API](/zh-CN/docs/Web/API/Web_Workers_API)

- [PWA](/zh-CN/docs/Web/Apps/Progressive/Offline_Service_workers)
- [缓存](/zh-CN/docs/Web/HTTP/Caching)
- 内容分发网络 (CDN)
