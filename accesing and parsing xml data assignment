import urllib.request, urllib.parse, urllib.error
import xml.etree.ElementTree as ET
import ssl

ctx = ssl.create_default_context()
ctx.check_hostname = False
ctx.verify_mode = ssl.CERT_NONE

while True:
    sum = 0
    address = input('Enter location: ')
    if len(address) < 1: break

    print('Retrieving', address)
    uh = urllib.request.urlopen(address, context=ctx)
    data = uh.read()
    print('Retrieved', len(data), 'characters')
    tree = ET.fromstring(data)
    counts = tree.findall('.//count')
    for i in counts :
        count = int(i.text)
        sum += count
    print('count:',len(counts))
    print('sum:',sum)
