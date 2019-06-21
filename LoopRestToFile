import requests
import json
import urllib3
import os
import os.path
import sys
import datetime

url = ''
pwd = '*'
user = ''
proxies = {
  'http': '',
  'https': '',
}
# Set proper headers
headers = {"Accept": "application/json"}
# Do the HTTP request
i = 0
x = 0
loop = 1
os.chdir("C:\\test\\")
while loop :
    try:
        response = requests.get(url.format(i*100000), auth=(user, pwd), headers=headers, proxies=proxies, verify=False )
        x = x + 1
        i = i + 1
        response_json = response.json()

        for result in response_json['result']:
            with open("test"+datetime.datetime.now().strftime("_%Y_%m_%d_%H_%M_%S")+".json", "a+") as f:
                f.write(json.dumps(result,f, indent=0,))
        f.close()
        if (len(response_json['result']) < 100000):
            loop = 0
    except:
        print "Query failed for offset {}... Retrying".format(i*100000)
