---
name: Pooled scroll list
type: Tool

# Listing settings

font_awesome_icon: fa-wrench

one_liner: Yet another reusable view list for Unity.

# Project Page

source_code_url: https://gitlab.com/lucasmontec/pooledscrolllist
source_code_phrase: The source code is avaliable at GitLab.

---

All of the free implementations I hhave found for reusable view lists on unity were lacking features and didn't work correctly when under pressure (high speed scrolling, pushing beyound the last element...).
Because of this, I made my own version of this feature. Not as flexible as the commercial ones but it does the job for single direction lists.
Supports scrolling very fast and supports almost an infinite number of items.

It does use a mock container that is sized according to the virtual content, and this causes floating point errors on the inertia of scroll views in unity when above 10k items.
Im working on this right now replacing the inertial calculation.