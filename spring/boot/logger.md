Java标准库内置日志包：java.util.logging(jul)。配置不方便，需要在JVM启动时传递参数。

Commons Logging，第三方日志库，由Apache创建，可以挂接不同的日志系统（默认搜索Log4j，找不到使用JDK Logging）（Log log = LogFactory.getLog(XXX.class)）

Log4j，Commons Logging视为日志接口的话，Log4j可以视为日志实现。

使用Log4j输出一条日志时，通过不同的Appender把同一条日志输出到不同的目的地（console、file、socket、jdbc等）。log -> Appender -> Filter ->Layout -> (Console、File...)

类似于Commons Logging和Log4j，有人开发了SLF4J(接口)和LogBack(实现)。（Logger logger = LoggerFactory.getLogger(getClass())）



Spring Boot内部使用Commons Logging。

（在日志PATTERN前加一个-|方便正则切分的时候和换行的日志区分，如-|%d{yyyy-MM-dd HH:mm:ss.SSS}|%-5level|%X{tid}|%thread|%logger{36}.%M:%L-%msg%n）

日志系统初始化：LoggingApplicationListener根据不同事件做不同处理，ApplicationStartingEvent时调用LoggingSystem的`beforeInitialize()`，ApplicationEnvironmentPreparedEvent时进行初始化。