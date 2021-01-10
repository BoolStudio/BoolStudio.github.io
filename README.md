# TEST PAGE FILES 
<head>
    <meta http-equiv="Content-Type" content="text/html;charset=utf-8"/>
  <title>Now Time</title>
</head>
<body>
  <script>
    Date.prototype.format = function (fmt){
    var o = {
          "y+":this.getFullYear,
          "m+":this.getMonth() + 1,
          "d+":this.getDate(),
          "h+":this.getHours(),
          "m+": this.getMinutes(),
          "s+": this.getSeconds()
    };
     if (/(y+)/.test(fmt)) fmt = fmt.replace(RegExp.$1, (this.getFullYear() + "").substr(4 - RegExp.$1.length));
            for (var k in o)
                if (new RegExp("(" + k + ")").test(fmt)) fmt = fmt.replace(RegExp.$1, (RegExp.$1.length == 1) ? (o[k]) : (("00" + o[k]).substr(("" + o[k]).length)));
            return fmt;
    }
     setInterval("document.getElementById('dateTime').innerHTML = (new Date()).format('yyyy-mm-dd hh:mm:ss');", 10000);
    </script>
 
    <div id="dateTime"></div>
</body>
    
