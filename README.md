#全球疫情历史数据
url = 'https://github.com/datasets/covid-19/blob/master/data/countries-aggregated.csv'
data = pd.read_html(url, header = 0,index_col=0)
data1 = data[0]
data1= data1['Date,Country,Confirmed,Recovered,Deaths'].str.split(',',expand=True)
data1.columns = ['日期','国家','确诊','治愈','死亡','none']
del data1['none']
data1 = data1.set_index('日期')
