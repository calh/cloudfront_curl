# TODO list

Just some items for features that I'd like to add, but haven't dedicated the time to them.

* Match the IPs into CIDR ranges populated from https://ip-ranges.amazonaws.com/ip-ranges.json
  * especially useful for input IPs, we can toss out non-AWS IPs
  * `client_ip` in ELB logs seems to have a mix of CDN PoPs and client IP addresses?

* Find some other method to grab live logs from a globally active CloudFront distribution,
  publish PoP IPs to an API somewhere?  This would be more efficient than the RIPE measurement.

* Add flags for `--warning_pop_latency` and `--error_pop_latency` to flag an exit code
  if any PoP IP address has a latency above the given threshold.  (in milliseconds)

* Provide a flag for threading out the HTTP checks?  (And the number of threads)  This
  is potentially a double-edged sword -- too high of a concurrency will adversely affect
  the timings.
