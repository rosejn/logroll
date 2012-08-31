# LogRoll

A simple logging library for Lua with support for log levels, and printing to
STDIO or files.

## Usage

Log to standard out:

     require 'logroll'
     log = logroll.print_logger()
     log.error("Testing...")  -- => [ERROR - 2012_08_10_11:42:06] - Testing...
     log.warn("Testing...")   -- => [WARN - 2012_08_10_11:42:08] - Testing...
     log.info("Testing...")   -- => [INFO - 2012_08_10_11:42:15] - Testing...

     log.debug("Testing...")  -- => <nothing>
     log.level = logroll.DEBUG
     log.debug("Testing...")  -- => [DEBUG - 2012_08_10_11:42:25] - Testing...

or to a file:

    require 'logroll'
    flog = logroll.file_logger('logs/testing.log')
    flog.debug("Testing file write.")
