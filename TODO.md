TODO
====

- [P0] Change writes to use f.fileno and os.write()
- [P1] Make MapReduce robust against cases where ".compressme" files disappear before we get to them.  Preopen the files at the start of the mapper (with a warning on fail, which should happen rarely)
- [P4] Preopen the mapper input files in the parent process, pass fd's to child process to avoid race condition with the compressor.
- [P1] Teach the compressor to compress previous days' log files, even if they aren't ".compressme" (since they won't be written to anymore).
- [P1] Write data to [Amazon S3][4] (and delete locally on success)
- [P1] Switch compression to LZMA (and see if we can still keep up)
- [P2] nginx: Check into load-balancing
- [P2] nginx: Accept gzip-encoded submissions
- [P3] Add many tests
- [P3] Add runtime performance metrics using [scales][1] and on-demand perf tests
  using [cProfile][3]
- [P3] Add proper [logging][2]
- [P2] Improve speed of the conversion process
- [P4] Change the RevisionCache to fetch the entire history of Histograms.json and
  then convert incoming revisions to times to find the right version
- [P2] Define data access policy
  -  read access?
  -  retention period

[1]: https://github.com/Cue/scales "Scales"
[2]: http://docs.python.org/2/library/logging.html "Python Logging"
[3]: http://docs.python.org/2/library/profile.html "Python Profilers"
[4]: http://boto.s3.amazonaws.com/s3_tut.html "Using S3 with boto"