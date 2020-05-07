# Ajxs

## 原生js实现:
```

        var xmlhttp;
        if (str.length === 0) {
            document.getElementById("txtHint").innerHTML = "";
            return;
            }
        if (window.XMLHttpRequest) {// code for IE7+, Firefox, Chrome, Opera, Safari
            xmlhttp = new XMLHttpRequest();
        } else {// code for IE6, IE5
             xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
        }
        xmlhttp.onreadystatechange = function () {
            if (xmlhttp.readyState === 4 && xmlhttp.status === 200) {
                document.getElementById("txtHint").innerHTML = document.getElementById("txtHint").innerHTML + xmlhttp.responseText;
            }
        };
        xmlhttp.open("GET", "./getJuheJoke.php?page=" + str, true);
        xmlhttp.send();
     }



```

## Jquery实现
1. $("div").load();加载完成后填充div;

```

```

2. 加载成功后回调,有get和post
```
   $.get("./getJuheJoke.php?page=" + str, function (data, status) {
                    $("#txtHint").html($("#txtHint").html() + data);
                });


```

