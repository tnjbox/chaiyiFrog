flowchart TD
    A[dfs(r, c, stepsLeft, coins)] --> B{stepsLeft == 0?}
    
    B -- 是 --> C[更新最佳解]
    C --> D[return 回上一層]
    
    B -- 否 --> E[嘗試四個方向 for dirs]
    
    E --> F{方向合法?}
    F -- 否 --> E
    
    F -- 是 --> G{是否走過?}
    G -- 是 --> E
    
    G -- 否 --> H[做選擇<br/>setBit + path.push]
    H --> I[dfs(下一格)]
    
    I --> J[子遞迴結束]
    J --> K[回溯<br/>path.pop()<br/>visitedMask = oldMask]
    
    K --> E
    
    E --> L[所有方向都嘗試完]
    L --> D
