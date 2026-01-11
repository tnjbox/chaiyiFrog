flowchart TD
    A[dfs(r, c, stepsLeft, coins)]
    B{stepsLeft == 0?}
    C[更新最佳解]
    D[return 回上一層]
    E[嘗試四個方向]
    F{方向是否在地圖內?}
    G{是否已走過?}
    H[做選擇<br/>標記走過<br/>加入路徑]
    I[遞迴 dfs 下一格]
    J[子遞迴結束]
    K[回溯<br/>path.pop()<br/>visitedMask = oldMask]
    L[所有方向嘗試完]

    A --> B
    B -->|是| C --> D
    B -->|否| E
    E --> F
    F -->|否| E
    F -->|是| G
    G -->|是| E
    G -->|否| H --> I --> J --> K --> E
    E --> L --> D
