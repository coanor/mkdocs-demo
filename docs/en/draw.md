
``` mermaid
graph LR
  A[Error] --> B{出错?};
  B -->|Yes| C[啊...];
  C --> D[Debug];
  D --> B;
  B ----> |No| E[Yay!];
```
