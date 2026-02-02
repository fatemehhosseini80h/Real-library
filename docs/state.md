```mermaid
stateDiagram-v2
    [*] --> Available
    Available --> Reserved : رزرو
    Reserved --> Available : لغو
    Reserved --> Borrowed : تحویل
    
    Available --> Borrowed : امانت
    Borrowed --> ReturnedOnTime : بازگشت به موقع
    Borrowed --> Overdue : دیرکرد
    
    Overdue --> Available : بازگشت با جریمه
    ReturnedOnTime --> Available : بازگشت
    
    Borrowed --> Extended : تمدید
    Extended --> ReturnedOnTime : بازگشت
    Extended --> Overdue : دیرکرد
    
    Overdue --> [*]
    ReturnedOnTime --> [*]