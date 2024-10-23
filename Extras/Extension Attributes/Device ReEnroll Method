#!/bin/bash

# This script returns the ReEnroll method used.
# Make sure to set the Extension Attribute Data Type to "String".
# https://github.com/AndrewMBarnett/ReEnroll
# by Andrew Barnett (@andrewmbarnett)
# 10.11.2024

# Path to ReEnroll folder
folder_path="/Library/Application Support/ReEnroll"

# ReEnroll property list file
ReEnrollFile="$folder_path/ReEnroll"

if [ -f "${ReEnrollFile}.plist" ]; then
    ReEnrollEnrolledResults=$(defaults read "${ReEnrollFile}" ReEnrollMethod | sed 's/.\{30\}$//' 2> /dev/null)
    [[ -n "${ReEnrollEnrolledResults}" ]] && echo "<result>${ReEnrollEnrolledResults}</result>"
    [[ -z "${ReEnrollEnrolledResults}" ]] && echo "<result>No ReEnroll Method</result>"
else
    echo "<result>No ReEnroll Property List file</result>"
fi

exit 0
