# -Web-Crawler---example

步骤：

1. 找到URL等文件源头；
2. 变换格式
3. 写代码
4，代码里面替换小元素

# 1、确定爬虫路径：headers参数
# 2、发送请求 -- requests， 模拟浏览器发送请求
# 3、解析数据 -- json：把json的string转换成python可交互数据类型
# 4、保存数据 -- store在目标文件中

1. URL位置

  一般在inspect - network - all - 从response里面看是否一样。
  常见feed？。。。
  
    # 1、确定爬虫路径：headers参数
         从response里面找，
         找到后要headers里面的URL

    # 2、发送请求 -- requests， 模拟浏览器发送请求
         模拟是浏览器请求，所以要用到 headers = user-agent【模拟】
         response = requests.get（base-URL,headers) 【user- agent】is very important
         res- data = response.text  要里面文本内容

    # 3、解析数据 -- json：把json的string转换成python可交互数据类型
         with open('ku6.json','w') as f:
             f.write(res_data)
             
         建json数据库，with open-建， w - 代表写
         json.cn helps to explain the json
         only title and url
         
         (import json)
         from json to dict loads helps
         json_data = json.loads(res_data)
         
         data_list = json_data['data']
         
         for data in data_list:
             video_name = data['title']
             video_route = data['playUrl']
             
             resquests.get()
    
    # 4、保存数据 -- store在目标文件中
