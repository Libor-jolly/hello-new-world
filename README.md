# hello-new-world
#! /usr/bin/env python

import sys
import rospy
from time import sleep
import threading

import logging
import logging.config

logging.config.fileConfig("coffee_logger.conf")
logger = logging.getLogger("system")
#
logger.debug('This is debug message')
logger.info('This is info message')
logger.warning('warning message')
logger.error('error message')
logger.critical('critical message')


def loghandle(level, msg):
    handler = getattr(logger, level)
    handler("%s: %s" % (level, msg))

loghandle("debug", "..")
loghandle("info", "..")
loghandle("warning", "..")
loghandle("error", "..")
loghandle("critical", "..")
