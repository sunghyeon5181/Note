# Java-mail SMTP 무한로딩 에러

1. 에러 내용   
   ```
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
   ```   
   server log에서 해당 부분까지 나오고 무한로딩이 걸렸습니다. 

3. 원인   
   Spring 프레임워크 pom.xml 파일에   
   javax-mail, javax-mail-api 두개의 라이브러리가 있었고   
   두개가 충돌하면서 mail Form이 발송이 안넘어가는 문제   
   참고 : <https://stackoverflow.com/questions/1010296/javamail-not-sending-subject-or-from-under-jettyrun-war> 


4. 해결방법
   ```   
   <dependency>   
      <groupId>javax.mail</groupId>
      <artifactId>javax.mail-api</artifactId>
      <version>1.5.5</version>
   </dependency>

   <dependency>
      <groupId>javax.mail</groupId>
      <artifactId>mail</artifactId>
      <version>1.4.7</version>
   </dependency>
   ```
   부분에서 javax.mail-api 부분을 주석으로 막고 maven실행후 다시 진행 해보면 문제 해결할수 있다.   

5. 특이사항
   local 서버에서 테스트 할때는 문제 없이 메일이 전송 가능했는데
   운영 서버에 올리니 해당 문제가 발생했는데
   로컬에서 문제 없이 메일 전송이 된 이유는 아직 모르겠다. 
