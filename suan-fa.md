https://coggle.it/diagram/XMljvqW0VAK8JJx0/t/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84-%E7%AE%97%E6%B3%95





正常工作中, curd 太多
并且通常不会处理很复杂的程序, 一般情况下  可扩展性 要求会比时间空间高


所以  业务代码 会经常被 线性展开
比如, 做市box   会把  数量刻度  展开为  box

然后由box 控制价格和数量


正常的思维: 盘口,价格,数量3个维度


盘口刻度 -> (价格  , 数量 )  解耦过后 最多2个维度