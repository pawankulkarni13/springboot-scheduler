# springboot-scheduler


You can enable scheduling simply by adding the @EnableScheduling annotation to the main application class or 
one of the Configuration classes.

Any method which is annotated with @Scheduled annotation follow two rules
1. The method should have a void return type.
2. The method should not accept any arguments.


By Default tasks scheduled are run in the default thread pool created by Spring.
we can customize it as in SpringbootSchedulerAppConfig to use a custom thread pool and 
configure the load as task are scheduled


Sample logs captured :
`
~~~~~~2020-11-13 10:51:47.400  INFO 42020 --- [     pawan-tp-1] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:51:47
2020-11-13 10:51:47.400  INFO 42020 --- [           main] c.s.s.SpringbootSchedulerApplication     : Started SpringbootSchedulerApplication in 0.549 seconds (JVM running for 0.989)
2020-11-13 10:51:47.400  INFO 42020 --- [     pawan-tp-2] c.s.s.scheduler.SpringbootScheduler      : Fixed Delay Task :: Execution Time - 10:51:47
2020-11-13 10:51:49.400  INFO 42020 --- [     pawan-tp-3] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:51:49
2020-11-13 10:51:51.398  INFO 42020 --- [     pawan-tp-3] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:51:51
2020-11-13 10:51:52.400  INFO 42020 --- [     pawan-tp-5] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:51:52
2020-11-13 10:51:53.399  INFO 42020 --- [     pawan-tp-4] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:51:53
2020-11-13 10:51:54.400  INFO 42020 --- [     pawan-tp-3] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:51:54
2020-11-13 10:51:54.401  INFO 42020 --- [     pawan-tp-1] c.s.s.scheduler.SpringbootScheduler      : Fixed Delay Task :: Execution Time - 10:51:54
2020-11-13 10:51:55.399  INFO 42020 --- [     pawan-tp-5] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:51:55
2020-11-13 10:51:56.397  INFO 42020 --- [     pawan-tp-2] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:51:56
2020-11-13 10:51:57.398  INFO 42020 --- [     pawan-tp-4] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:51:57
2020-11-13 10:51:58.400  INFO 42020 --- [     pawan-tp-3] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:51:58
2020-11-13 10:51:59.399  INFO 42020 --- [     pawan-tp-5] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:51:59
2020-11-13 10:52:00.000  INFO 42020 --- [     pawan-tp-2] c.s.s.scheduler.SpringbootScheduler      : Cron Task :: Execution Time - 10:52:00
2020-11-13 10:52:00.398  INFO 42020 --- [     pawan-tp-4] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:52:00
2020-11-13 10:52:01.400  INFO 42020 --- [     pawan-tp-3] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:52:01
2020-11-13 10:52:01.405  INFO 42020 --- [     pawan-tp-5] c.s.s.scheduler.SpringbootScheduler      : Fixed Delay Task :: Execution Time - 10:52:01
2020-11-13 10:52:02.399  INFO 42020 --- [     pawan-tp-1] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:52:02
2020-11-13 10:52:03.401  INFO 42020 --- [     pawan-tp-2] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:52:03
2020-11-13 10:52:04.397  INFO 42020 --- [     pawan-tp-4] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:52:04
2020-11-13 10:52:05.402  INFO 42020 --- [     pawan-tp-3] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:52:05
2020-11-13 10:52:06.400  INFO 42020 --- [     pawan-tp-1] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:52:06
2020-11-13 10:52:07.399  INFO 42020 --- [     pawan-tp-2] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:52:07
2020-11-13 10:52:08.400  INFO 42020 --- [     pawan-tp-4] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:52:08
2020-11-13 10:52:08.407  INFO 42020 --- [     pawan-tp-3] c.s.s.scheduler.SpringbootScheduler      : Fixed Delay Task :: Execution Time - 10:52:08
2020-11-13 10:52:09.399  INFO 42020 --- [     pawan-tp-1] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:52:09
2020-11-13 10:52:10.402  INFO 42020 --- [     pawan-tp-5] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:52:10
2020-11-13 10:52:11.402  INFO 42020 --- [     pawan-tp-2] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:52:11
2020-11-13 10:52:12.399  INFO 42020 --- [     pawan-tp-4] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task with Initial Delay :: Execution Time - 10:52:12
2020-11-13 10:52:13.402  INFO 42020 --- [     pawan-tp-1] c.s.s.scheduler.SpringbootScheduler      : Fixed Rate Task :: Execution Time - 10:52:13~~~~~~
`