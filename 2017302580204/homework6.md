P11.  
如果从“等待来自下层的1”中删除，不会影响正常工作，因为 sndpkt 已经被生成了。  
但是如果从“等待来自下层的0”中删除，而且接收方刚刚启动（处于初始状态），  
sndpkt 是一个错误的值（很可能是一个随机值），那么发送方会认为 ACK 损坏并重发分组，  
接收方会继续发送错误值，浙江导致一个死锁。  

P12.  
仅有一个比特差错时，协议正常工作，只不过可能比 rdt3.0 发送方反应更快。  
而当定时器时间过短时，每一个超时重发的分组都将会导致正在发送的包重发，  
这样从第一个包累积到第n个包，分组发送的次数将趋于无穷。  

P43.  
流量控制将无法适用，因为接受缓存足够大。  
没有丢包、没有超时，因此拥塞控制也无法适用。  
无需适用任何措施，当发送缓存满载时，自动就慢下来了  
