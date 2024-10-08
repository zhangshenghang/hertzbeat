---
id: doris_be  
title: 监控：DORIS数据库BE监控      
sidebar_label: DORIS数据库BE  
keywords: [开源监控系统, 开源数据库监控, DORIS数据库BE监控]
---

> 对DORIS数据库FE的通用性能指标进行采集监控。支持DORIS2.0.0。

### 配置参数

|  参数名称  |                       参数帮助描述                        |
|--------|-----------------------------------------------------|
| 监控Host | 被监控的对端IPV4，IPV6或域名。注意⚠️不带协议头(eg: https://, http://) |
| 任务名称   | 标识此监控的名称，名称需要保证唯一性                                  |
| 端口     | 数据库对外提供的端口，默认为8040                                  |
| 查询超时时间 | 设置连接未响应的超时时间，单位ms毫秒，默认3000毫秒                        |
| 数据库名称  | 数据库实例名称，可选                                          |
| 采集间隔   | 监控周期性采集数据间隔时间，单位秒，可设置的最小间隔为30秒                      |
| 是否探测   | 新增监控前是否先探测检查监控可用性，探测成功才会继续新增修改操作                    |
| 描述备注   | 更多标识和描述此监控的备注信息，用户可以在这里备注信息                         |

### 采集指标

#### 指标集合：doris_be_load_channel_count

| 指标名称  | 指标单位 |        指标帮助描述         |
|-------|------|-----------------------|
| value | 无    | 当前打开的 load channel 个数 |

#### 指标集合：doris_be_memtable_flush_total

| 指标名称  | 指标单位 |       指标帮助描述       |
|-------|------|--------------------|
| value | 无    | memtable写入磁盘的个数累计值 |

#### 指标集合：doris_be_plan_fragment_count

| 指标名称  | 指标单位 |            指标帮助描述            |
|-------|------|------------------------------|
| value | 无    | 当前已接收的 fragment instance 的数量 |

#### 指标集合：doris_be_process_thread_num

| 指标名称  | 指标单位 |             指标帮助描述              |
|-------|------|---------------------------------|
| value | 无    | BE 进程线程数。通过 `/proc/pid/task` 采集 |

#### 指标集合：doris_be_query_scan_rows

| 指标名称  | 指标单位 |                                    指标帮助描述                                    |
|-------|------|------------------------------------------------------------------------------|
| value | 无    | 读取行数的累计值。这里只统计读取 Olap 表的数据量。并且是 RawRowsRead（部分数据行可能被索引跳过，并没有真正读取，但仍会记录到这个值中） |

#### 指标集合：doris_be_result_buffer_block_count

| 指标名称  | 指标单位 |       指标帮助描述        |
|-------|------|---------------------|
| value | 无    | 当前查询结果缓存中的 query 个数 |

#### 指标集合：doris_be_send_batch_thread_pool_queue_size

| 指标名称  | 指标单位 |       指标帮助描述        |
|-------|------|---------------------|
| value | 无    | 导入时用于发送数据包的线程池的排队个数 |

#### 指标集合：doris_be_tablet_base_max_compaction_score

| 指标名称  | 指标单位 |           指标帮助描述            |
|-------|------|-----------------------------|
| value | 无    | 当前最大的 Base Compaction Score |

#### 指标集合：doris_be_timeout_canceled_fragment_count

| 指标名称  | 指标单位 |              指标帮助描述              |
|-------|------|----------------------------------|
| value | 无    | 因超时而被取消的 fragment instance 数量累计值 |

#### 指标集合：doris_be_load_rows

| 指标名称  | 指标单位 |         指标帮助描述         |
|-------|------|------------------------|
| value | 无    | 通过 tablet sink 发送的行数累计 |

#### 指标集合：doris_be_all_rowsets_num

| 指标名称  | 指标单位 |     指标帮助描述      |
|-------|------|-----------------|
| value | 无    | 当前所有 rowset 的个数 |

#### 指标集合：doris_be_all_segments_num

| 指标名称  | 指标单位 |      指标帮助描述      |
|-------|------|------------------|
| value | 无    | 当前所有 segment 的个数 |

#### 指标集合：doris_be_heavy_work_max_threads

| 指标名称  | 指标单位 |      指标帮助描述       |
|-------|------|-------------------|
| value | 无    | brpc heavy线程池线程个数 |

#### 指标集合：doris_be_light_work_max_threads

| 指标名称  | 指标单位 |      指标帮助描述       |
|-------|------|-------------------|
| value | 无    | brpc light线程池线程个数 |

#### 指标集合：doris_be_heavy_work_pool_queue_size

| 指标名称  | 指标单位 |             指标帮助描述              |
|-------|------|---------------------------------|
| value | 无    | brpc heavy线程池队列最大长度,超过则阻塞提交work |

#### 指标集合：doris_be_light_work_pool_queue_size

| 指标名称  | 指标单位 |             指标帮助描述              |
|-------|------|---------------------------------|
| value | 无    | brpc light线程池队列最大长度,超过则阻塞提交work |

#### 指标集合：doris_be_heavy_work_active_threads

| 指标名称  | 指标单位 |       指标帮助描述       |
|-------|------|--------------------|
| value | 无    | brpc heavy线程池活跃线程数 |

#### 指标集合：doris_be_light_work_active_threads

| 指标名称  | 指标单位 |       指标帮助描述       |
|-------|------|--------------------|
| value | 无    | brpc light线程池活跃线程数 |

#### 指标集合：doris_be_compaction_bytes_total

|    指标名称    | 指标单位 |            指标帮助描述            |
|------------|------|------------------------------|
| base       | 字节   | Base Compaction 的数据量累计       |
| cumulative | 字节   | Cumulative Compaction 的数据量累计 |

#### 指标集合：doris_be_disks_avail_capacity

| 指标名称  | 指标单位 |                   指标帮助描述                   |
|-------|------|--------------------------------------------|
| path  | 无    | 指定数据目录                                     |
| value | 字节   | `{path="/path1/"}` 表示 `/path1` 目录所在磁盘的剩余空间 |

#### 指标集合：doris_be_disks_total_capacity

| 指标名称  | 指标单位 |                   指标帮助描述                   |
|-------|------|--------------------------------------------|
| path  | 无    | 指定数据目录                                     |
| value | 字节   | `{path="/path1/"}` 表示 `/path1` 目录所在磁盘的全部空间 |

#### 指标集合：doris_be_local_bytes_read_total

| 指标名称  | 指标单位 |           指标帮助描述           |
|-------|------|----------------------------|
| value | 字节   | 由 `LocalFileReader` 读取的字节数 |

#### 指标集合：doris_be_local_bytes_written_total

| 指标名称  | 指标单位 |           指标帮助描述           |
|-------|------|----------------------------|
| value | 字节   | 由 `LocalFileWriter` 写入的字节数 |

#### 指标集合：doris_be_memory_allocated_bytes

| 指标名称  | 指标单位 |                  指标帮助描述                  |
|-------|------|------------------------------------------|
| value | 字节   | BE 进程物理内存大小，取自 `/proc/self/status/VmRSS` |
