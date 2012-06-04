RedisLogger
===========

Central Logging system using Redis.
Logs are very essential and are  distributed on different machines and in different files. 
So,we all want the exception logs from all of our apps to be tracked centrally and viewed in single console. This is yet another a good use case of redis.

To hook up this RedisLogHandler to your application logger, all you need to do is following:

	log = logging.getLogger('')

	rh = RedisLogHandler() #you can specify all redis params here
	rh.setLevel(logging.WARNING) #set the filter for critical logs only
	formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s') #custom formatter
	rh.setFormatter(formatter)

	log.addHandler(rh)

