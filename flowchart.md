flowchart TD
    Start([Start]) --> Input[/Read integer n/]
    Input --> Check1{n <= 1?}
    Check1 -- Yes --> RetFalse1([Return False])
    Check1 -- No --> Check2{n == 2?}
    Check2 -- Yes --> RetTrue1([Return True])
    Check2 -- No --> Check3{n % 2 == 0?}
    Check3 -- Yes --> RetFalse2([Return False])
    Check3 -- No --> InitLoop([i = 3])
    InitLoop --> LoopCond{i * i <= n?}
    LoopCond -- No --> RetTrue2([Return True])
    LoopCond -- Yes --> DivCheck{n % i == 0?}
    DivCheck -- Yes --> RetFalse3([Return False])
    DivCheck -- No --> Inc([i += 2]) --> LoopCond
