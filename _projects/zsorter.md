---
name: ZSorter
type: Tool

# Listing settings

font_awesome_icon: fa-wrench

one_liner: Sort files by type and size.

# Project Page

source_code_url: https://gitlab.com/lucasmontec/zsorter/
source_code_phrase: The source code is avaliable at GitLab.

---

## Description

I made this small tool to sort files on my system so I could organized recovered files from backups.

This Python script is designed to help you organize files in a directory by scanning for file extensions, displaying statistics, and sorting files based on their frequency and type. The script supports customizable sorting behavior through a YAML configuration file, allowing you to define thresholds, excluded extensions, size-based subfolders, and type directories.

## Features

 * Scan: Recursively scans a directory to count file extensions and saves the results to a YAML file.
 * Stats: Displays statistics from a previously generated scan YAML file.
 * Sort: Sorts files based on the scan results and user-defined settings, moving files to appropriate folders.
 * Sort-Settings: Creates a default YAML file for customizing sort settings.