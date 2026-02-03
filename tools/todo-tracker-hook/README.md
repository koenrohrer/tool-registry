# TODO Tracker

Surfaces TODO, FIXME, HACK, and XXX comments whenever they appear in written files. Helps you stay aware of technical debt as it's introduced rather than discovering it later.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "TODO Tracker"
3. Click Install

## Configuration

No configuration required.

## Usage

This hook triggers on `PostToolUse` for `Write` and `Edit` operations. After any file is written, it scans the content for `TODO`, `FIXME`, `HACK`, or `XXX` markers and prints them as reminders. It does **not** block the operation — it only surfaces the markers for awareness. Up to 5 matches are shown per file.
