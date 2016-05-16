Although get5 converts all authentication formats to steam64 internally, get5 supports multiple forms of steamids as input for player authentication. This page describes their format for users to understand what is gong on.


## Steam2

This is currently what you see in CS:GO when you type ``status`` in console. It is of the format "STEAM_x:y:z". The y:z element is unique for each account. The x value is always 1 in CS:GO, but may be seen as 0 elsewhere; its value doesn't matter. Additionally, y is always 0 or 1. It's value **does** matter for uniqueness!

## Steam3

These are relatively new. They are of the format "[U:1:x]". The "x" value is what matters for uniqueness.

## Steam64

The 64-bit integer steam64 is what is used on steam community profile links by default. These always start with the string "7656119" at least -  they do not start at 0! This is the recommended format for all input to get5.