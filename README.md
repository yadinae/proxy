# proxy
打开Github，新建一个仓库
pages1 pages1

点击creating a new file按钮
创建一个文件名为_worker.js的文件，然后复制以下代码
export default {
  async fetch(request, env) {
    const url = new URL(request.url);
    url.host = "api.openai.com";
    // openai is already set all CORS heasders 
    return fetch(url, {
      headers: request.headers,
      method: request.method,
      body: request.body,
      redirect: 'follow'
    });
  }
}
pages1 pages1

然后点Commit new file保存
pages1

扩展
如果想中转别的网站把下面代码中的TELEGRAPH_URL换为别网站就行

代码
部署
登录到Cloudflare控制台.

在帐户主页中，选择pages>  Create a project > Connect to Git Cloudflare_pages1.png

选择你 Fork 的项目存储库，在Set up builds and deployments部分中，选择None作为您的框架预设。其他为空。(即保持默认即可)

点击Save and Deploy部署

然后点Continue to project即可看到访问域名

Cloudflare_pages6.png

用法
参考
