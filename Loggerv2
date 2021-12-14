public class loggerjava {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

	}

}
package com.journaldev.log;

import java.util.logging.LogRecord;
import java.util.logging.StreamHandler;

public class MyHandler extends StreamHandler {

    @Override
    public void publish(LogRecord record) {
        //add own logic to publish
        super.publish(record);
    }


    @Override
    public void flush() {
        super.flush();
    }


    @Override
    public void close() throws SecurityException {
        super.close();
    }

}
package com.journaldev.log;

import java.util.Date;
import java.util.logging.Formatter;
import java.util.logging.LogRecord;

public class MyFormatter extends Formatter {

    @Override
    public String format(LogRecord record) {
        return record.getThreadID()+"::"+record.getSourceClassName()+"::"
                +record.getSourceMethodName()+"::"
                +new Date(record.getMillis())+"::"
                +record.getMessage()+"\n";
    }

}
LogManager.getLogManager().readConfiguration(new FileInputStream("mylogging.properties"));# default file output is in user's home directory.
java.util.logging.FileHandler.pattern = %h/java%u.log
java.util.logging.FileHandler.limit = 50000
java.util.logging.FileHandler.count = 1
java.util.logging.FileHandler.formatter = java.util.logging.XMLFormatter

# Limit the message that are printed on the console to INFO and above.
java.util.logging.ConsoleHandler.level = INFO
java.util.logging.ConsoleHandler.formatter = java.util.logging.SimpleFormatter

com.journaldev.files = SEVERE
import java.io.FileInputStream;
import java.io.IOException;
import java.util.logging.ConsoleHandler;
import java.util.logging.FileHandler;
import java.util.logging.Handler;
import java.util.logging.Level;
import java.util.logging.LogManager;
import java.util.logging.Logger;

public class LoggingExample {

    static Logger logger = Logger.getLogger(LoggingExample.class.getName());
    
    public static void main(String[] args) {
        try {
            LogManager.getLogManager().readConfiguration(new FileInputStream("mylogging.properties"));
        } catch (SecurityException | IOException e1) {
            e1.printStackTrace();
        }
        logger.setLevel(Level.FINE);
        logger.addHandler(new ConsoleHandler());
        //adding custom handler
        logger.addHandler(new MyHandler());
        try {
            //FileHandler file name with max size and number of log files limit
            Handler fileHandler = new FileHandler("/Users/pankaj/tmp/logger.log", 2000, 5);
            fileHandler.setFormatter(new MyFormatter());
            //setting custom filter for FileHandler
            fileHandler.setFilter(new MyFilter());
            logger.addHandler(fileHandler);
            
            for(int i=0; i<1000; i++){
                //logging messages
                logger.log(Level.INFO, "Msg"+i);
            }
            logger.log(Level.CONFIG, "Config data");
        } catch (SecurityException | IOException e) {
            e.printStackTrace();
        }
    }

}
package com.journaldev.log;

import java.util.logging.Filter;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class MyFilter implements Filter {

	@Override
	public boolean isLoggable(LogRecord log) {
		//don't log CONFIG logs in file
		if(log.getLevel() == Level.CONFIG) return false;
		return true;
	}

}
1::com.journaldev.log.LoggingExample::main::Sat Dec 15 01:42:43 PST 2021::Msg977
1::com.journaldev.log.LoggingExample::main::Sat Dec 15 01:42:43 PST 2021::Msg978
1::com.journaldev.log.LoggingExample::main::Sat Dec 15 01:42:43 PST 2021::Msg979
1::com.journaldev.log.LoggingExample::main::Sat Dec 15 01:42:43 PST 2021::Msg980
<record>
<date>2021-12-14T17:03:13</date>
<millis>1355533393319</millis>
<sequence>996</sequence>
<logger>com.journaldev.log.LoggingExample</logger>
<level>INFO</level>
<class>com.journaldev.log.LoggingExample</class>
<method>main</method>
<thread>1</thread>
<message>Msg996</message>
</record>
Dec 15, 2021 1:42:43 AM com.journaldev.log.LoggingExample main
INFO: Msg997
Dec 15, 2021 1:42:43 AM com.journaldev.log.LoggingExample main
INFO: Msg998
Dec 15, 2021 1:42:43 AM com.journaldev.log.LoggingExample main
INFO: Msg998
