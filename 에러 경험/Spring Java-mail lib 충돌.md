# Java-mail SMTP 무한로딩 에러

1. 에러 내용
   
  DEBUG SMTP: Found extension "8BITMIME", arg ""   
  DEBUG SMTP: Found extension "SIZE", arg "41943040"   
  DEBUG SMTP: Found extension "AUTH", arg "PLAIN LOGIN"   
  DEBUG SMTP: Found extension "STARTTLS", arg ""   
  DEBUG SMTP: Attempt to authenticate using mechanisms: LOGIN PLAIN DIGEST-MD5 NTLM   
  DEBUG SMTP: AUTH LOGIN command trace suppressed   
  DEBUG SMTP: AUTH LOGIN succeeded   
  DEBUG SMTP: use8bit false   
  MAIL FROM:<XXX@XXX.com> [보내는 사람 메일]   
  250 <XXX@XXX.com>, abcdef  [보내는 사람 메일]   
  RCPT TO:<YYY@YYY.com>   [받는사람 메일]   
  250 OK   
  DEBUG SMTP: Verified Addresses   
  DEBUG SMTP:   YYY@YYY.com   
  DATA   
  354 Start mail input; end with <CRLF>.<CRLF>   
  QUIT   
