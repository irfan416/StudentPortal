flowchart TD
    A[Start] --> B[Input n]
    B --> C{n <= 1?}
    C -- Yes --> R1[Return False]
    C -- No --> D{n == 2?}
    D -- Yes --> R2[Return True]
    D -- No --> E{n is even?}
    E -- Yes --> R3[Return False]
    E -- No --> F[Set i = 3]
    F --> G{i * i <= n?}
    G -- No --> R4[Return True]
    G -- Yes --> H{n % i == 0?}
    H -- Yes --> R5[Return False]
    H -- No --> I[Set i = i + 2]
    I --> G
