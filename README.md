import requests
import json
content = input("请输入你的内容：")
url = 'http://fanyi.youdao.com/translate?smartresult=dict&smartresult=rule'
from_data = {
'i': content,
'from': 'AUTO',
'to': 'AUTO',
'smartresult': 'dict',
'client': 'fanyideskweb',
'salt': '16112359189517',
'sign': '0f8564bd82b7706e773a050410f712a5',
'lts': '1611235918951',
'bv': '8d869977ed9730c759a83d50a1f65ed0',
'doctype': 'json',
'version': '2.1',
'keyfrom': 'fanyi.web',
'action': 'FY_BY_CLICKBUTTION'
}
response = requests.post(url,from_data)
trans_json = response.text
trans_dict = json.loads(trans_json)
result = trans_dict['translateResult'][0][0]['tgt']
print("翻译结果")
print(result)
