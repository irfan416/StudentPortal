```mermaid
flowchart TD
    A([Start]) --> B{Argument provided?}
    B -- Yes --> C[Parse command-line input]
    C -- Valid --> D{Is number even?}
    C -- Invalid --> E[Print error message] --> F([Exit])

    B -- No --> G[Prompt user for input]
    G --> H[Parse user input]
    H -- Valid --> D
    H -- Invalid --> I[Print invalid input] --> G

    D -- True --> J["even"]
    D -- False --> K["odd"]

    J --> L{Negative?}
    K --> L
    L -- Yes --> M[Append '(n]()
