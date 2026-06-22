# tiku-docs
[
  {
    "name": "不挂科题库",
    "url": "https://api.buguake.com/search",
    "method": "get",
    "data": {
      "q": "${title}"
    },
    "handler": "res=>[res.data.question,res.data.answer]"
  },
  {
    "name": "icodef编程题库",
    "url": "https://api.icodef.com/v1/query",
    "method": "get",
    "data": {
      "keyword": "${title}"
    },
    "handler": "res=>[res.question,res.ans]"
  }
]
