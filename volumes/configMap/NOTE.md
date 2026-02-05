## NOTE
- The usage of when we not use the exact needed of the secret
``` yaml
env: 
    - name: POSTGRES_USER
    valueFrom:
        configMapKeyRef:
            key: WHATEVER_USER
            name: postgres-demo-cm
```

- When you use the specific one
``` yaml
envFrom:
    - configMapRef:
        name: postgres-demo-cm
```

## The four symbols
### `|`

**Literal block (keep everything)**

*   Line breaks are **preserved**
    
*   Newline at the end is **kept**
    

📌 Use when formatting matters (configs, scripts)

### `|-`

**Literal block, but trim last newline**

*   Line breaks are **preserved**
    
*   Final newline is **removed**
    

📌 Use when the app is picky about extra newlines

### `\>`

**Folded block (lines become spaces)**

*   Line breaks become **spaces**
    
*   Newline at the end is **kept**
    

📌 Use for long text that should read as one line

### `\>-`

**Folded block, trim last newline**

*   Line breaks become **spaces**
    
*   Final newline is **removed**
    

📌 Use for compact text without trailing newline