# Url-Shorten-By-CF-Worker
A URL Shortener Powered by Cloudflare Worker with password protection feature

This project is based on the work done by xyTom/Url-Shorten-Worker. I added a small javascript to prompt password to verify the user since ideally you do not want this service to be completely public because this kind of url shorten site usually will gett abused usage as the original author faced. Again, this is a simple javascript and no security consideration. Once tested with a better code, it will be replaced right away. 
<br/>
<br/>
Cloudflare works has 100k/day requests limistation, which is enough for a small project to use. 
  
# API  [中文API文档](API.md)
  
# Primeros pasos
去Workers KV中创建一个命名空间  
## 1. Go to Workers KV and create a namespace.
<img src="https://cdn.jsdelivr.net/npm/imst@0.0.4/20201205232805.png" width = 640>
  
  <br/>
  <br/>
  
## 2. Create a new worker.

  <br/>
  <br/>
  
  
去Worker的Settings选选项卡中绑定KV Namespace  
## 3. Bind an instance of a KV Namespace to access its data in this new created Worker.
<img src="https://cdn.jsdelivr.net/npm/imst@0.0.4/20201205232536.png" width = 640>

  <br/>
  <br/>


其中Variable name填写`LINKS`, KV namespace填写你刚刚创建的命名空间
## 4.Where Variable name should set as `LINKS` and KV namespace is the namespace you just created in the first step.
<img src="https://cdn.jsdelivr.net/npm/imst@0.0.4/20201205232704.png" width = 640>



  <br/>
  <br/>

复制本项目中的`index.js`的代码到Cloudflare Worker 
## 5. Copy the `index.js` code from this project to Cloudflare Worker. 
<img src="https://photos.51sec.org/file/test1-51sec/2021/09/chrome_EN7fWx3qnx.png" width = 640>



  <br/>
  <br/>

点击Save and Deploy
## 6. Click Save and Deploy



  <br/>
  <br/>

# Demo
  
  - https://go.51sec.org/
  
  <br/>
  <br/>
 
### Note: Because someone abuse this demo website, all the generated link will automatically expired after 24 hours. For long-term use, please deploy your own. To test this demo site, please use code 'cool'. There is a space in the prompt textbox. You might want to delete that space first then enter the password.

注意：由于该示例服务被人滥用，用于转发诈骗网站，故所有由demo网站生成的链接24小时后会自动失效，如需长期使用请自行搭建。



# Example Code for Authentication
This code has been put into index.html file. You might want to change it based on your needs.

```
<SCRIPT language="JavaScript">
var password;
var pass1="cool";
password=prompt('Please enter your password to view this page!',' ');
if (password!=pass1)
    window.location="https://51sec.org";
else
   {
    alert('Password Correct! Click OK to enter!');
    }
</SCRIPT>

```
<br/>

<p align="center">
  <a href="https://51sec.org">
    <img src="https://photos.51sec.org/file/test1-51sec/2021/09/chrome_m3UjIxRh8p.png">
  </a>
  <br />
</p>
<br/>




