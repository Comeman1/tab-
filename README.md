# tab-
原生js实现，点击导航栏，对应背景颜色变化
当页面加载时，首页状态为选中。
步骤：

一、首先遍历所有要点击的element，循环每个element，实现点击。
二、遍历每个点击元素，在点击前，所有元素的背景颜色恢复正常（这也是关键点）
三、遍历元素，判断，如果当前背景是所选颜色，切换类名即可。
4、点击，实现背景变色
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
<html xmlns="http://www.w3.org/1999/xhtml"> 
<head> 
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" /> 
<title>JAVASCRIPT之导航栏鼠标点击变色特效</title> 
<style type="text/css"> 
body { 
  font-size:12px; 
  font-family: Arial, Helvetica, sans-serif; 
} 
.ts_seled { 
  color: #F00; 
} 
.ts_sel { 
  color:#666; 
} 
</style> 
<script language="javascript"> 
window.onload = initLinkStyle; 
function initLinkStyle() { 
  if(document.getElementsByName('myset')){ 
    var arrLink = document.getElementsByName('myset'); 
    for(i = 0; i < arrLink.length; i++) { 
      var link = arrLink[i];     
      link.onclick = clickNav;   
    } 
  } 
} 
/** 
 * 执行点击事件 
 * @param {Object} event 鼠标事件 
 */  
function clickNav(event) { 
  var target = event.currentTarget;   
  //上次选择的a的样式 
  if(document.getElementsByName('myset')){ 
    var arrLink = document.getElementsByName('myset'); 
    for(i = 0; i < arrLink.length; i++) { 
      var link = arrLink[i]; 
         link.className='ts_sel'; 
      if(link.className == 'ts_seled') { 
        link.className = 'ts_sel'; 
      } 
    } 
  } 
  target.className = 'ts_seled'; 
  return false;//阻止浏览器默认事件 
} 
</script> 
</head> 
<body> 
  <ul> 
    <li>           
      <a href="#" rel="external nofollow" rel="external nofollow" rel="external nofollow" name="myset">首页</a> 
    </li> 
    <li> 
      <a href="#" rel="external nofollow" rel="external nofollow" rel="external nofollow" name="myset">联系我们</a> 
    </li> 
    <li> 
      <a href="#" rel="external nofollow" rel="external nofollow" rel="external nofollow" name="myset">帮助</a> 
    </li> 
  </ul> 
</body> 
</html>
