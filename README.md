# Fluentd files used to parse different log files.

<code>fluent_sge.conf</code> parser for SGE, OGE (Oracle Grid Engine, former Sun Grid Engine)
Uses accounting log file from sgemaster. rsyslog directs the offline log file to a fluentd stream process
rsyslog config

```# SGE ACCOUNTING log file
 $InputFileName /$OGE/default/common/accounting
 $InputFileTag sge:
 $InputFileStateFile sge-stat-file
 
 $InputFileSeverity info
 $InputFileFacility local5
 $InputRunFileMonitor
 
 local5.*                                                @fluentdhost:5140
 ``` 
 
<code>fluent_flexlm.conf</code> parser for FlexLM log files used by most EDA companies.

<code>fluent_ibovespa.conf</code> parser for B3 (former bovespa) historical files
