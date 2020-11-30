import httpx
import json
url = "https://www.luogu.com.cn/problem/list?page=1&_contentOnly=1"
tmp = httpx.get(url)
abc = json.loads(tmp.text)
currentData = abc['currentData']
problems = currentData['problems']

for i in range(0,len(problems['result'])):
    result = problems['result'][i]
from py2neo import Graph, Node, Relationship

graph = Graph('http://localhost:7474', username='neo4j', password='123456')
for i in range(0,len(abc)):
    problems_abc = Node('Problem',title = abc[i][Problem])
    graph.create(problem_abc)
