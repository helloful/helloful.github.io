
## 教育背景

- 2017-2021，本科，上海大学，计算机工程与科学学院，计算机科学与技术

- 2021-2024，硕士，复旦大学，计算机技术学院，电子信息

## 专业技术

- 熟练使用`c/c++`,`java`,`python`等主流开发开发语言


## 开发项目经历

- 暂未填写

## 实习经历

- 暂未填写

## 工作经历

- 暂未填写

## 兴趣爱好

- 暂未填写


## 公益活动

- 代码效果展示

```

export default function Detail(props) {
  //prop是接收的getInitialProps获取的api接口返回来的对象
  const renderer = new marked.Renderer();

  marked.setOptions({
      renderer: renderer, 
      gfm: true,
      pedantic: false,
      sanitize: false,
      tables: true,
      breaks: false,
      smartLists: true,
      smartypants: false,
      highlight: function (code) {
          return hljs.highlightAuto(code).value;
      }
    }); 
    let html = marked(props.data[0].articlecontent) 

 return (
 <div>
	<div className="detailed-content" 
	       dangerouslySetInnerHTML={{__html:html}}   //react用dangerouslySetInnerHTML解析有html的内容，内容vue中的v-html
	        >
	 </div>
 </div>
)
}


Detail.getInitialProps = async (context)=>{   //接收路由传过来的值
  console.log('aaa'+context.query.id)
  let result = await fetch('http://127.0.0.1:7001/default/getArticleId/'+context.query.id,{
})
let res = await result.json() //必须通过此方法才可返回数据
console.log('远程获取数据结果:'+JSON.stringify(res))
 return res  
}

```

