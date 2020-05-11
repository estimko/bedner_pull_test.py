# bedner_pull_test.py
Test for pulling daily box contents from bedner farms

import requests
from bs4 import BeautifulSoup
from datetime import datetime

URL = 'http://www.bedners.com/'

headers = {'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/81.0.4044.138 Safari/537.36'}

page = requests.get(URL, headers=headers)

soup = BeautifulSoup(page.content, 'html.parser')

def check_box:

    fruit_box = soup.find(id='location').get_text()
    substring = '$'
    index_for_day = (fruit_box.find(substring)-1)
    box_day = fruit_box[6:(index_for_day)]
    #box_date = datetime.datetime.strptime(box_day,'%A-%d').strftime('%m-%d-%y')

    if #box_date > #today_date:
        send_mail()
