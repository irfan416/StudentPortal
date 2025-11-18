```mermaid
flowchart TD
    Start([Start]) --> CheckArg{argc > 1?}
    CheckArg -- Yes --> TryParseCmd[/Call _parse_int(sys.argv[1])\]
    TryParseCmd -- Success --> ParityCheck{is_even(num)?}
    TryParseCmd -- ValueError --> PrintCmdErr([Print "Please provide a valid integer..."]) --> ExitErr([Exit with code 1])
    CheckArg -- No --> PromptLoop([Prompt user: "Enter an integer:"])
    PromptLoop --> TryParseInput[/Call _parse_int(input)\]
    TryParseInput -- Success --> ParityCheck
    TryParseInput -- ValueError --> PrintInvalid([Print "Invalid input. Please enter a whole number..."]) --> PromptLoop

    ParityCheck -- True --> Result["even"]
    ParityCheck -- False --> Result["odd"]

    Result --> NegCheck{num < 0?}
    NegCheck -- Yes --> Output["append ' (negative input)'"]
    NegCheck -- No --> Output

    Output --> PrintFinal([Print final result])
    PrintFinal --> End([End])
```flowchart TD
    Start([Start]) --> CheckArg{argc > 1?}
    CheckArg -- Yes --> TryParseCmd[/Call _parse_int(sys.argv[1])\]
    TryParseCmd -- Success --> ParityCheck{is_even(num)?}
    TryParseCmd -- ValueError --> PrintCmdErr([Print "Please provide a valid integer..."]) --> ExitErr([Exit with code 1])
    CheckArg -- No --> PromptLoop([Prompt user: "Enter an integer:"])
    PromptLoop --> TryParseInput[/Call _parse_int(input)\]
    TryParseInput -- Success --> ParityCheck
    TryParseInput -- ValueError --> PrintInvalid([Print "Invalid input. Please enter a whole number..."]) --> PromptLoop

    ParityCheck -- True --> Result["even"]
    ParityCheck -- False --> Result["odd"]

    Result --> NegCheck{num < 0?}
    NegCheck -- Yes --> Output["append ' (negative input)'"]
    NegCheck -- No --> Output

    Output --> PrintFinal([Print final result])
    PrintFinal --> End([End])
