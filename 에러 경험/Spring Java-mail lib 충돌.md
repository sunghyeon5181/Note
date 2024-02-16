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
  MAIL FROM:<help@kaflixcloud.co.jp>
  250 <help@kaflixcloud.co.jp>, a168ce1865c56c51  
  RCPT TO:<eddie@jejupass.co.kr>
  250 OK
  DEBUG SMTP: Verified Addresses
  DEBUG SMTP:   eddie@jejupass.co.kr
  DATA
  354 Start mail input; end with <CRLF>.<CRLF>
  QUIT
