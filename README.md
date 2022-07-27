# faz-reports-custom
Custom reports for FortiAnalyzer

These reports were created using FortiAnalyzer version 7.0.4, so your FortiAnalyzer version should be at least that high in order to import successfully.

N.B. that some reports, including the FortiGate DoS Report, contain charts whose table does not use the FlexInterval (i.e. "time compression") function, in order to get a really high resolution picture of what's happening, but it can also create really large tables, greater than 10K entries, which is the default limit of FortiAnalyzer (which exists to protect against high CPU/RAM utilization). If you run the report and see charts that appear truncated part-way through, it's because you've hit that 10K limit. 

You can override this default limit if you want to see this full graph without truncation, up to a maximum of 10M entries, using the below CLI commands on FortiAnalyzer. If you do this, please pay attention to the RAM and CPU utilization of your FortiAnalyzer, and if it is already tight, you may need to increase resource allocation in vSphere in order to run reports that contain graphs with more than 10,000 entries. 

```
config system report setting
  set max-table-rows <integer between 10,000 and 10,000,000>
end
```
