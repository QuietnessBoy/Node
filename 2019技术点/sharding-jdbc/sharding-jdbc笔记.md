## sharding-jdbc

#### 分片策略
  数据源分片策略（DatabaseShardingStrategy）
  表分片策略（TableShardingStrategy）

#### 分片算法
 Sharding提供5种分片策略：
#### 1. 标准分片策略（StandardShardingStrategy）
提供对SQL语句中的=, IN和BETWEEN AND的分片操作支持。

StandardShardingStrategy只支持单分片键，提供PreciseShardingAlgorithm和RangeShardingAlgorithm两个分片算法。

  * PreciseShardingAlgorithm是必选的，用于处理=和IN的分片。

  * RangeShardingAlgorithm是可选的，用于处理BETWEEN AND分片，如果不配置RangeShardingAlgorithm，SQL中的BETWEEN AND将按照全库路由处理。

#### 2. 复合分片策略（ComplexShardingStrategy）
提供对SQL语句中的=, IN和BETWEEN AND的分片操作支持。

ComplexShardingStrategy支持多分片键，由于多分片键之间的关系复杂，因此Sharding-JDBC并未做过多的封装，而是直接将分片键值组合以及分片操作符交于算法接口，完全由应用开发者实现，提供最大的灵活度。

#### 3. Inline表达式分片策略（InlineShardingStarategy）
Inline表达式分片策略。使用Groovy的Inline表达式，提供对SQL语句中的=和IN的分片操作支持。

InlineShardingStrategy只支持单分片键，对于简单的分片算法，可以通过简单的配置使用，从而避免繁琐的Java代码开发，如: tuser${user_id % 8} 表示t_user表按照user_id按8取模分成8个表，表名称为t_user_0到t_user_7。


#### 4. Hint非Sql解析方式分片策略(HintShardingStarategy)
通过Hint而非SQL解析的方式分片的策略。

#### 5. 不分片策略(NoneShardingStrategy)
不分片的策略。

#### 自定义分片算法
Sharding提供了以下4种算法接口：

* PreciseShardingAlgorithm
* RangeShardingAlgorithm
* HintShardingAlgorithm
* ComplexKeysShardingAlgorithm
