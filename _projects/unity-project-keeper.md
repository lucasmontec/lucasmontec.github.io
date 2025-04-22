---
name: Unity Project Keeper
type: Tool

# Listing settings

font_awesome_icon: fa-wrench

one_liner: Unity project cleanup based on last edit time.

# Project Page

source_code_url: https://gitlab.com/lucasmontec/unityprojectkeeper
source_code_phrase: The source code is avaliable at GitLab.

---

This is a small tool that I made to quickly cleanup and reduce the size of my Unity project's directory. I have many unity projects and that uses a LOT of disk space. This will delete caches and library folders of older projects automatically.

## Overview

Unity Project Keeper is a command-line tool designed to keep your Unity projects organized by managing, filtering, and cleaning up projects based on their last modification date, Unity version, and other parameters. It allows for batch processing using profiles, making it easy to automate project maintenance.

## Features

 * Register and manage Unity project directories.
 * Scan for Unity projects automatically.
 * Filter projects based on Unity version, modification date, and Git status.
 * Remove 'Library' folders to free up space and force asset reimport.
 * Create and run custom profiles for batch cleanup and maintenance.

## Example calls

Creating a cleaning profile (delete library folder for projects where the last change was more than 2 months ago):
`python UnityProjectKeeper.py --create-profile bl-cleanup gamejams remove-library "if last-change older than 2 months"`

Running a cleaning profile:
`python UnityProjectKeeper.py --run-profile PROFILE_NAME`

Registering a project library directory to be kept:
`python UnityProjectKeeper.py --register /home/user/UnityProjects/GameJams`

Running a profile as a dry run to check what it will do:
`python UnityProjectKeeper.py --dry-run --run-profile bl-cleanup`

Creating an alias to cleanup a library directory while using a blacklist:
`python UnityProjectKeeper.py --create-profile bl-cleanup gamejams remove-library "if last-change older than 6 months" blacklist SuperSecretProject`

Disclaimer: some AI was used to create readmes and boiler-plate code. I coded the tool by hand but AI was used to create some boring methods. No vibe coding here.