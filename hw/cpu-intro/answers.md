# OSTEP Ch.4 Homework Answers

## Q1
- Prediction / 预测:
Time  PID 0    PID 1    CPU   IOs
1     RUN:cpu  READY    1
2     RUN:cpu  READY    1
3     RUN:cpu  READY    1
4     RUN:cpu  READY    1
5     RUN:cpu  READY    1
6     DONE     RUN:cpu  1
7     DONE     RUN:cpu  1
8     DONE     RUN:cpu  1
9     DONE     RUN:cpu  1
10    DONE     RUN:cpu  1
Total Time: 10
CPU Utilization: 100%
- Reasoning / 理由:
两个进程都各包含5条纯CPU指令（5:100），没有任何I/O操作，所以CPU不会空闲。它们顺序执行，总时间是10个tick，CPU利用率为100%。
- Verified result / 验证结果:
- Analysis / 分析:

## Q2
- Prediction / 预测:
Time  PID 0    PID 1    CPU   IOs
1     RUN:cpu  READY    1
2     RUN:cpu  READY    1
3     RUN:cpu  READY    1
4     RUN:cpu  READY    1
5     DONE     RUN:io   1     1
6     DONE     BLOCKED        1
7     DONE     BLOCKED        1
8     DONE     BLOCKED        1
9     DONE     BLOCKED        1
10    DONE     BLOCKED        1
11    DONE     RUN:io_done 1
Total Time: 11
CPU Utilization: 6/11 ≈ 54.5%
- Reasoning / 理由:
进程0先连续运行4条CPU指令（耗时4个tick），然后结束。进程1开始运行，它先发起一次I/O请求（占用1个tick），随后进入BLOCKED状态等待设备工作（默认5个tick）。因为此时进程0已经结束，没有其他进程可以运行，所以CPU会空闲这5个tick。I/O完成后，进程1再次获得CPU，执行io_done（占用1个tick）。因此总时间为 4+1+5+1=11个tick，CPU忙碌了6个tick。
- Verified result / 验证结果:
- Analysis / 分析:

## Q3
- Prediction / 预测:
- Reasoning / 理由:
- Verified result / 验证结果:
- Analysis / 分析:

## Q4
- Prediction / 预测:
- Reasoning / 理由:
- Verified result / 验证结果:
- Analysis / 分析:

## Q5
- Prediction / 预测:
- Reasoning / 理由:
- Verified result / 验证结果:
- Analysis / 分析:

## Q6
- Prediction / 预测:
- Reasoning / 理由:
- Verified result / 验证结果:
- Analysis / 分析:

## Q7
- Prediction / 预测:
- Reasoning / 理由:
- Verified result / 验证结果:
- Analysis / 分析:

## Q8
- Prediction / 预测:
- Reasoning / 理由:
- Verified result / 验证结果:
- Analysis / 分析: