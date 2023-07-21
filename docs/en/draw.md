
``` mermaid
graph LR
  A[Error] --> B{出错?};
  B -->|Yes| C[啊...];
  C --> D[Debug];
  D --> B;
  B ----> |No| E[Yay!];
```

``` mermaid
graph LR
  no_data[无数据];
  self_debug{自行排查};
  debug_fail{无果};
  monitor[查看 <a href='https://docs.guance.com/datakit/datakit-monitor/'>monitor</a> 情况];
  debug_input[<a href='https://docs.guance.com/datakit/why-no-data/#check-input-conf'>调试采集器 conf</a>];
  read_faq[查看文档中的 FAQ];
  dql[DQL 查询];
  beyond_usage[数据超量];

  no_data --> self_debug;

  self_debug --> monitor --> debug_fail;
  self_debug --> debug_input --> debug_fail;
  self_debug --> read_faq --> debug_fail;
  self_debug --> dql --> debug_fail;
  self_debug --> beyond_usage --> debug_fail;

  ligai[提交 <a href='https://ligai.cn/'>Ligai</a> 问题];
  trouble_shooting[<a href='https://docs.guance.com/datakit/why-no-data/#bug-report'>收集信息</a>];

  debug_fail --> trouble_shooting;
  trouble_shooting --> ligai;
```

``` mermaid
requirementDiagram

    requirement test_req {
    id: 1
    text: the test text.
    risk: high
    verifymethod: test
    }

    functionalRequirement test_req2 {
    id: 1.1
    text: the second test text.
    risk: low
    verifymethod: inspection
    }

    performanceRequirement test_req3 {
    id: 1.2
    text: the third test text.
    risk: medium
    verifymethod: demonstration
    }

    interfaceRequirement test_req4 {
    id: 1.2.1
    text: the fourth test text.
    risk: medium
    verifymethod: analysis
    }

    physicalRequirement test_req5 {
    id: 1.2.2
    text: the fifth test text.
    risk: medium
    verifymethod: analysis
    }

    designConstraint test_req6 {
    id: 1.2.3
    text: the sixth test text.
    risk: medium
    verifymethod: analysis
    }

    element test_entity {
    type: simulation
    }

    element test_entity2 {
    type: word doc
    docRef: reqs/test_entity
    }

    element test_entity3 {
    type: "test suite"
    docRef: github.com/all_the_tests
    }


    test_entity - satisfies -> test_req2
    test_req - traces -> test_req2
    test_req - contains -> test_req3
    test_req3 - contains -> test_req4
    test_req4 - derives -> test_req5
    test_req5 - refines -> test_req6
    test_entity3 - verifies -> test_req5
    test_req <- copies - test_entity2
```

``` mermaid
erDiagram
    CAR ||--o{ NAMED-DRIVER : allows
    CAR {
        string registrationNumber
        string make
        string model
    }
    PERSON ||--o{ NAMED-DRIVER : is
    PERSON {
        string firstName
        string lastName
        int age
    }
```

``` mermaid
erDiagram
    CAR ||--o{ NAMED-DRIVER : allows
    CAR {
        string traceID_0001
        string parentID_1230
        string spanID_1231
        string metaData_some
    }
    PERSON ||--o{ NAMED-DRIVER : is
    PERSON {
        string traceID_0001
        string parentID_0
        string spanID_1230
        string metaData_some
    }
```

``` mermaid
classDiagram
  direction RL
  class RootSpan{
     string traceID=0001
     string spanID=1230

     string parentID=0

     string metaData=some
  }
  class ChildSpan1{
     string traceID=0001
     string spanID=1231
     string parentID=1230
     string metaData=some
  }

  class ChildSpan2{
     string traceID=0001
     string spanID=1232
     string parentID=1231
     string metaData=some
  }

  ChildSpan1 <|-- RootSpan
  ChildSpan2 <|-- ChildSpan1
```
