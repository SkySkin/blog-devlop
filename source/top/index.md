---
title: TopX 
comments: false
keywords: top,文章阅读量排行榜
description: 博客文章阅读量排行榜
---
<div id="top"></div>

<script src="//cdn1.lncld.net/static/js/3.0.4/av-min.js"></script>
<script>AV.initialize("OWVlAu5UqsRl69dQN7vDRGSI-gzGzoHsz", "to1wcPixG8AmJXLUdCwd17th");</script>
<script type="text/javascript">
    var time=0
    var title=""
    var url=""
    var query = new AV.Query('Counter');
    query.notEqualTo('id',0);
    query.descending('time');
    query.limit(1000);
    query.find().then(function (todo) {
        for (var i=0;i<1000;i++){
            var result=todo[i].attributes;
            time=result.time;
            title=result.title;
            url=result.url;
            var content="<a href='"+url+"'>"+title+"</a>"+"<br />"+"<font color='#555'>"+"阅读次数："+time+"</font>"+"<br /><br />";
            document.getElementById("top").innerHTML+=content
        }
    }, function (error) {
        console.log("error");
    });
</script>

<style>.post-description { display: none; }</style>