## 分布式计算与网络第六次作业





###  习题

#### p22
```
a.
接收方都完整得接收并发送 ACK，但 ACK 全都未传到发送方，接收方的期待序号为 k，而发送方窗口序号为 (k-4)-(k-1)，则发送方更新 base，其序号为 (k, k+3)

b.
如果接收方期待 k，则它一定将比 k-1 小的 ACK 发送出去了，如果要使发送方发送 k-1，那么它至少已经接收到了 k-5 的 ACK。因此 返回的ACK 序号可能是 (k-4, k-1)
```
#### p42
```
TCP使用流水线的方式，发送方有多个未确认的未确认段。超时间隔的加倍不会阻止tcp发送者向网络发送大量第一时间传输的数据包，
即使端到端路径非常拥挤。当出现网络拥塞时，需要一种拥塞控制机制来阻止从上面的应用程序接收到的数据流。

```

#### p44
```
a. 6RTT

b.平均吞吐量为(51 MSS)/(6 RTT)=8.5MSS/RTT。
```