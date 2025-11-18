```mermaid
flowchart TD
    A([Start]) --> B{argc > 1?}
    B -- Yes --> C[/_parse_int(sys.argv[1])\]
    C -- Success --> D{is_even(num)?}
    C -- ValueError --> E([Print "Please provide a valid integer..."]) --> F([Exit with code 1])

    B -- No --> G([Prompt user: "Enter an integer:"])
    G --> H[/_parse_int(input)\]
    H -- Success --> D
    H -- ValueError --> I([Print "Invalid input. Please enter a whole number..."]) --> G

    D -- True --> J["result = 'even'"]
    D -- False --> K["result = 'odd'"]

    J --> L{num < 0?}
    K --> L
    L -- Yes --> M["append ' (negative input)'"]
    L -- No --> M

    M --> N([Print result])
    N --> O([End])
```
