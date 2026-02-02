```mermaid
flowchart TD
    Start[شروع] --> Login[ورود]
    Login --> Search[جستجو]
    Search --> CheckAvailable{موجود؟}
    
    CheckAvailable -- بله --> Request[درخواست]
    CheckAvailable -- خیر --> NotAvailable[نمایش موجود نیست]
    
    Request --> CheckMember{وضعیت عضو؟}
    
    CheckMember -- بله --> Process[کاهش موجودی و ثبت]
    Process --> Notify[اعلام تاریخ]
    Notify --> Receive[دریافت]
    Receive --> Use[استفاده]
    Use --> Return[بازگرداندن]
    Return --> Update[افزایش موجودی]
    Update --> End[پایان]
    
    CheckMember -- خیر --> Reject[عدم امکان]
    Reject --> End
    
    NotAvailable --> ReserveDecision{رزرو کند؟}
    ReserveDecision -- بله --> Reserve[رزرو]
    Reserve --> Wait[انتظار]
    ReserveDecision -- خیر --> End