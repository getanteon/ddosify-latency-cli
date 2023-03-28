# Ddosify latencies CLI tool

The CLI tool interacts with the [ddosify latency API](https://docs.ddosify.com/cloud/api/latency-testing-api). The CLI usage can be found below:

~~~sh
Usage:
  ddosify-latencies run [flags]

Flags:
  -h, --help                    help for run
  -i, --interval string         The amount of waiting time between runs. (default "1m")
  -l, --locations stringArray   The array of locations to be requested. e.g: NA.US.*,NA.EU.* (default [EU.ES.*])
  -o, --output-format string    Output in an specific format. Usage: '-o [ table | yaml | json ]' (default "table")
      --output-locations int    The number of best locations to output. (default 1)
  -r, --runs int                The number of executions. (default 1)
  -t, --target-url string       The target url. e.g: https://google.com
~~~

An example output using `table` output:

~~~sh
┌─────────────┬─────────────────┐
│ LOCATION    │ AVERAGE LATENCY │
├─────────────┼─────────────────┤
│ NA.US.TX.DA │ 9.000000        │
│ NA.US.TX.SA │ 11.000000       │
│ NA.US.NV.LV │ 13.000000       │
└─────────────┴─────────────────┘
~~~

An example output using `json` output:

~~~sh
{
    "result": [
        {
            "location": "NA.US.TX.HO",
            "avgLatency": 3
        },
        {
            "location": "NA.US.VA.AS",
            "avgLatency": 4
        },
        {
            "location": "NA.US.TX.DA",
            "avgLatency": 4
        }
    ]
}
~~~

An example output using `yaml` output:

~~~sh
result:
- location: NA.US.VA.AS
  avglatency: 4
- location: NA.US.TX.DA
  avglatency: 4
- location: NA.US.TX.HO
  avglatency: 4
~~~