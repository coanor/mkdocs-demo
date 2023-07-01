---
tags:
  - Datakit
  - K8s
---

# 更新日志
---

<!--
[:octicons-tag-24: Version-1.4.6](changelog.md#cl-1.4.6) · [:octicons-beaker-24: Experimental](index.md#experimental)
[:fontawesome-solid-flag-checkered:](index.md#legends "支持选举")

    ```toml
    {{ CodeBlock .InputSample 4 }}
    ```

# 外链的添加方式
[some text](http://external-host.com){:target="_blank"}

## x.x.x(YY/MM/DD) {#cl-x.x.x}

本次发布属于迭代发布，主要有如下更新：

### 新加功能 {#cl-x.x.x-new}
### 问题修复 {#cl-x.x.x-fix}
### 功能优化 {#cl-x.x.x-opt}
### 兼容调整 {#cl-x.x.x-brk}
-->

## 1.9.2(2023/06/20) {#cl-1.9.2}

本次发布属于迭代中期发布，增加部分跟中心对接的功能以及一些 bug 修复和优化：

### 新加功能 {#cl-1.9.2-new}

- 新增 [Chrony 采集器](chrony.md)（#1671）
- 新增 RUM Headless 支持（#1644）
- Pipeline
    - 新增 [offload 功能](../developers/pipeline/pipeline-offload.md)（#1634）
    - 重新调整了已有的文档结构（#1686）

### 问题修复 {#cl-1.9.2-fix}

- 修复一些可能导致崩溃的问题（!2249）
- HTTP 网络拨测增加 Host header 支持并修复随机的 error 报错（#1676）
- 修复 Kubernetes 中自动发现 Pod Monitor 和 Service Monitor 问题（#1695）
- 修复 Monitor 问题（#1702/!2258）
- 修复 Pipeline 数据误操作 bug（#1699）

### 功能优化 {#cl-1.9.2-opt}

- 在 Datakit HTTP API 返回中增加更多信息，便于错误排查（#1697/#1701）
- 其它重构（#1681/#1677）
- RUM 采集器增加更多 Prometheus 指标暴露（#1545）
- 默认开启 Datakit 的 pprof 功能，便于问题排查（#1698）

### 兼容调整 {#cl-1.9.2-brk}

- 移除 Kubernetes CRD `guance.com/datakits v1bate1` 对 logging 采集的支持（#1705）

---

!!! example

    === "C lang"
    
        ``` c
        #include <stdio.h>
    
        int main(void) {
          printf("Hello world!\n");
          return 0;
        }
        ```
    
    === "C++ lang"
    
        ``` c++
        #include <iostream>
    
        int main(void) {
          std::cout << "Hello world!" << std::endl;
          return 0;
        }
        ```
