### gceasy
---
http://gceasy.io/

https://github.com/6yue4me/gceasy

```py
// main/sendMail.py

def sendMail(receivers, sbu, content, ct='plain', attach=None):
  mailhost = "dwmail.dangdang.com"
  mailuser = "ddop"
  mailpass = "*"
  mailpostfix = "dangdang.com"
  me = "hello" + "<" + mailuser + "@" + mailpostfix + ">"
  msg = MIMEText(context, _subtype=ct, _charset='utf-8')
  if attach:
    mtp = MIMEMultipart()
    mtp.attach(msg)
    mtp.attach(attach)
    msg = mtp
  msg['Subject'] = sub
  msg['From'] = me
  msg['To'] = ";".join(receivers)
  
  try:
    smtpObj = smtplib.SMTP()
    smtpObj.connect(mailhost)
    smtpObj.starttls()
    smtpObj.login(mailuser, mailpass)
    smtpObj.sendmail(me, receivers, msg.as_string())
    smtpObj.close()
    return True
  except smtplib.SMPTException, e:
    print str(e)
    return False

```

```
```

```
```


