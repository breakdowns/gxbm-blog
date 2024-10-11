+++
author = "Breakdowns"
title = "Rclone"
date = "2023-11-02"
description = "How to use Rclone feature"
categories = [
    "Tutorial"
]
tags = [
    "Mirror Bot"
]
image = "banner.jpg"
+++

## Installing Rclone
You must download and install [Termux](https://github.com/termux/termux-app/releases) App. After that run command `termux-setup-storage` and `pkg install rclone` to install Rclone.

## Generate `rclone.conf` file
**NOTE:** Each Cloud may have a slightly different way of generating it, So please follow the instructions.
- Run command `rclone config` to open menu then type `n` and please enter a name for the New Remote. **NOTE:** Don't add Space when adding a name for the New Remote.
![Preview](rclone-config.jpg)
- Select Cloud by entering number. **NOTE:** Here I choose Mega with number 31.
![Preview](choose-rclone-cloud.jpg)
- Enter your Mega Email, Then type `y` and enter your Mega password.
![Preview](credential-account.jpg)
- After that type `n` then `y` then type `q` for quit.
![Preview](completed.jpg)
- To copy files `rclone.conf` to internal storage, Use command `rclone config file` then `cp /data/data/com.termux/files/home/.config/rclone/rclone.conf /sdcard`.
![Preview](copy-rclone-file.jpg)

## Setup the Rclone feature on Bot
**NOTE:** Rclone feature is not enabled by default, So you have to contact Admin to enable it for you.
- Go to User Settings, Then click Rclone button.
![Preview](setup-rclone.jpg)
- Then upload your `rclone.conf` file.
![Preview](upload-rclone-file.jpg)

## How to upload using Rclone
**NOTE:** Only works when you reply to the message link.
- To use Rclone, you must add arguments `up: rcl`.
![Preview](command-rclone.jpg)
- Please select your Cloud. **NOTE:** here I choose Mega.
![Preview](choose-cloud.jpg)
- Then select upload destination. **NOTE:** Because I don't have a folder on my Mega, so just click **Choose Current Path**.
![Preview](choose-path.jpg)
- Done! My files are uploaded to Mega.
![Preview](done.jpg)

## Deleting/Replacing Cloud Accounts
Run command `rclone config` to open menu then type `d` and enter your cloud number.
![Preview](change-cloud-account.jpg)
After that, please follow the method above if you want to change or re-add your cloud account.
