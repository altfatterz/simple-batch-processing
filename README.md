#### CHUNK_SIZE=10 and CONCURRENCY_LIMIT = 1

Each chunk processed in sequence and each `chunk` is processed (`reader`/`processor`/`writer`) with a single thread.

```bash
...
2019-06-13 16:36:00.781  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : MyJob.beforeChunk: SimpleAsyncTaskExecutor-1 ChunkContext:ChunkContext: attributes=[], complete=false, stepContext=SynchronizedAttributeAccessor: [], stepExecutionContext={batch.taskletType=org.springframework.batch.core.step.item.ChunkOrientedTasklet, personItemReader.read.count=0, batch.stepType=org.springframework.batch.core.step.tasklet.TaskletStep}, jobExecutionContext={}, jobParameters={run.id=1}
2019-06-13 16:36:00.793  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:01.793  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Tito, lastName: Tunbridge) into (firstName: TITO, lastName: TUNBRIDGE)
2019-06-13 16:36:01.794  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:02.795  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Ambrose, lastName: Phettis) into (firstName: AMBROSE, lastName: PHETTIS)
2019-06-13 16:36:02.795  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:03.797  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Dallis, lastName: Vaan) into (firstName: DALLIS, lastName: VAAN)
2019-06-13 16:36:03.797  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:04.802  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Rosalyn, lastName: Blowne) into (firstName: ROSALYN, lastName: BLOWNE)
2019-06-13 16:36:04.802  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:05.806  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Fairlie, lastName: Donn) into (firstName: FAIRLIE, lastName: DONN)
2019-06-13 16:36:05.806  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:06.809  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Anatol, lastName: Jellis) into (firstName: ANATOL, lastName: JELLIS)
2019-06-13 16:36:06.809  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:07.812  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Sukey, lastName: Goshawke) into (firstName: SUKEY, lastName: GOSHAWKE)
2019-06-13 16:36:07.813  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:08.816  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Ursula, lastName: Liddington) into (firstName: URSULA, lastName: LIDDINGTON)
2019-06-13 16:36:08.817  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:09.820  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Merrily, lastName: Archbell) into (firstName: MERRILY, lastName: ARCHBELL)
2019-06-13 16:36:09.820  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Thread:SimpleAsyncTaskExecutor-1
2019-06-13 16:36:10.826  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : Converting (firstName: Kare, lastName: Blowne) into (firstName: KARE, lastName: BLOWNE)
2019-06-13 16:36:10.836  INFO 85039 --- [cTaskExecutor-1] ch.helsana.PersonItemProcessor           : MyJob.afterChunk: SimpleAsyncTaskExecutor-1 ChunkContext:ChunkContext: attributes=[], complete=true, stepContext=SynchronizedAttributeAccessor: [], stepExecutionContext={batch.taskletType=org.springframework.batch.core.step.item.ChunkOrientedTasklet, personItemReader.read.count=10, batch.stepType=org.springframework.batch.core.step.tasklet.TaskletStep}, jobExecutionContext={}, jobParameters={run.id=1}
...
``` 

The `job` took:100 seconds


#### CHUNK_SIZE=10 and CONCURRENCY_LIMIT = 5

Each `chunk` processed in sequence and each `chunk` is processed (reader/processor/writer) with 5 threads.

The `job` took:30 seconds


