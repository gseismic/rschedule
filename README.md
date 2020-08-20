# rschedule
Redis-based task distributer and processing pipeline

# 应用场景: 
    - 本地多线程数据处理: key=filename 处理hexun-minute/sina-day-kline数据入库 finio
    - 获取并处理固定列表的网络数据: key=symbol+date，可线程多开，断点继续处理，并行处理
    - 通过数据计算指标

# Known Issues
    fetcher     : fetch data    key -> data  -> pipelines
    scheduler   : 调度运行
    storage     : distributer:key -> storage -> scheduler:key
    key_yielder : 生产Key key_yielder:key -> distributer:key -> storage
    distributer : 把Key推送到中心redis服务器
# ChangeLog
