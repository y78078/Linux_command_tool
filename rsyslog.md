# rsyslog

## C/C++ example
// gcc giuspexample.c -o giuspexample

#include <syslog.h>

int  main()
{
    setlogmask(LOG_UPTO (LOG_NOTICE));

    openlog("atm", LOG_CONS | LOG_PID | LOG_NDELAY, LOG_LOCAL0);

    syslog(LOG_NOTICE, "Program started by User %d", getuid ());
    syslog(LOG_INFO, "A tree falls in a forest");

    closelog();
    return 0;
}

## rsyslog configure

### /etc/rsyslog.conf
local0.*  /var/log/mylog
### /etc/rsyslog.d/10-custom.conf
ModLoad imfile
$InputFilePollInterval 1
$InputFileName /home/ubuntu/test.log
$InputFileTag testlogs:
$InputFileStateFile testlogs
$InputFileFacility local0
$InputRunFileMonitor
:syslogtag, isequal, "testlogs:" {
  :msg, contains, "HELLO" {
    local0.* /var/log/testlog_error.log
    local0.* @@rsyslogserver.mycompany.com:10514
  }
  stop
}

### reference
https://t.codebug.vip/questions-907872.htm
https://stackoverflow.com/questions/10952515/c-c-syslog-to-custom-file-not-var-log-syslog-but-var-log-mylog-ubuntu-12
