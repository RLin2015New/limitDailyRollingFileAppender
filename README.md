# limitDailyRollingFileAppender

基于 DailyRollingFileAppender 实现的，限定单文件大小，如果文件达到指定大小，则以logs.log.2018-05-13.3（文件名.日期.备份号）的方式备份。

最大每日可生成文件、单文件大小可按下述方式配置。


log4j.logger.testMsg=DEBUG,testMsg
log4j.appender.testMsg=com.log4j.LimitDailyRollingFileAppender
log4j.appender.testMsg.File=./logs/logs.log
log4j.appender.testMsg.layout=org.apache.log4j.PatternLayout
log4j.appender.testMsg.layout.ConversionPattern=%d{yyyy-MM-dd HH:mm:ss,S} %5p (%c:%L) - %m%n
log4j.appender.testMsg.Encoding=utf-8
#最多支持每天生成1000个日志文件（默认1000）
log4j.appender.testMsg.maxBackUpSize=1000  
#每个日志文件最多允许记录1024*1024=1048576  个字节（默认300M）
log4j.appender.testMsg.maxFileSize=1048576  
