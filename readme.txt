Took some python Rijndael code from here: https://gist.github.com/jeetsukumaran/1291836


Added in CBC option

Example using malware C2 sample ab3867c8d002138882ecea67562e2cd112dafe96b26870861dfa927498cfc3f7

>>> k = 'h6g7hjk9f4GT3edGbh8k19geeK0gfq51'
>>> iv = 'BTgtyb67jNqt6ha7jd6g8wh9u6q31YlY'
>>> import rijndael
>>> r = rijndael.Rijndael(k, block_size=32)
>>> import base64
>>> data2 = base64.b64decode('J7dRBs91FvgeSkZc5aTLap9E77jYaFlOdFsmSGiXzzAAEzRrn+5W4tYnhH4MyFD0MCvk7qihflkLHMnAAFI4laCfjt90wuRvIkR6be3iftbafi/WwkY5g89NSu/k6n+m')
>>> r.decrypt_cbc(data2, iv)
'ED386BDBEA794480::::1.5::::Microome Premium ::::'
>>> data3 = base64.b64decode('XPyQ0pPRcdlK+h3Xs1OJoFX2O553RfwCedbfZQSrqis=')
>>> r.decrypt_cbc(data3, iv)
'CHK::::KNOCK 200'
