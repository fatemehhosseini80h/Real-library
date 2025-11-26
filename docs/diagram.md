
flowchart TB
  subgraph System[سامانه امانت‌دهی کتاب]
    UC_Register[ثبت‌نام]
    UC_Login[ورود]
    UC_AddBook[ثبت/ویرایش کتاب]
    UC_Search[جستجو و مشاهده جزئیات]
    UC_RequestBorrow[درخواست امانت]
    UC_ApproveReject[تأیید/رد درخواست]
    UC_Return[ثبت بازگشت]
    UC_Fine[محاسبه/پرداخت جریمه]
    UC_UserMgmt[مدیریت کاربران]
    UC_BookMgmt[مدیریت کتاب‌ها]
    UC_Reports[گزارش‌ها]
  end

  Actor_Member((کاربر عضو))
  Actor_Owner((مالک کتاب))
  Actor_Admin((مدیر سیستم))

  Actor_Member --> UC_Register
  Actor_Member --> UC_Login
  Actor_Member --> UC_Search
  Actor_Member --> UC_RequestBorrow

  Actor_Owner --> UC_Login
  Actor_Owner --> UC_AddBook
  Actor_Owner --> UC_ApproveReject
  Actor_Owner --> UC_Return

  Actor_Admin --> UC_Login
  Actor_Admin --> UC_UserMgmt
  Actor_Admin --> UC_BookMgmt
  Actor_Admin --> UC_Reports

  UC_Return --- UC_Fine
  UC_RequestBorrow --> UC_ApproveReject
