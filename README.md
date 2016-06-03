# HttpDNS
修改自新浪HttpDNSLib，改项目结构为Android Studio gradle项目，底层请求使用OkHTTP
 
 
 DNSCacheConfig -----  DNS全局配置文件包括（配置文件地址（需要修改），HTTP_DNS 服务器API地址，自己家HTTP_DNS服务API地址，
测速间隔时间，timer轮询器的间隔时间等等）

NetworkManager ----   获取网络类型是wifi还是3g，4g，mac地址，运营商代码，运营商名称

AppConfigUtil  ----   获取缓存文件夹，应用版本名，appkey，设备id

NetworkStateReceiver ---- 网络状态变化广播：网络变化则更新网络信息

DNSCache ---- 对外实例对象:预加载逻辑,获取 HttpDNS信息,过滤无效ip数据,从httpdns 服务器重新拉取数据,根据 host 更新数据

DomainModel ---- 域名数据模型：域名，运营商，域名过期时间，域名最后查询时间

DnsCacheManager ---- 缓存管理：获取缓存，插入本来cache缓存，获取即将过期的domain数据

DnsManager ---- 管理请求dns server，解析该domain域名：包括SinaHttpDns，HttpPodDns，UdpDns，LocalDns

SinaHttpDns ---- 连接sina的httpDns类

HttpPodDns ---- 连接DnsPod d+的httpDns类

DnsConfig ---- SinaHttpDns，HttpPodDns类需要的信息配置：如HTTP_DNS 服务器API地址，自己家HTTP_DNS服务API地址（在DNSCacheConfig中使用）

UdpDns ---- 连接dns服务器类 用socket的udp方式连接查询

LocalDns ---- 运营商默认的查询方式

HttpDnsPack ---- 获取到的httpDns数据，用于封装几种请求方式得到的数据

IJsonParser ---- 自己httpDns服务器返回的数据解析

SpeedtestManager ---- 用来测试服务器返回的ip的连接速度，为了更好地连接

Socket80Test ---- socket测试ip连接80端口的速度

PingTest ---- 用ping指令测试ip连接速度





