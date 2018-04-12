import urllib.request
import re

url = 'https://www.google.hu/search?rlz=1C1CHBD_enIT750IT750&q=budapest+weather&oq=budapest&gs_l=psy-ab.3.1.0l4.33427.35502.0.39643.8.8.0.0.0.0.554.982.4j1j5-1.6.0....0...1.1.64.psy-ab..2.6.979...46j0i46k1j0i67k1.TvG1RQfWVoA'

headers = {}
headers ['User-Agent'] = 'Mozilla/5.0 (X11; Linux i686) AppleWebKit/537.17 (KHTML, like Gecko) Chrome/24.0.1312.27 Safari/537.17'
req = urllib.request.Request(url, headers=headers)
resp = urllib.request.urlopen(req)
content = resp.read()
stringtext = str(content)

s2 = '<span class="wob_t" id="wob_tm" '

post1= (stringtext.find(s2))+ 55
post2=post1 + 1
post3=post2 + 1
post4=post3 + 1

Temp1=stringtext[post1] #0
Temp2=stringtext[post1:post3] #00
Temp3=stringtext[post1:post4] #000
Temp4=stringtext[post2] 
Temp5=stringtext[post3]
Temp6=stringtext[post4]

if Temp4 == str('<'):
    print (Temp1 + '°C')

if Temp5 == str('<'):
    print (Temp2 + '°C')

if Temp6 == str('<'):
    print (Temp3 + '°C')
