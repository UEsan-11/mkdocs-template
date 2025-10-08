# Mermaid
---

[Reference](https://mermaid-js.github.io/mermaid/)

## Flowchart
---

``` mermaid
graph LR;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

## Sequence Diagram
---

``` mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

## State Diagram
---

``` mermaid
stateDiagram-v2
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```
